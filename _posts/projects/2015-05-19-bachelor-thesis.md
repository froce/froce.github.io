---
layout: page
#subheadline:  "Bewegungserfassung mit Kameranachführung und Übertragung auf ein Körpermodell am Beispiel der Microsoft Kinect"
title:  "Bachelor Thesis"
teaser: "Motion- and Camera Tracking with transfer to a Rigid Body Model using Microsoft Kinect"
categories:
    - projects
tags:
    - projects
    - bachelor thesis
    - kinect
header: no
image:
    title: Modellvergleiche3.png
---

This was the thesis project for my Bachelor's degree, originally titled "Bewegungserfassung mit Kameranachführung und Übertragung auf ein Körpermodell am Beispiel der Microsoft Kinect". It involved first taking the motion tracking data
 and applying to a 3D model and secondly mounting the Kinect on a rotating platform and keeping the user within its field of view. The main application was written in C#, using the Kinect SDK to read the tracking data, XNA for rendering and WPF as the windowing library.
To improve the match between the tracking data and the resulting model pose cyclic coordinate descent inverse kinematics are applied to different chains in the model's skeleton.

The rotating platform for camera tracking is controlled by a LEGO NXT brick, using USB to communicate with the host. The actual control is done using a slightly modified version of the MotorControl library, which runs natively on the NXT.
 

<ul class="clearing-thumbs small-block-grid-4" data-clearing>
  <li><a href="{{ site.url }}/images/Modellvergleiche3.png"><img data-caption="" class="th" src="{{ site.url }}/images/Modellvergleiche3.png"></a></li>
  <li><a href="{{ site.url }}/images/Anwendungsfenster.png"><img data-caption="" class="th" src="{{ site.url }}/images/Anwendungsfenster.png"></a></li>
</ul>

### All Projects
{: .t60 }

{% include list-posts.html tag='projects' %}