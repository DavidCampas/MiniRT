# MiniRT

A minimalistic ray tracer written in C that parses `.rt` scene files and renders 3D scenes with lighting and shadows using the MLX42 graphics library.

![C](https://img.shields.io/badge/C-00599C?logo=c&logoColor=white)
![MLX42](https://img.shields.io/badge/MLX42-graphics-5C4EE5)
![42 Barcelona](https://img.shields.io/badge/42-Barcelona-000000?logo=42&logoColor=white)

## About

MiniRT is a Common Core project at 42 that builds a ray tracer from scratch. It reads a plain-text `.rt` file describing a camera, lights and simple geometric primitives, then casts rays through each pixel to produce a rendered image. The project demonstrates the fundamentals of computer graphics: vector math, ray-object intersection, the Phong-style lighting model and shadow computation, all in a memory-safe, Norm-compliant C codebase. It was developed by Ernest Balañá and David Campas.

## Features

- Parses `.rt` scene files with validation and clear error messages
- Supported elements: **A** ambient light, **C** camera (with FOV), **L** point light, **sp** sphere, **pl** plane, **cy** cylinder
- Ray-object intersection for spheres, planes and cylinders
- Diffuse lighting with ambient term and hard shadows
- Progressive, row-by-row rendering into an MLX42 window
- `ESC` closes the window; clean resource teardown on exit
- Custom vector-math utilities and a `libft`-based helper library

## Build & run

MLX42 and `ultimate_libft` are bundled as submodules and built automatically by the Makefile (requires `cmake`, `glfw` and a C toolchain).

```bash
# Clone with submodules
git clone --recursive https://github.com/DavidCampas/MiniRT.git
cd MiniRT

# Build (compiles MLX42, libft and the miniRT binary)
make

# Render a scene
./miniRT scene/subject.rt

# Try the bundled example scenes
./miniRT scene/sphere.rt
./miniRT scene/cylinder.rt

# Clean up
make clean    # remove object files
make fclean   # remove objects and binaries
make re       # rebuild from scratch
```

Scene files live in the `scene/` directory. A minimal scene defines ambient light, a camera, at least one light and at least one object:

```
A  0.2                255,255,255
C  -50,0,20  0,0,1    70
L  -40,0,30           0.7  255,255,255
sp 0,0,20             20   255,0,0
```

## Concepts

C · ray tracing · vector math · ray-object intersection · lighting & shadows · MLX42 / OpenGL · Makefile & CMake · memory management · 42 Norm

_42 Barcelona · Common Core project._
