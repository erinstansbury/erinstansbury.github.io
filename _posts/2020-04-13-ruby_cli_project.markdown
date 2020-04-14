---
layout: post
title:      "Ruby CLI Project"
date:       2020-04-13 10:47:27 -0400
permalink:  ruby_cli_project
---


For this portfolio project the goal was to create a ruby gem and scrape a site for its data. One example given was a Daily Deals CLI, that when prompted would scrape two sites that advertised their top deals of the day and return the two deals to the user. From there, the user could see more information about each deal if they were interested. 

[The example project can be found here](https://github.com/learn-co-curriculum/daily_deal)


When trying to think about what I would want to create, I was hesitant to accidentally use what others had created in the past, ie Kickstarter, Top Restaurants, etc. Something I thought would be a bit timely would be to create a CLI that would return the latest statistics on the coronavirus pandemic. 


[](https://giphy.com/gifs/6dRsQSNHU3Cla/html5)

Firstly, I began to plan out the project and understand what statistics I would like to display to the user. These were the stats I was going to scrape then display:

* The Top 10 countries with the most people affected
* The number of reported cases worldwide
* The number of deaths caused by the coronavirus
* The number of people who have recovered from coronavirus

From there, I wanted to drill in a bit further. If the user wants to see more detailed data about the cases, it would then display:
**The number of reported cases worldwide**  ->
* The number of currently affected patients
* The number of cases in mild condition
* The number of cases in a serious condition


When I began the CLI, I wanted to make sure that after the proper data was printed, the user was prompted again if they wanted to see more virus statistics.

```
    def self.menu
        puts "-- Type 'cases' for the number of confirmed cases worldwide"
        puts "-- Type 'deaths' for the number of Covid-related deaths worldwide"
        puts "-- Type 'recovered' for the number of reported virus recoveries"
        puts "-- Type 'top' for the list of the top ten countries affected by Covid"
        puts "To exit, just type 'exit'"
        input = gets.strip.downcase
    
        if input == "cases"
            Scraper.scrape_worldwide
        elsif input == "deaths"
            Scraper.scrape_deaths
            Scraper.prompt
        elsif input == "recovered"
            Scraper.scrape_recovered
            Scraper.prompt
        elsif input == "top"
            Scraper.scrape_countries
            Scraper.prompt
        else input == "exit"
            Scraper.goodbye
        end
    end
```
