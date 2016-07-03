---
layout: project
title: Garminello - Trello for Garmin devices
technologies:
  - Monkey C
  - NodeJS
  - BackboneJS
  - Browserify
  - Babel
  - Gulp
  - JavaScript ES6
  - Express
  - PostgreSQL
  - Heroku
  - Docker
category: software
tags:
  - watch
  - mobile
  - server
  - client
repositories:
  - url: https://github.com/fikander/garminello-watch
    name: Garmin watch application (MonkeyC)
  - url: https://github.com/fikander/garminello-web
    name: NodeJS based backend and BackboneJS frontend
published: true
---

Having used [Fitbit One](https://www.fitbit.com/uk/one) since 2012, I decided to finally try different sports tracker.

The choice was newly released in April 2016 Garmin [vívoactive® HR](https://buy.garmin.com/en-US/US/wearabletech/wearables/vivoactive-hr/prod538374.html).

![Garmin vívoactive® HR]({{ site.baseurl }}/images/projects/vivoactive_hr.jpg)

It's a brilliant watch, with many smartwatch functions (calls, notifications etc.), impressive selection of supported sports (smimming was the big one for me as I swim indoor a lot), and a built-in GPS.


## Motivation

The one feature it doesn't support though (at least at the time of writing) is **customised workouts**.
What I wanted is an easy way to prepare a set of exercises together with durations, and play them on my watch as I exercise.

Good example of such a workout would be [7 min workout](http://7-min.com/) or different variations of it. Timing matters, and you have some 13-15 exercises to remember.

## What it is

This project was to integrate [Trello](http://trello.com) with Garmin devices. Workouts can be easily defined in Trello (see this [example public board](https://trello.com/b/SOCdcatH/workouts)).
Note, how durations for each element of the workout sequence are defined using simple `[XXm YYs]` text added to the card summary.

This required:

1. writing a web backend and frontend that integrated with Trello using their REST API. It supports user registration (using [passport](https://github.com/jaredhanson/passport)).
1. writing an [Connect IQ app](https://apps.garmin.com/) which would communicate with the backend

The app is available at **[Garmin IQ Shop](https://apps.garmin.com/en-US/apps/da6ba406-488c-4f10-83d4-3e70507d4656)**. It has its dedicated **[Garminello website](https://garminello.herokuapp.com)** hosted on [heroku](http://heroku.com).

The diagram below shows state changes of the app:
![Garminello app diagram]({{ site.baseurl }}/images/projects/garminello_app_diagram.png) 

## Lessons learned

* NodeJS - my first project using Express framework 
* JavaScript ES6 - this is the first project where I had a chance to use ECMAScript 6 specification. Thanks to [Babel project](https://github.com/babel/babel) (and babelify for browserify) this was pretty easy.
* Web backend is Dockerised. Launching NodeJS and PostgreSQL based backed locally is a matter or running docker-compose.
* Hosting and monitoring using heroku.
* Programming for a very resource constrained device using fairly limited C++ - like language - Monkey C
