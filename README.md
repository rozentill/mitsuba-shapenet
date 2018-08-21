<<<<<<< HEAD
# mitsuba-shapenet

Most ShapeNet models are exported from SketchUp with double-faces. In original Mitsuba renderer without back-face culling, there are black pixels when intersecting the 'back side' face. There are also some categories, such as cars, are not double-sided. Some of them only have flipped faces, which makes backface culling not work.

This fork simply implements a 'shapenet' shape importer. It reads model and material from ShapeNet .obj files and assign them with proper 'twosided' BSDF.

For more details about mitsuba renderer, please visit its homepage at https://www.mitsuba-renderer.org/ .

And for the dependency of the project, please check https://www.mitsuba-renderer.org/repos/ .

On Windows, you can simply put the dependencies_windows repo under the project folder and rename it as mitsuba-shapenet\dependencies. It would automatically find required headers and libraries.

If you meet the problem of missing header such as mitsuba_precompiled_header.hpp, please turn off MTS_USE_PCH flag during CMake.

Currently it cannot handle per-vertex normal or smooth group in ShapeNet obj. You can use 'maxSmoothAngle' to add some smoothness rendering effect.

#### Samples

Rendering scripts and results can be found [here](shapenet). Images rendered with this ShapeNet importer(left) and Mitsuba OBJ importer(right):

![alt text](shapenet/sample-car-shapenet.png "ShapeNet importer")
![alt text](shapenet/sample-car-obj.png "Mitsuba OBJ importer")

![alt text](shapenet/sample-chair-shapenet.png "ShapeNet importer")
![alt text](shapenet/sample-chair-obj.png "Mitsuba OBJ importer")

#### Download

A compiled Windows x64 DLL can be downloaded [here](http://share.shijian.org.cn/shapenet/render/shapenet.dll) . Please put it under 'plugins' folder.
=======
Mitsuba — Physically Based Renderer
===================================

http://mitsuba-renderer.org/

## About

Mitsuba is a research-oriented rendering system in the style of PBRT, from which it derives much inspiration. It is written in portable C++, implements unbiased as well as biased techniques, and contains heavy optimizations targeted towards current CPU architectures. Mitsuba is extremely modular: it consists of a small set of core libraries and over 100 different plugins that implement functionality ranging from materials and light sources to complete rendering algorithms.

In comparison to other open source renderers, Mitsuba places a strong emphasis on experimental rendering techniques, such as path-based formulations of Metropolis Light Transport and volumetric modeling approaches. Thus, it may be of genuine interest to those who would like to experiment with such techniques that haven't yet found their way into mainstream renderers, and it also provides a solid foundation for research in this domain.

The renderer currently runs on Linux, MacOS X and Microsoft Windows and makes use of SSE2 optimizations on x86 and x86_64 platforms. So far, its main use has been as a testbed for algorithm development in computer graphics, but there are many other interesting applications.

Mitsuba comes with a command-line interface as well as a graphical frontend to interactively explore scenes. While navigating, a rough preview is shown that becomes increasingly accurate as soon as all movements are stopped. Once a viewpoint has been chosen, a wide range of rendering techniques can be used to generate images, and their parameters can be tuned from within the program.

## Documentation

For compilation, usage, and a full plugin reference, please see the [official documentation](http://mitsuba-renderer.org/docs.html).

## Releases and scenes

Pre-built binaries, as well as example scenes, are available on the [Mitsuba website](http://mitsuba-renderer.org/download.html).
>>>>>>> 450a2b8a258f09ec7e0824861e2306340ccbb3f4
