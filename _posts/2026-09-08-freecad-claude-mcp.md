---
layout: post
title: "Designing 3D prints with Claude and FreeCAD"
date: 2026-09-08 10:00:00 +0530
categories: [blog]
---

I've recently acquired a 3D printer and use [FreeCAD](https://www.freecad.org/) to design parts to print. I built an MCP server to drive FreeCAD via Claude Code. It's a collection of tools that use built-in FreeCAD capabilities to design parts.

**Code:** [GitHub Repo](https://github.com/aakashsbhatia2/claude-freecad-mcp)

It's very straightforward to install, a guide can be found [here](https://github.com/aakashsbhatia2/claude-freecad-mcp/blob/main/INSTALL.md). Once installed, you can:
- Design parts with Claude Code directly in FreeCAD open on your computer
- Select faces/edges and ask Claude to update them
- Export in 3MF/STL format
- Create artifacts for the designs with Claude Code, including views from 3 planes (XY, YZ, XZ), dimensions etc.

### Considerations
- Plugin should be installed locally in the folder you plan to save your models. To keep results predictable and prevent Claude from writing Python scripts to build designs, I have blocked bash commands while the plugin is running
- I've found discussing the design and creating artifacts to map out all the dimensions before creating the designs in FreeCAD very helpful

### Some 3D printable models I created using my MCP server

**Wall-mounted deodorizer holder**

This holds a standard OdoBan deodorizer. It can be wall-mounted in each room in the house. It's three parts, and for each one below you'll see the print, the artifact Claude created for the design specs, and the model it generated in FreeCAD.

*Sleeve* - This holds the deodorizer tub. The T-shaped mount on the back slides into the wall mount.

![Fluted black sleeve holding a deodorizer puck]({{ site.baseurl }}/assets/images/deodorizer-sleeve.jpg)

![Sleeve dimension sheet with top, side and bottom views]({{ site.baseurl }}/assets/images/deodorizer-sleeve-artifact.png)

![Sleeve model in FreeCAD with its ribbed polar pattern]({{ site.baseurl }}/assets/images/deodorizer-sleeve-FreeCAD-design.png)

*Lid* - A vented cap to cover the sleeve. This is optional but makes things look better.

![Brown lid with a hexagonal vent pattern]({{ site.baseurl }}/assets/images/deodorizer-lid.jpg)

![Lid dimension sheet with top, side and bottom views]({{ site.baseurl }}/assets/images/deodorizer-lid-artifact.png)

![Lid model in FreeCAD with hexagonal vent cutouts]({{ site.baseurl }}/assets/images/deodorizer-lid-FreeCAD-design.png)

*Wall mount* - Screws into the wall with two screws.

![Brown wall bracket with screw holes and a sliding rail]({{ site.baseurl }}/assets/images/wall-bracket.jpg)

![Wall mount dimension sheet with top, slot detail, side and bottom views]({{ site.baseurl }}/assets/images/deodorizer-wallmount-artifact.png)

![Wall mount model in FreeCAD showing the tongue slot and screw hole]({{ site.baseurl }}/assets/images/deodorizer-wallmount-FreeCAD-design.png)

*All together* - The sleeve slides down onto the mount and the lid goes on top:

![Deodorizer holder with lid mounted on the wall bracket]({{ site.baseurl }}/assets/images/deodorizer-wallmounted.jpg)

**Spatula drip tray**

A drip tray to hold a used spatula while cooking

![Blue drip tray holding a spatula on a kitchen counter]({{ site.baseurl }}/assets/images/spatula-drip-tray.jpg)

 

