---
layout: post
title:      "TIMESHEET a Sinatra App"
date:       2019-02-02 05:21:24 +0000
permalink:  timesheet_a_sinatra_app
---


For my second project I decided a timesheet app that allows logged in users to log their start and end times for a particular date and then show a full list of all users inputs. In a real world scenario this makes no sense but I thought it was funny so ¯\_(ツ)_/¯

To tackle the project I first start off with building out the login and account creating process. I was a bit confused with the serializes session token and how that related to a users session through the labs but once i coded this out and i realized that the generated token was not actually tied permanently to the user it all clicked.

I user Corneal to both generate the project folder structure as well as their scaffold generator to build out all my migrations, models, views, AND controllers. Pretty great task they have goin for them but one pitfall i found that actually ended up costing me a bunch of time was they did not `use Rack::MethodOverride` to the `config.ru` so PATCH and DELETE methods were erroring and suggesting the user of a POST instead. All good tho

After working through that I once again used scaffold to generate everything i needed for the time logs part of this whole project. That was all really easy to set up but once it was complete there was a bit of confusion as to what the best way to manage users not being able to manually go to urls to lets say edit another users time log. To solve this i ended up putting a check on every GET request to see if the session id matched the user ID or just check if there was an active session (whichever made sense for the respective get request). That seemed to work well as i kicked the tires and tried to break it although it felt a bit dirty repeating the checks over and over, maybe a helper could have been used in that scenario

All in all, fun nonsensical project that affirmed and cemented a lot of MVC knowledge that i did not initially feel very confident on.
