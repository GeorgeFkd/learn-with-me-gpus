# learn-with-me-gpus
This is a repository where i document my journey into learning about GPUs
What i will study can be seen below and i will try to also write brief explanations about those to enhance the learning experience of others from this repository.
## Table of Contents
- [ ] GPU architecture
  - https://medium.com/codex/understanding-the-architecture-of-a-gpu-d5d2d2e8978b
- [ ] Graphics Pipeline
  -  https://en.wikipedia.org/wiki/Graphics_pipeline
  -  https://graphics.stanford.edu/courses/cs448a-01-fall/lectures/lecture2/gpipeline.2up.pdf
  -  https://www.cs.cornell.edu/courses/cs4620/2020fa/slides/11pipeline.pdf
- [ ] Shaders
- [ ] Anti-Aliasing
- [ ] Ray Tracing
- [ ] SIMT(Single Instruction Multiple Threads)
- [ ] GPU Programming Tools
  - AMD's ROCm (AMD's CUDA Alternative)
  - OpenGL
    - https://graphics.stanford.edu/courses/cs448a-01-fall/design_opengl.pdf


## GPU Project 
All of this knowledge amassed above is unrealistic to fit in a single project.

For starters i want to implement a simple LED sign where the user can input some kind of text and it will be displayed in that way.
I want to make it cross-platform to sharpen my skills but one platform only is ok.
The features i will aim for are:
- Custom Thing Displayed(Not something static)
- Cycle through multiple things to be displayed (with an animation if it is doable, a continuous movement)
- Allow customisation from the user(choose colors, construct "animations"/sequences of stuff to be displayed)
- Allow realtime control of it(display text X for Y time)
