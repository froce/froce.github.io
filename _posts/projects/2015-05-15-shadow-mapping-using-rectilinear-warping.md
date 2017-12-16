---
layout: page
#subheadline:  "Shadow Mapping"
#title:  "Shadow Mapping using Rectilinear Shadow Warping"
teaser: "???"
categories:
    - projects
tags:
    - projects
    - shadows
header: no
image:
    title: RectilinearShadowWarping.png
---

{% highlight glsl %}
void expandTriangle(inout vec2 screenPos[3])
{
	vec2 edge[3];
	edge[0] = screenPos[1].xy - screenPos[0].xy;
	edge[1] = screenPos[2].xy - screenPos[1].xy;
	edge[2] = screenPos[0].xy - screenPos[2].xy;

	
	float area = abs(0.5f * (edge[0].x * edge[1].y-edge[1].x*edge[0].y));
	
	float PixelDiagonal = 1.0/2.0;	

	if(area < 0.0000001) //Triangle is degenerate
	{
		float distAB = dot(screenPos[0], screenPos[1]);
		float distBC = dot(screenPos[2], screenPos[1]);
		float distAC = dot(screenPos[0], screenPos[2]);

		//if(distAB < distAC && distBC < distAC) //Everythings fine.
		if(distAB > distAC) //A or C are midpoint
		{
			vec2 temp;
			if(distBC < distAB) //C midpoint
			{
				temp = screenPos[1];
				screenPos[1] = screenPos[2];
				screenPos[2] = temp;
			}
			else //A midpoint
			{
				temp = screenPos[1];
				screenPos[1] = screenPos[0];
				screenPos[0] = temp;
			}
		}

		edge[0] = screenPos[1].xy - screenPos[0].xy;
		edge[1] = screenPos[2].xy - screenPos[1].xy;
		edge[2] = screenPos[0].xy - screenPos[2].xy;

		vec2 extensionEdge = vec2(0,0);
		if(dot(edge[0],edge[0]) > 0.00001)
			extensionEdge = edge[0];
		else if(dot(edge[1],edge[1]) > 0.00001)
			extensionEdge = edge[1];
		else if(dot(edge[2],edge[2]) > 0.00001)
			extensionEdge = edge[2];

		
		vec2 extensionNormal = normalize(extensionEdge);
		extensionNormal = vec2(-extensionNormal.y, extensionNormal.x);

		screenPos[0] += 0.000001*PixelDiagonal * extensionNormal;
		screenPos[2] += 0.000001*PixelDiagonal * extensionNormal;
		screenPos[1] -= 0.000001*PixelDiagonal * extensionNormal;

		edge[0] = screenPos[1].xy - screenPos[0].xy;
		edge[1] = screenPos[2].xy - screenPos[1].xy;
		edge[2] = screenPos[0].xy - screenPos[2].xy;

		if((edge[0].x * edge[1].y-edge[1].x*edge[0].y) < 0.0)
		{
			vec2 temp;
			temp = screenPos[2];
			screenPos[2] = screenPos[0];
			screenPos[0] = temp;

			edge[0] = screenPos[1].xy - screenPos[0].xy;
			edge[1] = screenPos[2].xy - screenPos[1].xy;
			edge[2] = screenPos[0].xy - screenPos[2].xy;
		}
	}

	vec2 edgeNormal[3];
	//edgeNormal[0] = normalize(edge[0]);
	//edgeNormal[0] = vec2(-edgeNormal[0].y, edgeNormal[0].x);

	//edgeNormal[0] = normalize(edge[0]);
	//edgeNormal[1] = normalize(edge[1]);
	//edgeNormal[2] = normalize(edge[2]);
	

    // If triangle is back facing, flip it's edge normals so triangle does not shrink.
    //vec2 a = screenPos[1] - screenPos[0];
	//vec2 b = screenPos[2] - screenPos[0];
	//vec3 clipSpaceNormal = cross(a, b);
	//vz = v1x * v2y - v1y * v2x
	float cz = sign(edge[0].y*edge[2].x - edge[0].x*edge[2].y);
    //if (cz < 0.0)
    //{
    //    edgeNormal[0] *= -1.0;
    //    edgeNormal[1] *= -1.0;
    //    edgeNormal[2] *= -1.0;
    //}
	edgeNormal[0] = normalize(vec2(-edge[0].y, edge[0].x))*cz;
	edgeNormal[1] = normalize(vec2(-edge[1].y, edge[1].x))*cz;
	edgeNormal[2] = normalize(vec2(-edge[2].y, edge[2].x))*cz;

	screenPos[0].xy = screenPos[0].xy - PixelDiagonal * (edge[2] / dot(edge[2], edgeNormal[0]) + edge[0] / dot(edge[0], edgeNormal[2]));
	screenPos[1].xy = screenPos[1].xy - PixelDiagonal * (edge[0] / dot(edge[0], edgeNormal[1]) + edge[1] / dot(edge[1], edgeNormal[0]));
	screenPos[2].xy = screenPos[2].xy - PixelDiagonal * (edge[1] / dot(edge[1], edgeNormal[2]) + edge[2] / dot(edge[2], edgeNormal[1]));
}
{% endhighlight %}

### All Projects
{: .t60 }

{% include list-posts.html tag='projects' %}