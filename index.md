---
layout: lesson
root: .  # Is the only page that doesn't follow the pattern /:path/index.html
permalink: index.html  # Is the only page that doesn't follow the pattern /:path/index.html
venue: "Fermi National Accelerator Laboratory"
address: "online"
country: "us"
language: "en"
latitude: "45"
longitude: "-1"
humandate: "May 24-25, 2023"
humantime: "8:00 am - 3:00 pm"
startdate: "2023-05-24"
enddate: "2023-05-25"
instructor: ["Michael Kirby","Steve Timm","Tom Junk","Ken Herner"]
helper: ["mentor1", "mentor2"]
email: ["mkirby@fnal.gov","timm@fnal.gov","junk@fnal.gov","herner@fnal.gov"]
collaborative_notes: "2023-05-24-dune"
eventbrite:
---

This tutorial will teach you the basics of DUNE Computing. 

Instructors will engage students with hands-on lessons focused in three areas:

1. Data storage and management,
2. Introduction to LArSoft,
3. Job submission and monitoring.

Mentors will answer your questions and provide technical support.

<!-- this is an html comment -->

{% comment %} This is a comment in Liquid {% endcomment %}

> ## Prerequisites
>
> Command line experience is necessary for this training. We recommend the
> participants to go through
> [The Unix Shell](https://swcarpentry.github.io/shell-novice/), if new to the
> command line (also known as terminal or shell).  
{: .prereq}

By the end of this workshop, participants will know how to:

* Utilize data volumes at FNAL.
* Understand good data management practices.
* Provide a basic overview of art and LArSoft to a new researcher.
* Develop configuration files to control batch jobs.
* Monitor jobs submitted to the grid.

You will need to be a DUNE Collaborator (listed member), and have a valid FNAL or CERN computing account to join the tutorial. Contact your  DUNE group leader for assistance.

> ## Getting Started
>
> First step: follow the directions in the "[Setup](
> {{ page.root }}/setup.html)" to arrived prepared for this event. Follow the instructions; we give you an easy exercise 
> to make sure you are good to go.
{: .callout}


<h2 id="schedule">Schedule by Day</h2>

The official schedule for this event is listed on the [Indico site (59762)](https://indico.fnal.gov/event/59762/timetable/#20230524).

{% include sc/schedule.html %}

<!--<center><img  alt="" src="fig/Schedule_computing_training_202105.png"/></center>-->

<!-- An [asynchronous session]({{site.baseurl}}/asynchronous/) is designed as later day acivities for the first two days of the workshop.-->

{% include links.md %}
