<div align="center">

# Four Cubes

**Four textured dice spinning in real-time OpenGL. Grab the scene with your mouse, flick it, and watch it keep turning.**

![C++](https://img.shields.io/badge/C%2B%2B-17-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![Qt](https://img.shields.io/badge/Qt-6.6-41CD52?style=flat-square&logo=qt&logoColor=white)
![OpenGL](https://img.shields.io/badge/OpenGL-GLSL%20Shaders-5586A4?style=flat-square&logo=opengl&logoColor=white)

<img src="docs/screenshots/four-cubes.jpg" width="640" alt="Four textured dice rotating" />

</div>

---

## What it does

A compact real-time 3D graphics demo. Four independently positioned cubes, one in each quadrant, are drawn with vertex and fragment shaders and a texture-mapped die face on every side. Click and drag to set a spin: the drag direction becomes the rotation axis, the drag length sets the speed, and the cubes keep turning under **quaternion-based momentum** that slowly decays.

## Highlights

- **GPU rendering** with `QOpenGLWidget`, vertex buffers built by a reusable `GeometryEngine`, and GLSL shaders compiled at runtime.
- **Texture mapping:** one image wrapped across all six faces of each cube.
- **Quaternion rotation**, which avoids gimbal lock and gives smooth, continuous spinning.
- **Inertia:** each mouse flick adds angular velocity, and friction slows it frame by frame.
- **Multiple instances:** a `TextureCube` class encapsulates position, rotation and drawing, so the scene is four objects rather than four copies of code.

## How it works

```
main.cpp            → sets up a 24-bit depth buffer and shows MainWidget
main_widget.*       → mouse input, rotation axis/speed, timer-driven animation, four TextureCubes
texture_cube.*      → per-cube model matrix (translate + rotate), shader and texture binding
geometryengine.*    → cube vertex/index buffers (positions + texture coordinates)
vshader.glsl        → model-view-projection transform
fshader.glsl        → texture sampling
```

## Build and run

Open `four_cubes_anti.pro` in **Qt Creator** (Qt 6) and press **Run**, or:

```sh
qmake four_cubes_anti.pro && make
```

## Credits

Built by **Roszhan Raj** for CSUF computer graphics coursework. It extends Qt's official *Cube OpenGL ES 2.0* example (BSD license); the original notices are kept in the source files.
