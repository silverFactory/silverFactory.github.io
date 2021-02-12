---
layout: post
title:      "Stage Time"
date:       2021-02-12 15:17:09 +0000
permalink:  stage_time
---


One of my favorite parts of New York is the open mic scene. Whether your thing is music, comedy, or anything else that needs an audience; there is somewhere that’ll allow you to hone your craft. Finding the right one, however, isn’t always easy. I wanted to design a website to allow aspiring performers of all sorts to find their audience, as well as create a social space to foster connectedness, creativity, and collaboration.

As the host of an open mic, you can quickly set up a page with all the information needed to reach your target audience. Something I have experienced first hand is going to a mic that is listed on a bar’s website as being open to all genres of performance. This page was presumably maintained by the owner, and not accurate, I got there and it was exclusively comics. This situation is easily avoided if the hosts of these mics have a simple and direct method of advertising for themselves. This data is represented by the genre attribute of the open_mic model I made in rails. Everything else a performer could need to know is part of the open_mic model: sign-up procedure, cover, drink/food min, location, time etc. 

 Another feature of the open_mic page is the update section. This functions differently than Facebook updates that populate a wall and allow people to comment and all that. My updates are intentionally more limited in scope. Only the most recent update is posted to the open_mic’s show page, serving the purpose of simply giving potential performers one extra bit of information specific to the upcoming show. I have personally hauled my gear from Brooklyn into Manhattan just to find out that the mic is cancelled that night due to a sewage leak. If the mic had the ability to post about this, it would've saved me the headache. 

	The other two aspects of the open-mics page are geared towards connected performers and promoting collaboration. The first is missed-connections, which allows performers(users) to make a simple post with a title and body for the purpose of connecting with someone they saw in last week’s show. I’ve met some great people at open mics, walking to the train after or hanging around outside; but a lot of times you don’t have a chance to connect in the moment. The other aspect of the open mic page designed to connect performers I have called lend-a-hand, which provides a way for people to ask for a little help on stage for the upcoming show. An example of this would be a story-teller or poet looking for someone to play a little jazz piano with them on stage as support.

	I created a single nested resource- the support model- to track these posts, since from the user’s perspective they are identical: a title for the post and the body of the post. I added two boolean attributes- missed_connection and lend_a_hand- to differentiate how and where they would be displayed on the open_mic’s page. These are tracked via hidden inputs on the new_support form. Once a support post is made, other users have the opportunity to respond and connect via comments. 

Users also have their own show pages which are fairly streamlined. They can add a link for a picture of themselves to be displayed. There’s also a little bio section. When they sign up they also have the options to link to Facebook, Instagram, Youtube, Bandcamp, and Spotify. Although this site isn’t designed for artist promotion, I thought it would be helpful to include these links so that when users are interacting via the missed_connections and lend_a_hands they can follow the links to find out more about their potential collaborators.

