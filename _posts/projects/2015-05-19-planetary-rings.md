---
layout: page-fullwidth
#subheadline:  "Path Tracing"
title:  "Planetary Rings for Dome Rendering"
#teaser: "???"
categories:
    - projects
tags:
    - projects
    - dome rendering
    - procedural content
header: no
image:
    title: rings1.png
---

This project was created for the Media Production for Immersive Environments course at Linköping University.
The program is written in C++ and uses <a href="https://c-student.itn.liu.se/wiki/develop:sgct:sgct">Simple Graphics Cluster Toolkit</a> to handle frame and data synchronization between the nodes in the dome's cluster,
as well as the necessary fisheye projection. Rendering is done using deferred shading and modern OpenGL features, like MultiDrawIndirect.
The planet's texture is based on a photograph of Saturn, distorted using noise and changing the color channels to get the blue hues. Similarly, at large viewing distances the rings are rendered as a single ring of triangles, with a 1D texture 
and some noise. This texture gets faded out at closer distances, while individual asteroids slowly fade in.

The asteroids are distorted subdivided icosahedra, which are created at different levels of detail at load-time and later scaled individually to create additional variation.
The shadows between the planet and the rings are ray traced, using a ray-annulus intersection for the rings and a ray-sphere intersection for the planet. There is no inter-object shadowing between asteroids, but there is ray-marched self-shadowing.

<ul class="clearing-thumbs small-block-grid-4" data-clearing>
  <li><a href="{{ site.url }}/images/rings1.png"><img data-caption="" class="th" src="{{ site.url }}/images/rings1.png"></a></li>
  <li><a href="{{ site.url }}/images/rings2.png"><img data-caption="" class="th" src="{{ site.url }}/images/rings2.png"></a></li>
  <li><a href="{{ site.url }}/images/rings3.png"><img data-caption="" class="th" src="{{ site.url }}/images/rings3.png"></a></li>
  <li><a href="{{ site.url }}/images/AsteroidDebug1.png"><img data-caption="" class="th" src="{{ site.url }}/images/AsteroidDebug1.png"></a></li>
  <li><a href="{{ site.url }}/images/AsteroidDebug2.png"><img data-caption="" class="th" src="{{ site.url }}/images/AsteroidDebug2.png"></a></li>
</ul>

### All Projects
{: .t60 }

{% include list-posts.html tag='projects' %}