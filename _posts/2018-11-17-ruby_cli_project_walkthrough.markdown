---
layout: post
title:      "Ruby CLI Project Walkthrough"
date:       2018-11-18 01:33:31 +0000
permalink:  ruby_cli_project_walkthrough
---

For my project I scraped data from Beer Advocates Top 250 beer list using Open URI and Nokogiri.

First step was to require all necessary files in `environment.rb`. In addition to the auto-generated versions local path I also started off by requiring my CLI class file and eventutally throughout the process of creation a Scraper class as well as a Beer class.

In `cli.rb` there is a a base `run` method that is used to execute the program. That method begins by scraping the data behind then scenes and then run another method called `show_list` which as you can guess shows the list of scraped data. When the data is scraped an object for each element in the list is created which is out Beer class.

Because the list is so long (250) I decided to let `show_list` take an argument of the desired amount shown so we could display as much or as little of the data as desired. This would also be useful for pagination but things would have to be tweaked a bit further.

Going back to the `run` method, after the list is shown you are presented with some instructional text that basically presents the options of the program (select a number between 1 and 250 to see info on a beer, full for the whole list, or q to quit the program). 

Following that we go through the `options` method which present the user with the option for declaring what their next move is, anything that is input aside from what options are listed above results in an error and a repromt of what the valid options are

When a value is selected we run through a second scraper method called `scrape_beer` which takes the url of the beer object selected and fetches specific information about that object

Fun project!
