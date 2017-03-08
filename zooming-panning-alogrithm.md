# Zooming & Panning Algorithm
To provide the `panTo(node_id)` and `zoomOn(node_id)` methods, the exact node size and location relative to the container SVG document must be calculated.

## Single nodes
The location of a single node is easier. First a pan is applied then a zoom.

### Pan

1) Get the node size by calling `getBBox()` on the node. This returns the tight bounding box around the rectangular node. See [here](https://www.w3.org/TR/SVG/types.html#__svg__SVGLocatable__getBBox). It returns an [SVGRect](https://www.w3.org/TR/SVG/types.html#InterfaceSVGRect) **Note**: This would not work for any other shapes other than rectngle
2) Find the x,y coordinatees of the BBox. These are located on the top left corner
3) Find the center of the node by getting the BBox height and width and adding 1/2 width and 1/2 height to the x,y coordinates
4) Pan to this position

### Zoom
1) Find the longest side of the BBox (either its height or width)
2) Find the longest side of the container element (height or width)
3) Compute `containerLongSide / nodeLongSize`
4) Multiply by some scaling factor
5) Zoom by this amount

## Multiple nodes
The case of multiple nodes is a little trickier since need to find the point that is equidistant to all nodes.

### Pan
1) Compute the bounding box of all nodes by finding the lowest and highest x and y values. The lowest x and y values are the top left corner of the bounding box. 
The lowest x,y values are simply the lowest x,y values of the BBoxes of all nodes. The highest x,y values are the heighest value for the (x+width),(y+height) of all nodes.
Compute the width and height of the bounding box by `highest x - lowestx` and `highesty - lowesty`.

2) Follow as with single node

### Zoom
1) Do as with single node but using the bounding box of all nodes
