# Four Cubes — Qt OpenGL

A Qt 6 / OpenGL demo that renders four textured cubes with GLSL shaders. Drag with the mouse to spin the scene; rotation is tracked with quaternions and continues with momentum after release.

Built for CSUF's computer graphics coursework, extending Qt's official *Cube OpenGL ES 2.0* example (BSD license; notices kept in the source files).

## Build

Open `four_cubes_anti.pro` in Qt Creator (Qt 6.6) and run, or:

```sh
qmake four_cubes_anti.pro && make
```
