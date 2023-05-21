---
layout: post
title:  "Used Sailboat Market Analysis - Part One"
date:   2023-03-05 23:00:00 -0400
categories: setup
---

In this upcoming serie, we'll delve into the current state of the used sailboat market in the United States. Using marketplace data and expert opinions, we'll explore the trends and factors influencing the market, including supply and demand, pricing, age and condition of vessels, and regional variations. Whether you're a sailor looking to buy or sell a used boat, or simply interested in the boating industry, this article will provide insights into the state of the market.

## Data Source, Data Collection

We have referenced various used sailboat inventory sites to pull characteristics about the boats currently on the market. 

- Title : the title of the boat page
- Make : the term "make" refers to the manufacturer or builder of the boat. It is the company or individual who designed, constructed, and branded the vessel. 
- Model : The term "model" refers to the specific type or class of sailboat produced by that manufacturer. Sailboat models are often named and can be identified by their unique design features, specifications, and performance characteristics. For example, a manufacturer like Beneteau may produce multiple models of sailboats, such as the Oceanis, First, or Sense, each with its own distinct features and intended use.
- Year : the year the boat was built
- Price [US$] : the average asking price found for this boat on all inventory sites 
- Location : where the boat is currently located
- LOA [ft]: LOA stands for "length overall" and is a common term used to describe the length of a sailboat. LOA refers to the maximum length of the boat, measured from the foremost point on the bow (the front of the boat) to the aftermost point on the stern (the back of the boat), including any protruding structures such as a bowsprit or swim platform. It is an important measurement for boat designers and builders, as it is used to determine the boat's size, capacity, and performance characteristics, such as speed, stability, and maneuverability. LOA is often used as a specification in boat listings, and is one of the key measurements used to classify boats into different size categories.
- LWL [ft]: LWL stands for "length at waterline" and is another common term used to describe the length of a sailboat. LWL refers to the length of the boat along the waterline, which is the line where the boat meets the surface of the water when it is afloat. This measurement excludes any overhanging structures like the bow and stern, and represents the portion of the boat that is in contact with the water when it is sailing.LWL is an important measurement for boat designers and builders, as it is used to calculate the boat's theoretical hull speed, which is the maximum speed the boat can travel through the water based on its length at the waterline. It is also used to determine other performance characteristics of the boat, such as stability, maneuverability, and resistance to drag.LWL is often used as a specification in boat listings, and is one of the key measurements used to classify boats into different size categories.
- beam [ft]: Beam refers to the width of the boat at its widest point. It is the measurement from one side of the hull to the other, typically taken at the widest point of the boat, which is often near the middle of the vessel.Beam is an important measurement for boat designers and builders, as it determines the boat's stability, capacity, and performance characteristics. A wider beam typically means a more stable boat, as it provides a wider base and greater resistance to tipping or rolling. However, a wider beam can also mean slower speed and more drag, as there is more surface area in contact with the water.Beam is often used as a specification in boat listings, and is one of the key measurements used to classify boats into different size categories.
- maxDraft [ft]: Max draft refers to the maximum depth of the boat's keel below the waterline. It is the measurement from the lowest point of the keel to the waterline, which represents the deepest point of the boat when it is afloat.
- displacement : 
- ballast : 
- headroom [ft]: Headroom refers to the vertical distance between the cabin sole (floor) and the underside of the deck or cabin roof. It is the measurement from the highest point of the cabin sole to the lowest point of the overhead structure.
 - url(s) : the urls of the listing

![sailboat measures](/assets/2023-03-05-used-sailboat-market-analysis-part1/measures.webp)

## Building the web scrapper

I developed a scrapper in Python using the Scrapy library and  Beautiful Soup
Scrapy framework takes care of the scaffolding of the project. The scrpaing code is developed and captured in the scrapers file located under /scrapers folder

Here is an example used to scrape a used sailboat inventory site

    import scrapy
    #import urlparse
    import urllib.parse
    # https://doc.scrapy.org/en/latest/intro/tutorial.html

    class BoatsSpider(scrapy.Spider):
        name = "boats_details"

        start_urls = [
               'http://www.yachtworld.com/core/listing/cache/searchResults.jsp?N=2285+2279+1783',
        ]


        def parse(self, response):
            for href in response.css('.make-model a::attr(href)'):
                yield response.follow(href, self.parse_boat)

            # follow pagination links - crawls ALL pages !
            # for href in response.css('.navNext a::attr(href)'):
            #     yield response.follow(href, self.parse)


        def parse_boat(self, response):
            def extract_with_css(query):
                return response.css(query).extract_first().strip()

            yield {
                # 'boattitle' : boat.css('a::text'),
                'title' : extract_with_css('div.boat-title h1::text'),
                # 'year' : response.css('div.boat-title').re_first(r'\d\d\d\d'),
                'price' : extract_with_css('div.boat-price::text'),
                'location' : extract_with_css('div.boat-location::text'),
                'loa' : response.css('div.fullspecs').re_first(r'LOA:\s*(.*)<br>'),
                'lwl' : response.css('div.fullspecs').re_first(r'LWL:\s*(.*)<br>'),
                'beam' : response.css('div.fullspecs').re_first(r'Beam:\s*(.*)<br>'),
                'maxDraft' : response.css('div.fullspecs').re_first(r'Maximum Draft:\s*(.*)<br>'),
                'displacement' : response.css('div.fullspecs').re_first(r'Displacement:\s*(.*)<br>'),
                'ballast': response.css('div.fullspecs').re_first(r'Ballast:\s*(.*)<br>'),
                'headroom' : response.css('div.fullspecs').re_first(r'Headroom:\s*(.*)<br>'),
                'url' : response.request.url,
                'make-model' : urlparse.urlsplit(response.request.url).path.split('/')[3].replace('-', ' ')[:-8].upper(), 
                'year' : urlparse.urlsplit(response.request.url).path.split('/')[2],
            }





## Raw Data Format

The data is extracted in the json format. Here is an [example dataset](/assets/2023-03-05-used-sailboat-market-analysis-part1/inventoryNov2017.json) extracted in Nov 2017. Here are the 2 frist json records of the file :

        [
        {"headroom": null, "make-model": "HERRESHOFF SCHOONER INGOMAR", "title": "2016\u00a0Herreshoff Schooner Ingomar", "url": "http://www.yachtworld.com/boats/2016/Herreshoff-Schooner-Ingomar-2612668/ME/United-States", "price": "US$\u00a01,166,600", "maxDraft": "16 ft 7 in", "displacement": null, "beam": "24 ft 2 in", "loa": "176 ft 9 in", "location": "ME, United States", "lwl": "85 ft 10 in", "year": "2016", "ballast": null},
        {"headroom": null, "make-model": "ROYAL HUISMAN ", "title": "2004\u00a0Royal Huisman", "url": "http://www.yachtworld.com/boats/2004/Royal-Huisman--3041392/United-States", "price": "US$\u00a053,000,000", "maxDraft": "5.50 m", "displacement": null, "beam": "12.20 m", "loa": "90.0 m", "location": "United States", "lwl": null, "year": "2004", "ballast": null},
        ]




