---
#
# Use the widgets beneath and the content will be
# inserted automagically in the webpage. To make
# this work, you have to use › layout: frontpage
#
layout: page-fullwidth
#title: "Projects and Demos"
header:
   image_fullwidth: "rings3.png"
   title: "Projects and Demos"
---
<ul class="medium-block-grid-3 large-block-grid-3">
	<li>
        <a href="{% post_url projects/2015-05-15-shadow-mapping-using-rectilinear-warping %}"><img src="{{ site.url }}/images/RectilinearShadowWarping.png" alt="" class="th">
        <p>Shadow Mapping using Rectilinear Shadow Warping</p></a>
    </li>
    <li>
        <a href="{% post_url projects/2015-05-19-path-tracing %}"><img src="{{ site.url }}/images/pt.png" alt="" class="th">
        <p>Path Tracing</p></a>
    </li>
	<li>
		<a href="{% post_url projects/2015-05-19-smoke-rendering %}"><img src="{{ site.url }}/images/smoke.png" alt="" style="width: 100%" class="th">
        <p>Smoke Rendering in Maya's Viewport 2.0</p></a>
    </li>
    <li>
		<a href="{% post_url projects/2015-05-19-planetary-rings %}"><img src="{{ site.url }}/images/rings1.png" alt="" class="th">
        <p>Planetary Ring System for Fulldome Rendering</p></a>
    </li>
	<li>
		<a href="{% post_url projects/2015-05-19-tower-defense %}"><img src="{{ site.url }}/images/TD2.png" alt="" class="th">
        <p>Yet Another Tower Defense</p></a>
    </li>
	<li>
		<a href="{% post_url projects/2015-05-19-bachelor-thesis %}"><img src="{{ site.url }}/images/Modellvergleiche3.png" alt="" class="th">
        <p>Bachelor Thesis</p></a>
    </li>
	<li>
		<a href="{% post_url projects/2015-05-19-gpu-path-tracing %}"><img src="{{ site.url }}/images/CUDATracer2.png" alt="" class="th">
        <p>GPU Path Tracing</p></a>
    </li>	
    <li>
		<a href="{% post_url projects/2015-05-19-mesh-to-sdf %}"><img src="{{ site.url }}/images/MeshToSDF1.png" alt="" class="th">
        <p>Mesh to Signed Distance Field Conversion and Raymarching</p></a>
    </li>       
</ul>