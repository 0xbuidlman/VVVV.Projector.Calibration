# Introduction
Methods and tutorials for projection mapping 3D objects where a physical mesh of the object is available. It basically allows to retrieve the extrinsics and instrinsics parameters of a projector based on manually defined correspondences between the 3D scene (3D world points) and the projection space of the projector (2D points).

See also the [contribution page](http://vvvv.org/contribution/vvvv.tutorials.mapping.3d) of this tool for the DX11 version.

## CalibrateProjector

Using OpenCV's CalibrateCamera method to find the intrinsics and extrinsics of the projector (i.e. the projection and view matrices respectively).

### Inputs

* 7 or more World to Projection correspondences

### Controls
* S: Orbit
* D: Pan
* F: Zoom
* 1: Next point
* 2: Previous point
* Shift: Zoom to current point


### Prerequisites

* vvvv24.1+
* Elliot Woods' [VVVV.Packs.Image](http://vvvv.org/contribution/vvvv.packs.image) that wraps OpenCV (EmguCV)


### Notes

* Probably due to some misunderstandings from my part, I got the correct pose estimated with the following configurations:
	* Points in projective space (XY) converted to OpenCV's image coordinate using the node "MapNormalisedToCamera"
	* Input Space: pixels
	* Inside "CalibrateProjector": Coordinates: OpenCV
	* RTT the projector's renderer and rotate the texture by (0,0,0.5)