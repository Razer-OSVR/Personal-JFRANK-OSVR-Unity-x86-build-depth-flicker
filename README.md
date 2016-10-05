# Depth Flicker Reproduction
This repository contains a simple Unity3D scene to demonstrate a rendering bug that appears to be within OSVR.  This error only occurs in 32-bit builds of this project (as verified with an HDK2 with no camera plugged in and configuration set to 3DOF only).  It does not occur with the Unity SteamVR plugin and Vive.

Take a look at the cube that's clipping through the ground.  The rendering error manifests as a flickering between the part of that cube that should be occluded by the ground plane and the ground that should occlude it.  This is only visible in the left HMD display.

The directional light is not necessary to reproduce the error, but it makes it easier to see.  If you set the ground object's material to be the material provided with global illumination disabled (`Ground without GI - less flicker`), the flicker is less frequent, but still occurs.

If you remove the floating cube, the problem does not appear.  If you rotate the clipping cube sufficiently, the problem also does not appear.

Obviously something odd is going on with the depth buffer...
