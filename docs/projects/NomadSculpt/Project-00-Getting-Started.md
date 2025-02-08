# Getting to Know Nomad Sculpt

![P0-01.png](https://github.com/beets3d/FutureMakers/blob/main/docs/projects/NomadSculpt/Images/P0-01.png)

## Welcome to Nomad!

Nomad is a 3D sculpting app that works best on tablets with a pressure sensitive stylus, 
eg an Apple iPad and pencil, or a Samsung Galaxy Tab with stylus.

It is inspired by desktop sculpting apps like Zbrush and Blender, with a focus on an easy to understand UI, without sacrificing on features. 
If you've used 3d sculpting apps before, Nomad will feel very familiar.

If this is your first time doing 3d sculpting, then it's good to know some basics.

## Your first sculpt

![P0-04.png](https://github.com/beets3d/FutureMakers/blob/main/docs/projects/NomadSculpt/Images/P0-04.png)

When you first start Nomad you'll see a sphere on screen. Simply drag your stylus on the sphere to start sculpting. 
Symmetry is enabled by default to make sculpting easier.

<img src="https://github.com/beets3d/FutureMakers/blob/main/docs/projects/NomadSculpt/Images/P0-02.png" alt="My Image" height="300"/><img src="https://github.com/beets3d/FutureMakers/blob/main/docs/projects/NomadSculpt/Images/P0-03.png" alt="My Image" height="300"/>

# Interface

![P0-05.png](https://github.com/beets3d/FutureMakers/blob/main/docs/projects/NomadSculpt/Images/P0-05.png)

## Nav Cube

A helper to show which side of the sculpt you're viewing, as well as a shortcut to jump to different views. 
Tapping the cube will jump the view to the tapped side. Dragging the cube will rotate. 
Tap the small icons next to the cube to frame the current object or reset to the default home view.

### Three Gestures to Control the View of Screen

<img src="https://github.com/beets3d/FutureMakers/blob/main/docs/projects/NomadSculpt/Images/P0-06.png" alt="My Image" height="200"/>Drag to Rotate
<img src="https://github.com/beets3d/FutureMakers/blob/main/docs/projects/NomadSculpt/Images/P0-07.png" alt="My Image" height="200"/>Swipe to Pan
<img src="https://github.com/beets3d/FutureMakers/blob/main/docs/projects/NomadSculpt/Images/P0-08.png" alt="My Image" height="200"/>Pinch to Zoom

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

![P0-09.png](https://github.com/beets3d/FutureMakers/blob/main/docs/projects/NomadSculpt/Images/P0-09.png)

### Top 3 icons

- Undo:     revert the last operation
- Redo:     restore the last undo operation
- History:  acccess history options, explained in the History menu

# Tools

![P0-09.png](https://github.com/beets3d/FutureMakers/blob/main/docs/projects/NomadSculpt/Images/P0-10.png)

## Overview

Nomad has many tools that can be broadly categorized as follows: 

- Brush tools that directly affect the surface of an object, eg Clay
- Mask tools that will protect the surface from changes, eg Mask
- Selection based tools where a 2d mask is drawn first, then an operation happens, eg Trim
- Special tools with their own interaction methods, eg Tube

Many of these tools can be customized with different brush behavior, pressure, textures etc via the Stroke menu.

## Tool controls

![P0-09.png](https://github.com/beets3d/FutureMakers/blob/main/docs/projects/NomadSculpt/Images/P0-11.png)

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

## ![P0-09.png](https://github.com/beets3d/FutureMakers/blob/main/docs/projects/NomadSculpt/Images/P0-12.png)

The Clay tool is useful for building up your sculpture. 

**Sub** will remove material from your sculpture.

![P0-09.png](https://github.com/beets3d/FutureMakers/blob/main/docs/projects/NomadSculpt/Images/P0-13.png)

### How Sub removes materials

![P0-09.png](https://github.com/beets3d/FutureMakers/blob/main/docs/projects/NomadSculpt/Images/P0-16.png)

## ![P0-09.png](https://github.com/beets3d/FutureMakers/blob/main/docs/projects/NomadSculpt/Images/P0-14.png)

The standard brush. 

**Sub** will remove material.

![P0-09.png](https://github.com/beets3d/FutureMakers/blob/main/docs/projects/NomadSculpt/Images/P0-15.png)

### How Sub removes materials

![P0-09.png](https://github.com/beets3d/FutureMakers/blob/main/docs/projects/NomadSculpt/Images/P0-17.png)

## ![P0-09.png](https://github.com/beets3d/FutureMakers/blob/main/docs/projects/NomadSculpt/Images/P0-18.png)

The area under the brush will stick to the brush, allowing for elastic deformation. The selection is maintained during the move, so if you move the brush away, then move it back where you started, you will see no deformation. 

**Normal** will move the area under the brush along the surface normal.

![P0-09.png](https://github.com/beets3d/FutureMakers/blob/main/docs/projects/NomadSculpt/Images/P0-19.png)

### How Normal moves

![P0-09.png](https://github.com/beets3d/FutureMakers/blob/main/docs/projects/NomadSculpt/Images/P0-20.png)

## ![P0-09.png](https://github.com/beets3d/FutureMakers/blob/main/docs/projects/NomadSculpt/Images/P0-21.png)

The area under the brush will stick to the brush, allowing for elastic deformation. Unlike the move brush, the selection is continuously updated during the stroke, so it is possible to make longer, snake like objects, especially when Dynamic Topology is activated. 

**Normal** will move the area under the brush along the surface normal.

![P0-09.png](https://github.com/beets3d/FutureMakers/blob/main/docs/projects/NomadSculpt/Images/P0-22.png)

### How Normal moves

![P0-09.png](https://github.com/beets3d/FutureMakers/blob/main/docs/projects/NomadSculpt/Images/P0-23.png)

## ![P0-09.png](https://github.com/beets3d/FutureMakers/blob/main/docs/projects/NomadSculpt/Images/P0-24.png)

Smooth the area by average the point positions. This tool is highly dependent on the polygon density. So if you have many polygons, the smoothing will be less effective.

The alternate mode is the **Relax** mode, which only smooths the wireframe but tries to retain the geometric details.

![P0-09.png](https://github.com/beets3d/FutureMakers/blob/main/docs/projects/NomadSculpt/Images/P0-25.jpeg)

### Smooth settings

![P0-09.png](https://github.com/beets3d/FutureMakers/blob/main/docs/projects/NomadSculpt/Images/P0-26.png)

- #### Sticky vertex on border

For meshes with open edges, eg a plane, it is possible to smooth out the corners. Enabling this option will lock the open edges.

- #### Relax

The same as the relax alternate mode in the left-hand toolbar.

- #### Stable Smoothing

Tries to make the smoothing topology independent. This works best with varying topology density and with a high smoothing intensity value.

##### TIP

Higher polygon densities can require raising the intensity above 100%. Very high   values (300%, 500%) can also work well as a sculpting tool, forcing areas to go flat and smooth quickly under the brush, like hitting clay with a mallet!

## ![P0-09.png](https://github.com/beets3d/FutureMakers/blob/main/docs/projects/NomadSculpt/Images/P0-27.png)

This tool lets you mask points. Masked vertices can't be sculpted or painted afterwards, this is a way to "protect" areas. 

**Unmask** will erase where the mask has been painted.

![P0-09.png](https://github.com/beets3d/FutureMakers/blob/main/docs/projects/NomadSculpt/Images/P0-28.jpeg)

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

- ### Thickness
  
  The distance of the extraction. Use the ± button to set the distance to be positive, negative, or centered from the surface.

- ### Smoothness
  
  Will smooth the border of the extracted shape, it works better with higher polygon counts.
  
- ### Extract
  
  In default mode 'shell' mode, behave like an extrude in other 3d apps, pulling the mask section out from the surface.
  
- ### Split
  
  Will extract the masked region into a new shape, but also apply an operation to the unmasked region. By default ths operation is   'shell', resulting in a fat extruded mask and a matching unmasked shape.
  
- ### Carve
  
  In default mode, behave a if you had trimmed into the surface by the 'thickness' amount, like cutting a section of orange peel.

