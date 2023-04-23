---
layout: post
title:  "Used Sailboat Market Analysis"
date:   2023-03-05 23:00:00 -0400
categories: setup
---

In this upcoming article, we'll delve into the current state of the used sailboat market in the United States. Using marketplace data and expert opinions, we'll explore the trends and factors influencing the market, including supply and demand, pricing, age and condition of vessels, and regional variations. Whether you're a sailor looking to buy or sell a used boat, or simply interested in the boating industry, this article will provide insights into the state of the market.

## The Data

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

   
## Approach

Libraries used include BeautifulSoup. A MS powerbi dashboard presents the information wtih filters, geo rep.
 

## Analysis

 Next evolutions should include 
 1. time series based on regular data extractions
 2. multiple source listings sites
 3. deduping of entries
 4. analysis of most likely t sell in a specific category, price range etc... could be done using AI

Stay tuned...



