---
layout: post
title:      "Pedal Board Exchange"
date:       2020-11-18 16:04:00 +0000
permalink:  pedal_board_exchange
---


Back in high school, I used to spend a lot of time buying and selling guitar effects pedals on Craigslist. I would check Craigslist regularly to see if there were any good deals on items that I had my eye on. Since I didn’t have a lot of free cash to spend on this pricey hobby, I often had a one-in-one-out sort of philosophy, selling one pedal to buy another or just trading with someone. In doing these transactions, a bit of research was required. The new price for the pedal, assuming it was still in production, was certainly a factor in resale value. The other main indicator was the price at which other people were selling the same or similar item. 

The concept for this app is to save time by collecting this information for you. The user can enter a specific pedal name or style of pedal into the CLI, and the console will display the different listings that match the search criteria. If one of those seems interesting, the user enters the corresponding number, and is taken to a sub menu that provides more information:

- the seller’s description from Craiglslist
- the manufacturer’s description
- the price new, as listed on Guitar Center (who announced they would be filing for bankruptcy while I was writing this, could be refactored to work with a different online retailer). 

An issue I anticipated while planning this project was the method with which Craigslist carries out a search. It doesn’t only search posting titles, it also searches the body of the seller’s ad from the listing. Often when searching for a specific pedal, you would get listings for a whole variety of items that weren’t what you were looking for. Sometimes the pedal you would be looking for was mentioned in the post as something the seller would be willing to trade their for. From personal experience I knew those cases were rare. Usually one word of your search was used in an ad for something guitar related but not at all what you were searching for. 

Take for example the distortion pedal “Ibanez Tube Screamer”. Each of those three words can show up in a post that isn’t really at all what you were searching for. Although Ibanez makes other gear, they mostly make guitars. A common erratic search result would be something along the lines of “For Sale Ibanez Electric Guitar” with the post body “like new ibanez electric guitar. I usually play through a Marshall tube amp. Great clean tones but then crank the distortion and it’s a real screamer!” Craigslist sees all of its search words so it throws this in the search results. I knew I wanted to avoid things like this in my app, so I have a function that only keeps the search results that match all of the user’s search terms in the actual title. Admittedly it’s not perfect. There is some chance of missing a pedal because the seller didn’t put enough information in the actual post title. Still I felt it was advantageous to only show results that definitely matched what the user was looking for.

Next problem is that some of the more popular pedals have many different versions. The Tube Screamer is a classic distortion pedal originally made in the early ‘80’s. Currently you can purchase a new “reissue” version of the tube screamer, along with a more compact mini model, as well as a bass version and a few other variants. By searching Craigslist with my app, you can immediately find out subtle differences and values for the versions in your area.

	An issue I hadn’t anticipated when planning this app was that sellers didn’t always take advantage of the manufacturer and model fields when making their post. This meant that I couldn’t count on being able to search Guitar Center using these two crucial pieces of information. In these cases it was likely that the necessary information was contained within the post title, so I used that as a back-up method to try to get info from GC. Unfortunately the titles sometimes include a little too many words which would throw off the GC search algorithm. I found that in these cases the GC website would provide tips for searching their website as well as results for products generally related- results that I didn’t want to accidentally add to the pedal object made from the Craigslist post. I would rather have no info than the wrong info, so I built a function that would prevent any additional information being added to the pedal object if the webpage it was scraping contained a “Search Tips” section.

	Overall this project has taught me the value of working with precise and discrete pieces of information, and how quickly a seemingly-stable program can fall apart when the data it’s passing around isn’t what it anticipated.
 

