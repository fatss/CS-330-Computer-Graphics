# CS-330-Computational-Graphics

SNHU CS 330 Computational Graphics and Visualization Portfolio

This portfolio contains my final project, a 3D study desk scene built in C++
with OpenGL, GLFW, and GLM, along with the Design Decisions document that
explains how the scene was built and how a user navigates it.

## Files

```text
CS330_3D_Scene_Fatima_Imran.zip            Visual Studio project, source, shaders, and textures
CS330_Design_Decisions_Fatima_Imran.docx   Design decisions and development choices
```

## The Scene

The scene is a small study desk made entirely from basic shapes:

- **Tabletop:** a plane mesh with a tiled wood texture.
- **Desk lamp:** a cylinder base and arm, a sphere joint, and a cone shade,
  using metal and fabric textures.
- **Coffee mug:** a cylinder body with a torus handle.
- **Books:** two stacked box meshes in different colors.
- **Potted plant:** a tapered cylinder pot with sphere leaves.

Phong lighting from a warm point light gives the objects ambient, diffuse,
and specular shading, and each object has its own material settings.

## Controls

| Input        | Action                                  |
|--------------|-----------------------------------------|
| W / S        | Move forward / backward                 |
| A / D        | Move left / right                       |
| Q / E        | Move up / down                          |
| Mouse        | Look around                             |
| Scroll wheel | Change camera movement speed            |
| P / O        | Perspective / orthographic projection   |
| Esc          | Close the window                        |

## Reflection

### How do I approach designing software?

Working on this project taught me to design in layers. Before writing any
code, I made a scene proposal that broke each real-world object into simple
primitives. A lamp became a cylinder, a sphere, and a cone, and a plant
became a tapered cylinder with spheres for leaves. That habit of breaking a
complex thing into small, reusable pieces is the main design skill I built in
this course. I also learned to plan for the user, deciding early how someone
would move through the scene and why both perspective and orthographic views
were useful.

My design process followed the milestones. I started with a proposal and a
reference image, built one object at a time, then added textures, then
lighting, and finally camera navigation. Each stage had a clear goal I could
check before moving on. In future work I can use the same tactics: sketch the
structure first, identify the smallest reusable building blocks, and plan
the work so that each step produces something I can test.

### How do I approach developing programs?

The biggest new strategy I used was relying on helper functions instead of
repeating code. `SetTransformations()`, `SetShaderColor()`,
`SetShaderTexture()`, and `SetShaderMaterial()` let me place and style any
object with a few lines, and the same sphere mesh could be both a lamp joint
and a plant leaf. Keeping mesh loading in `PrepareScene()` separate from
drawing in `RenderScene()` made the code easier to follow and change.

Iteration was a constant part of development. I would change a scale,
position, or rotation value, rebuild, look at the result, and adjust again.
Some problems, like the plant pot not appearing and the leaves sitting too
low, only became clear after running the scene and viewing it from different
angles. Over the milestones my approach went from hard-coding one shape at a
time to working in small, tested increments. I commented each object block,
reused functions, and tested lighting and camera changes in the Windows
virtual environment before moving on. That steady cycle of build, test, and
refine is what got the project to completion.

### How can computer science help me in reaching my goals?

Computational graphics gave me a practical understanding of math I had only
seen on paper. Matrices, vectors, transformations, and coordinate spaces
became tools I used directly to position objects and move the camera. For my
education, this foundation will help in courses involving linear algebra,
simulation, game development, data visualization, and machine learning,
where the same ideas about vectors and transformations come up again.

Professionally, these skills apply to any field that presents information
visually, including game and app development, user interface work,
simulation, engineering tools, and data dashboards. Working with a real
graphics pipeline also taught me to read documentation, manage a project
with external libraries, debug visual problems that do not produce error
messages, and write organized, maintainable code. Those habits carry over to
any software role.
