# Getting to Know Nomad Sculpt

![p0-01.png](images/p0-01.png)

## Welcome to Nomad!

Nomad is a 3D sculpting app that works best on tablets with a pressure sensitive stylus, 
eg an Apple iPad and pencil, or a Samsung Galaxy Tab with stylus.

It is inspired by desktop sculpting apps like Zbrush and Blender, with a focus on an easy to understand UI, without sacrificing on features. 
If you've used 3d sculpting apps before, Nomad will feel very familiar.

If this is your first time doing 3d sculpting, then it's good to know some basics.

## Your first sculpt

![p0-04.png](images/p0-04.png)

When you first start Nomad you'll see a sphere on screen. Simply drag your stylus on the sphere to start sculpting. 
Symmetry is enabled by default to make sculpting easier.

<img src="images/p0-02.png" alt="My Image" height="300"/><img src="images/p0-03.png" alt="My Image" height="300"/>

# Interface

![p0-05.png](images/p0-05.png)

## Nav Cube

A helper to show which side of the sculpt you're viewing, as well as a shortcut to jump to different views. 
Tapping the cube will jump the view to the tapped side. Dragging the cube will rotate. 
Tap the small icons next to the cube to frame the current object or reset to the default home view.

### Three Gestures to Control the View of Screen

<img src="images/p0-06.png" alt="My Image" height="200"/>Drag to Rotate
<img src="images/p0-07.png" alt="My Image" height="200"/>Swipe to Pan
<img src="images/p0-08.png" alt="My Image" height="200"/>Pinch to Zoom

## Top menus

The menus in Nomad give you access to most of its features. The top-left menus mainly cover scene and object features, while the top-right menus are related to tools. On smaller screens, these menus will collapse together to save space. 

### Stats
This section provides information about the scene, the current object, mask status, and memory usage.

## Left toolbar
Sliders for radius and intensity for most tools, context-specific buttons for other tools, and shortcuts for symmetry, the tool alt/sub mode, masking, smoothing, the gizmo, and paint options.

## Bottom toolbar
Shortcuts for commonly used features are explained below.

## Toolbox

Nomad's tools are accessible from this scrollable region.

![p0-09.png](images/p0-09.png)

### Top 3 icons

- Undo:     revert the last operation
- Redo:     restore the last undo operation
- History:  acccess history options, explained in the History menu

# Tools

![p0-10.png](images/p0-10.png)

## Overview

Nomad has many tools that can be broadly categorized as follows: 

- Brush tools that directly affect the surface of an object, eg Clay
- Mask tools that will protect the surface from changes, eg Mask
- Selection based tools where a 2d mask is drawn first, then an operation happens, eg Trim
- Special tools with their own interaction methods, eg Tube

Many of these tools can be customized with different brush behavior, pressure, textures etc via the Stroke menu.

## Tool controls

![p0-11.png](images/p0-11.png)

The panel on the left side of the screen controls the tool radius and intensity, and hotkeys specific to certain tools, explained in each tool's help section below.

### TIP

The intensity slider for many tools can go above 100%, worth experimenting with!

## Tool context menu 

A right click or long press on a tool will bring up a context menu. 

This menu has the following options:

- Save:       save any changes you made to the tool 
- Clone:      duplicate the tool into a new tool shortcut
- Last save:  revert to the previously saved version of the tool
- Icon:       change the icon for the tool 
- Reset:      reset the tool to its defaults

# Common Sculpting Tools

## ![p0-12.png](images/p0-12.png)

The Clay tool is useful for building up your sculpture. 

**Sub** will remove material from your sculpture.

![p0-13.png](images/p0-13.png)

### How Sub removes materials

![p0-16.png](images/p0-16.png)

## ![p0-14.png](images/p0-14.png)

The standard brush. 

**Sub** will remove material.

![p0-15.png](images/p0-15.png)

### How Sub removes materials

![p0-17.png](images/p0-17.png)

## ![p0-18.png](images/p0-18.png)

The area under the brush will stick to the brush, allowing for elastic deformation. The selection is maintained during the move, so if you move the brush away, then move it back where you started, you will see no deformation. 

**Normal** will move the area under the brush along the surface normal.

![p0-19.png](images/p0-19.png)

### How Normal moves

![p0-20.png](images/p0-20.png)

## ![p0-21.png](images/p0-21.png)

The area under the brush will stick to the brush, allowing for elastic deformation. Unlike the move brush, the selection is continuously updated during the stroke, so it is possible to make longer, snake like objects, especially when Dynamic Topology is activated. 

