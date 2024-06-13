# learn-with-me-gpus
This is a repository where i document my journey into learning about GPUs
What i will study can be seen below and i will try to also write brief explanations about those to enhance the learning experience of others from this repository.

Found this course material: [Stanford Graphics Course](http://www.graphics.stanford.edu/courses/cs448a-01-fall/)

## Table of Contents
- [ ] GPU architecture
  - https://medium.com/codex/understanding-the-architecture-of-a-gpu-d5d2d2e8978b --> Not a very good article, too vague and general
  - https://www.amd.com/system/files/documents/rdna-whitepaper.pdf --> tough read, haven't read it yet 
- [ ] Graphics Pipeline
  -  https://en.wikipedia.org/wiki/Graphics_pipeline (read, without diving deep into the geometry stuff)
  -  https://graphics.stanford.edu/courses/cs448a-01-fall/lectures/lecture2/gpipeline.2up.pdf (read, really general but it gives lots of terms to look up)
  -  https://www.cs.cornell.edu/courses/cs4620/2020fa/slides/11pipeline.pdf
- [ ] Shaders
- [ ] Anti-Aliasing
- [ ] Ray Tracing
- [ ] Vulkan
- [ ] Understand common graphics teriminology(DPI,HDPI etc. etc.)
- [ ] SIMT(Single Instruction Multiple Threads)
- [ ] GPU Programming Tools
  - AMD's ROCm (AMD's CUDA Alternative)
  - OpenGL(+GLSL)
    - https://graphics.stanford.edu/courses/cs448a-01-fall/design_opengl.pdf
    - https://learnopengl.com/Getting-started/OpenGL


## GPU Project 
All of this knowledge amassed above is unrealistic to fit in a single project.

For starters i want to implement a simple LED sign where the user can input some kind of text and it will be displayed in that way.
I want to make it cross-platform to sharpen my skills but one platform only is ok(preferrably Web to be able to publish it).
The features i will aim for are:
- Custom Thing Displayed(Not something static)
- Cycle through multiple things to be displayed (with an animation if it is doable, a continuous movement)
- Allow customisation from the user(choose colors, construct "animations"/sequences of stuff to be displayed)
- Implement RGB Keyboard stuff (changing smoothly colors, cycling colors in a fun way to form a wave for example etc. etc.)


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

Terms to study:
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
