---
layout: post
title:      "Guitar Vault"
date:       2020-12-29 18:15:24 +0000
permalink:  guitar_vault
---


The purpose of this app is to allow guitar enthusiasts to catalog and view their gear. I broke up the gear into three different models: guitars, amps, and pedals. Guitars have model, manufacturer, and category (acoustic, electric, bass, etc.) attributes. Amps ended up having a lot: name, power type, watts, number of speakers, number of channels, speaker size as well as name and manufacturer. Pedals were just name, manufacturer, category, and power supply requirements.

Overall the process of making this web app was pretty smooth. Initially I wanted to call the “category” column for the guitars table “type”, but that was a class inheritance keyword so I had to rename it. All of my route controller files extend application_controller. I had to rename amps_controller to guitar_amps_controller because amps_controller came before application_controller in the app folder and apparently those get loaded up alphabetically. 

A debugging technique that really helped during this project was bouncing back and forth between looking at the entries in the database with tux, and the Sinatra error messages when the server was running on shotgun. For example, initially I was able to make a new guitar without any Sinatra errors but I wasn’t showing up in my vault. A quick hop over to tux to check out the database revealed that the object was persisted, but user_id was nil. Quick fix in the post ‘/guitars/new’ route and I was back on track.

