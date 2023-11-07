---
author: "Mike Wilding"
date: "2022-02-28 20:03:22"
title: "Artist tool for point-cache simulation "
description: "I developed a tool allowing artists to manipulate 3d simulation data"
draft: false
weight: 2
---

### Crowd Sim Point Cache Manager


The episode needed repeated crowd simulations of upwards of 500 “delegate” rats, whose behaviours needed to be altered en-masse by artists according to the needs of the art direction.

<!--more-->

- The pipeline called for a handful of rat meshes to be modeled with from a base, and animated in a number of ways, being reduced to a point-cache for 1 one of 7 different run or walk loops.
- The tool programmatically tied the speed and rotation of the (parent)delegate to the (child)point cache animated rat mesh.
- an artist could deselect a random percentage of the rats based on an initial visual selection. The selection could be further filtered based on various properties of the child nodes.

This was done for 
**Grimm - Bent Image Lab - Seas 1 Ep 5 - (NBC)**