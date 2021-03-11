---
layout: single
author_profile: True
classes: wide
excerpt: "Efficient sampler for geometric deep learning<br/>CVPR 2021"
header:
  overlay_image: /assets/images/Tessellation_MongeNet.png
  overlay_filter: 0.5
  caption: "Voronoi Tessellation for MongeNet sampled points.
  "
  actions:
    - label: "Paper"
      url: "https://github.com/lebrat/MongeNet"
    - label: "Code"
      url: "https://github.com/lebrat/MongeNet"
    - label: "Slides"
      url: "https://github.com/lebrat/MongeNet"
    - label: "Talk"
      url: "https://github.com/lebrat/MongeNet"
authors:
  - image_path: assets/images/bio-leo.jpg
    title: "Leo Lebrat"
    excerpt: ""
  - image_path: assets/images/bio-rodrigo.jpg
    title: "Rodrigo Santa Cruz"
  - image_path: assets/images/bio-clinton.jpg    
    title: "Clinton Fookes"
  - image_path: assets/images/bio-olivier.jpg
    title: "Olivier Salvado"
---


Recent advances in geometric deep-learning introduce complex computational challenges for evaluating the distance between meshes. From a mesh model, point clouds are necessary along with a robust distance metric to assess surface quality or as part of the loss function for training models. Current methods often rely on a uniform random mesh discretization, which yields irregular sampling and noisy distance estimation. We introduce, a fast and optimal transport based sampler that allows for an accurate discretization of a mesh with better approximation properties. Compared to the ubiquitous random uniform sampling, MongeNet approximation error is almost half with a very small computational overhead.


## Mesh Sampling Example

The image below shows an airplane mesh with sampled point clouds using MongeNet (left) and Random Uniform Sampling (right). We can observe that random uniform sampling produces clustering of points (clamping) along the surface resulting in large undersampled areas and spurious artifacts for flat surfaces. In contrast, MongeNet sampled points are uniformly distributed which better approximate the underlying mesh surfaces without producing sampling artifacts.

{% include figure image_path="/assets/images/avion_both.png" alt="Mesh sampling example" caption="Plane of the ShapeNet dataset sampled with 5k points. ***Left***: Point cloud produced by MongeNet. ***Right***: Point cloud produced by the random uniform sampler. Note the clamping pattern across the mesh produced by the random uniform sampling approach." %}



## Reconstructing watertight mesh surface from noisy point cloud 

The videos below compare the mesh reconstructing results of the [Point2Mesh](https://ranahanocka.github.io/point2mesh/) model using MongeNet and Random Uniform Sampling for two very complex shapes. MongeNet produces better results mainly in the shape's fine details and areas of high curvature.

{% include video id="RfmZBbSEiz4" provider="youtube" %}
{% include video id="iDA9n5CFY4c" provider="youtube" %}

<br/><br/>

If you find this work useful, please cite
```
@InProceedings{Lebrat:CVPR21:MongeNet,
    author    = {Lebrat, Leo and Santa Cruz, Rodrigo and Fookes, Clinton and Salvado, Olivier},
    title     = {MongeNet: Efficient sampler for geometric deep learning},
    booktitle = {Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition (CVPR)},
    month     = {June},
    year      = {2021}
}
```
