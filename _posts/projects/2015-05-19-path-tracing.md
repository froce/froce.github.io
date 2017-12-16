---
layout: page
#subheadline:  "Path Tracing"
title:  "Path Tracing"
#teaser: "???"
categories:
    - projects
tags:
    - projects
    - path tracing
    - global illumination
header: no
image:
    title: pt.png
---

This Path Tracer was created for the Global Illumination course at Linköping University, together with two other students.
It is implemented in C++ and uses Visual Studio's auto-parallelization feature to improve performance. Only basic primitives, 
spheres, boxes and planes with either fully diffuse, specular or refractive surfaces are supported. Spherical area lights are directly sampled,
 to improve convergence. Reinhard's global tonemapping operator and gamma correction are applied before storing the output images.

<ul class="clearing-thumbs small-block-grid-4" data-clearing>
  <li><a href="{{ site.url }}/images/pt1_1024.png"><img data-caption="" class="th" src="{{ site.url }}/images/pt1_1024.png"></a></li>
  <li><a href="{{ site.url }}/images/pt2_512.png"><img data-caption="" class="th" src="{{ site.url }}/images/pt2_512.png"></a></li>
  <li><a href="{{ site.url }}/images/pt3_512.png"><img data-caption="" class="th" src="{{ site.url }}/images/pt3_512.png"></a></li>
  <li><a href="{{ site.url }}/images/pt4_512.png"><img data-caption="" class="th" src="{{ site.url }}/images/pt4_512.png"></a></li>
</ul>

### All Projects
{: .t60 }

{% include list-posts.html tag='projects' %}