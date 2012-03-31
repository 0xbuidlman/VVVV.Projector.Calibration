# Introduction
Methods and tutorials for projection mapping 3D objects where a physical mesh of the object is available. In the tutorials we use ReconstructMe to create a mesh using a kinect to 3D scan a scene (http://reconstructme.net).

# Methods

## CalibrateProjector

Using OpenCV's CalibrateCamera method to find the intrinsics and extrinsics of the projector (i.e. the projection and view matrices respectively).

### Inputs

* 7 or more World to Projection correspondences

### Prerequisites

* vvvv24.1
* OpenCV plugins (available at http://vvvv.org/contribution/opencv-plugin-%28alpha%29 )

## Homography + Position

Homography and an arbitrary perspective are used to define the Projection matrix and the rotation element of the View matrix. This leaves 1 unknown (projector position) which can then be rapidly tweaked into position by the user

### Inputs

* 4 * World to Projection correspondences
* 3D position of projector (easy to tweak when 4 correspondences are locked)

### Prerequisites

* None (works with native vvvv24.1 and modules here)

