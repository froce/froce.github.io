---
layout: page
#subheadline:  "Path Tracing"
title:  "Smoke Rendering in Maya"
#teaser: "???"
categories:
    - projects
tags:
    - projects
    - smoke
    - maya
header: no
image:
    title: smoke.png
---

The goal of this project was creating a plug-in for Maya that would render smoke. The initial idea was to be able to use implicit functions and level-sets as primitives for the smoke shape. However, due to lack of time the implementation was limited to the sphere shape primitive.
The smoke is created, by first rasterizing its bounding box and then ray-marching the smoke's density field in a fragment shader.
The shading supports both a simple pure absorption model, as well as brute-forced single scattering, for point lights present in the Maya scene.
This brute-force approach was obviously very slow, barely real-time on the hardware we tested it on.
As mentioned, the plug-in would use light information from Maya, and it also allowed modifying the smoke's parameters from within Maya.



<ul class="clearing-thumbs small-block-grid-4" data-clearing>
  <li><a href="{{ site.url }}/images/density01.JPG"><img data-caption="" class="th" src="{{ site.url }}/images/density01.JPG"></a></li>
  <li><a href="{{ site.url }}/images/density0.JPG"><img data-caption="" class="th" src="{{ site.url }}/images/density0.JPG"></a></li>
  <li><a href="{{ site.url }}/images/density00.JPG"><img data-caption="" class="th" src="{{ site.url }}/images/density00.JPG"></a></li>
  <li><a href="{{ site.url }}/images/density.JPG"><img data-caption="" class="th" src="{{ site.url }}/images/density.JPG"></a></li>
  <li><a href="{{ site.url }}/images/light.JPG"><img data-caption="" class="th" src="{{ site.url }}/images/light.JPG"></a></li>
  <li><a href="{{ site.url }}/images/red smoke.JPG"><img data-caption="" class="th" src="{{ site.url }}/images/red smoke.JPG"></a></li>
  <li><a href="{{ site.url }}/images/red smoke2.JPG"><img data-caption="" class="th" src="{{ site.url }}/images/red smoke2.JPG"></a></li>
  <li><a href="{{ site.url }}/images/smoke1.JPG"><img data-caption="" class="th" src="{{ site.url }}/images/smoke1.JPG"></a></li>
  <li><a href="{{ site.url }}/images/smoke2.JPG"><img data-caption="" class="th" src="{{ site.url }}/images/smoke2.JPG"></a></li>
  <li><a href="{{ site.url }}/images/smoke3.JPG"><img data-caption="" class="th" src="{{ site.url }}/images/smoke3.JPG"></a></li>
</ul>

### All Projects
{: .t60 }

{% include list-posts.html tag='projects' %}