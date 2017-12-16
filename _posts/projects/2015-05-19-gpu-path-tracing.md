---
layout: page
#subheadline:  "Path Tracing"
title:  "GPU Path Tracing"
#teaser: "???"
categories:
    - projects
tags:
    - projects
    - path tracing
header: no
image:
    title: CUDATracer4.png
---
I decided to create this some time after writing the CPU path tracer for university, to get a better understanding of physically based rendering, with more interesting BRDFs and to add 
tracing of triangle meshes, which was not possible with the CPU tracer. Additionally I wanted to improve performance and it seemed like a good project to learn more about CUDA development.
This is still very much work in progress, but some of the current features are:

* Progressive Rendering
* Model loading using Assimp
* Cook-Torrance BRDF
* GPU-based BVH construction




<ul class="clearing-thumbs small-block-grid-4" data-clearing>
  <li><a href="{{ site.url }}/images/CUDATracer4.png"><img data-caption="" class="th" src="{{ site.url }}/images/CUDATracer4.png"></a></li>
  <li><a href="{{ site.url }}/images/CUDATracer2.png"><img data-caption="" class="th" src="{{ site.url }}/images/CUDATracer2.png"></a></li>
  <li><a href="{{ site.url }}/images/CUDATracer3.png"><img data-caption="" class="th" src="{{ site.url }}/images/CUDATracer3.png"></a></li>
  <li><a href="{{ site.url }}/images/balls.png"><img data-caption="" class="th" src="{{ site.url }}/images/balls.png"></a></li>
</ul>

### All Projects
{: .t60 }

{% include list-posts.html tag='projects' %}