# learn-with-me-gpus
This is a repository where i document my journey into learning about GPUs
What i will study can be seen below and i will try to also write brief explanations about those to enhance the learning experience of others from this repository.

Found this course material: [Stanford Graphics Course](http://www.graphics.stanford.edu/courses/cs448a-01-fall/)

## Table of Contents
- [ ] GPU architecture (i don't feel like i have read enough on the topic yet)
  - https://medium.com/codex/understanding-the-architecture-of-a-gpu-d5d2d2e8978b --> Not a very good article, too vague and general
  - https://www.amd.com/system/files/documents/rdna-whitepaper.pdf --> tough read, haven't read it yet 
- [X] Graphics Pipeline (i could read a bit more in depth for the separate steps)
  -  https://en.wikipedia.org/wiki/Graphics_pipeline (read, without diving deep into the geometry stuff)
  -  https://graphics.stanford.edu/courses/cs448a-01-fall/lectures/lecture2/gpipeline.2up.pdf (read, really general but it gives lots of terms to look up,also it is a bit old)
  -  https://www.cs.cornell.edu/courses/cs4620/2020fa/slides/11pipeline.pdf (read, good information, dives a bit deeper and does not just have pictures and bullet-points, gives an overview of some algorithms that I will not read as i will probably learn those in my master's).
- [X] Shaders (found this site -> https://thebookofshaders.com/01/ , that seems to have many posts for shaders, seems to be a quality resource and also has code examples, i will read it when i start coding)
- [X] Anti-Aliasing (from wikipedia: aliasing is a phenomenon from signals processing that seems to apply to graphics too, tldr: pixels rectangular,IRL objects curvy, so problem occurs and we gotta write algorithms to solve it, e.g. supersampling)
- [X] Ray Tracing (wikipedia has a good article on it with lots of stuff, tldr: calculates how light will bounce given the positions/angles(probably in the form of vectors) of the light, the sphere, and the camera
- [X] Vulkan (seems to be a bit newer, and openGL a bit older,[reddit post](https://www.reddit.com/r/vulkan/comments/77j2sz/when_to_use_vulkan_vs_opengl/), [stack exchange post](https://www.reddit.com/r/vulkan/comments/77j2sz/when_to_use_vulkan_vs_opengl/), tldr: vulkan is really low-level giving all the control to the developer and openGL is more high level)
- [ ] Understand common graphics teriminology(DPI,HDPI etc. etc.)
- [ ] SIMT(Single Instruction Multiple Threads)
- [ ] GPU Programming Tools
  - AMD's ROCm (AMD's CUDA Alternative)
  - OpenGL(+GLSL)
    - https://graphics.stanford.edu/courses/cs448a-01-fall/design_opengl.pdf
    - https://learnopengl.com/Getting-started/OpenGL
    - https://openglbook.com/chapter-0-preface-what-is-opengl.html


## GPU Project 
All of this knowledge amassed above is unrealistic to fit in a single project.

For starters i want to implement a simple LED sign where the user can input some kind of text and it will be displayed in that way.
I want to make it cross-platform to sharpen my skills but one platform only is ok(preferrably Web to be able to publish it).
The features i will aim for are:
- Custom Thing Displayed(Not something static)
- Cycle through multiple things to be displayed (with an animation if it is doable, a continuous movement)
- Allow customisation from the user(choose colors, construct "animations"/sequences of stuff to be displayed)
- Implement RGB Keyboard stuff (changing smoothly colors, cycling colors in a fun way to form a wave for example etc. etc.)

## GPU Tools
- GLSL Viewer in https://github.com/patriciogonzalezvivo/glslViewer
- 
## GPU Architecture notes

A CPU is smarter than a GPU,which means it can do smart things for optimisation like **out-of-order-execution**, **branch-prediction**, **speculative execution**.
But as they evolve, GPUs can do smarter things.

From the medium article above:
> It is worth adding that the GPU programming model is SIMD (Single Instruction Multiple Data) meaning that all the cores execute exactly the same operation, but over different data. Evidently, the strenght of a GPU is not much in the processing capabilities of the cores, but in their massive parallelism.


## GPU Graphics Pipelines
Graphics Pipeline is the process a 3D scene undergoes to be converted to a 2D scene and painted to the screen.
> a universally applicable graphics pipeline does not exist
> 
Direct3D, OpenGL and Vulkan were developed to standardize common procedures and oversee the graphics pipeline of a given hardware accelerator.
The term "pipeline" is used in a similar sense for the pipeline in processors: the individual steps of the pipeline run in parallel as long as any given step has what it needs.
There is also a Geometry Pipeline --> Model & Camera > Lighting > Projection > Clipping > Window-Viewport transformation (device coordinates).
Application > Geometry > Rasterization > Screen
In Rasterization, discrete fragments are created from continuous primitives

In the pipeline for shading we can control the vertex shader and the fragment shader, the rest are implemented from the providers.

Terms to study or just know:
- [Embarassingly Parallel](https://en.wikipedia.org/wiki/Embarrassingly_parallel)
- [Reduction Operator](https://en.wikipedia.org/wiki/Reduction_operator)
- Texture
- Fragment
- Antialiasing
- Shading
- Gamma Correction
- OpenGL Architecture
- [Streaming Multiprocessors](https://medium.com/@yunjiangster/understanding-streaming-multiprocessors-sm-blocks-threads-and-warps-in-cuda-programming-7e763c7d2563)
- [World Coordinate System](wikipedia)
- Hidden surface elimination
- Back face culling
- Painter's algorithm
- Z buffer/Z sort
- Gouraud and Phong Shading

## Qt and OpenGL
Previous knowledge of OpenGL is required in order to use it in Qt. The basic concepts and techniques should be enough though.  

[Qt Docs](https://doc.qt.io/qt-6/qtopengl-index.html)
The `QOpenGLWidget` Class is used to get the functionality for required to do OpenGL stuff in a Qt Widget by inheriting from that class. The 3 main methods are paintGL,resizeGL,initializeGL that each has its respective use case. 
There is also a `QOpenGLFunctions` instance(doing `QOpenGLContext::currentContext()->functions();` where the methods for opengl can be found, instead of calling them directly.

There is also a `QSurfaceFormat` Qt Class that can be helpful in this scenario.
Qt also provides wrapper classes for common openGL things suchs as shaders, textures, buffers and VertexArrayObjects.


