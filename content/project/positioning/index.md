---
title: lighTag - A UWB Positioning System Integrated in Lighting System and its Applications
summary: This project mainly focused on the research of the Ultra-wideband (UWB) technology and Internet of Things as well as their applications; supported by MIT Hong Kong Innovation Node and The Hong Kong Polytechnic University, made by KWOK Hin Chi, PAN Zewen, and ZHANG Wengyu from The Hong Kong Polytechnic University.
tags:
  - Internet of Things
  - Arduino
date: '2022-08-20T00:00:00Z'

# Optional external URL for project (replaces project detail page).
external_link: ''

image:
  caption: The diagram of 
  focal_point: Smart

links:
  - icon: github
    icon_pack: fab
    name: Github
    url: https://github.com/lighTag-UWB/lighTag

# url_pdf: ''
url_code: 'https://github.com/lighTag-UWB/lighTag/blob/main/backend.py'
url_slides: 'https://drive.google.com/file/d/1f5DzByI5hgoxdT9DESYJlOTlE70j8zAN/view?usp=sharing'
# url_video: ''

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
# slides: example
---

The lighTag UWB Project, supported by MIT Hong Kong Innovation Node and The Hong Kong Polytechnic University, is a research endeavor focusing on Ultra-wideband (UWB) technology and Internet of Things (IoT) applications. The project aims to address various challenges, such as indoor positioning, visitor recording during Covid-19, and smart lighting control.

The main features of lighTag include its integration with the building's lighting system, enabling continuous power supply for UWB bases. With four lighTag Base Stations, the system achieves 3D indoor positioning, accurately determining the x, y, and z coordinates of the lighTag Tags integrated into users' devices. It boasts high accuracy, with 5cm ranging accuracy, 10cm 2D accuracy, and 20cm 3D accuracy, facilitating precise user positioning. Additionally, lighTag can detect users' presence in specific areas within the building.

The project comprises three main components: Tag & Base, Algorithm API, and User Interface. The Tag & Base component utilizes the BP-TWR-50 UWB Module with Two Way Ranging (TWR) distancing algorithm. Python is used to implement the Multilateration Positioning Algorithm, enabling the calculation of coordinates from distance data. The User Interface, built with Python's Kivy library, offers real-time plotting of the user's position, Area of Interest (AOI) detection, and mobile app packaging possibilities.

The applications of lighTag are diverse. It facilitates 3D indoor navigation in venues like shopping malls, airports, and factories, with floor numbers clearly indicated. When integrated with the LeaveHomeSafe App, lighTag automatically records users' arrivals and departures, captures detailed location information, and measures social distancing. Additionally, lighTag intelligently adjusts indoor lighting, including ON/OFF status and brightness, based on the users' positions and the number of people present.

Overall, the lighTag UWB Project introduces a promising solution for enhancing indoor positioning, visitor recording, and smart lighting control, contributing to improved user experiences and efficiency in various indoor environments.