**Normal** will move the area under the brush along the surface normal.

![p0-22.png](images/p0-22.png)

### How Normal moves

![p0-23.png](images/p0-23.png)

## ![p0-24.png](images/p0-24.png)

Smooth the area by average the point positions. This tool is highly dependent on the polygon density. So if you have many polygons, the smoothing will be less effective.

The alternate mode is the **Relax** mode, which only smooths the wireframe but tries to retain the geometric details.

![p0-25.jpeg](images/p0-25.jpeg)

### Smooth settings

![p0-26.png](images/p0-26.png)

- #### Sticky vertex on border

For meshes with open edges, eg a plane, it is possible to smooth out the corners. Enabling this option will lock the open edges.

- #### Relax

The same as the relax alternate mode in the left-hand toolbar.

- #### Stable Smoothing

Tries to make the smoothing topology independent. This works best with varying topology density and with a high smoothing intensity value.

##### TIP

Higher polygon densities can require raising the intensity above 100%. Very high   values (300%, 500%) can also work well as a sculpting tool, forcing areas to go flat and smooth quickly under the brush, like hitting clay with a mallet!

## ![p0-27.png](images/p0-27.png)

This tool lets you mask points. Masked vertices can't be sculpted or painted afterwards, this is a way to "protect" areas. 

**Unmask** will erase where the mask has been painted.

![p0-28.png](images/p0-28.png)

### Mask settings

A toolbar will appear at the top of the viewport with extra controls:

- Clear：   Clear the mask					
- Invert：  Invert the mask
- Blur：    Blur the mask edge				
- Sharpen： Sharpen the mask edge

#### Quick gesture

4 gestures while holding the quick masking button:

- Clear：   Drag on the background
- Invert：  Tap on the background			
- Blur：    Tap on masked area				
- Sharpen： Tap on unmasked area

Masks can also be used to extract geometry. The **Carve**, **Extract** and **Split** buttons will create new shapes from the masked region. The following settings offer more control:

- #### Thickness
  
  The distance of the extraction. Use the ± button to set the distance to be positive, negative, or centered from the surface.

- #### Smoothness
  
  Will smooth the border of the extracted shape, it works better with higher polygon counts.
  
- #### Extract
  
  In default mode 'shell' mode, behave like an extrude in other 3d apps, pulling the mask section out from the surface.
  
- #### Split
  
  Will extract the masked region into a new shape, but also apply an operation to the unmasked region. By default ths operation is   'shell', resulting in a fat extruded mask and a matching unmasked shape.
  
- #### Carve
  
  In default mode, behave a if you had trimmed into the surface by the 'thickness' amount, like cutting a section of orange peel.

## ![p0-29.png](images/p0-29.png)

This tool is mostly similar to the **Masking tool**, the main difference is that you don't use stroke to paint mask, but instead use the **shape selector**.

Selector mask shares the same tool settings as the **Mask** tool.

![p0-30.png](images/p0-30.png)

### Shape selector

![p0-31.png](images/p0-31.png)

The **Trim**, **Split**, **Project**, **Facegroup** and **Hide** tools all use similar controls for selecting areas of the mesh, and are chosen with the shape selector panel on the left of the screen.

- #### Lasso
A freehand drawn shape

- #### Polygon
An enclosed shape defined by a combination of curves and/or straight lines. See **Shape editing** below for more info.

- #### Curve		(Project only) 
A freehand curve for the projection

- #### Path		(Project only)
A curve defined by points. See **Shape editing** below for more info.

- #### Line
Drag a line to define a planar segment. By default it will operate on the mesh immediately, turn off auto validate if you don't want this (long press or swipe on the line icon)

- #### Rect
Drag a diagonal line, this will define the corners of a rectangle shape. Long press or swipe to reveal options for auto validate, force to a square shape, and for the first click to be the center of the rectangle.

- #### Ellipse
Drag a diagonal line, this will define the size of an ellipse. Long press or swipe to reveal options for auto validate, force to a circle shape, and for the the first click to be the center of the ellipse.

- #### Flip
Invert the shape mask, or the direction of the project tool.

### Shape editing

Polygon editing and curve editing behave in similar ways:

To start, drag a line to define 2 points, then drag out from the middle of the line to define a polygon or curve. Click on the points to toggle between smooth and sharp. Click and drag on the curve or line sections to create new points.To delete a point, drag a point into its neighbor until it turns red. The trash icon in the corner of the polygon or path icon will delete the shape.
