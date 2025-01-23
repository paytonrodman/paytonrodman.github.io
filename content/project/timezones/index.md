---
title: "Converting meeting times between timezones"
subtitle: ""
summary: A tiny personal project to help me never miss a meeting!
date: "2024-01-00T00:00:00Z"
tags: ["Completed Work"]

reading_time: true  # Show estimated reading time?
share: false  # Show social sharing links?
profile: false  # Show author profile?
comments: false  # Show comments?
math: true
weight: 1

# Featured image
# To use, place an image named `featured.jpg/png` in your page's folder.
# Placement options: 1 = Full column width, 2 = Out-set, 3 = Screen-width
# Focal point options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
# Set `preview_only` to `true` to just use the image for thumbnails.
image:
  placement: 1
  caption: ""
  focal_point: "Center"
  preview_only: false
  alt_text: ""
---

As an Australian living in the UK and collaborating with researchers around the world, I often have to deal with meetings scheduled in another timezone. Unfortunately, whenever I'm presented with a time in a different timezone, I go silly and tend to mess up the conversions, especially when daylight savings is involved. To save myself some time and worry, I decided to write a short script which could convert a meeting time from one timezone to another.

The webapp can be found [here](https://paytonrodman.pythonanywhere.com/)!

Simply enter the data, time, and location of the original meeting, and the location you want the meeting localised to, and hit Submit!

The logic of the app is written in Python, served using [Flask](https://flask.palletsprojects.com/en/stable/) through [pythonanywhere](https://www.pythonanywhere.com/).
