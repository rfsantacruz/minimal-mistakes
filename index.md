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
gallery_voronoi:
  - url: /assets/images/voronoi_monge.gif
    image_path: /assets/images/voronoi_monge.gif
    alt: "MongeNet mesh discretization by a point cloud"
    title: "MongeNet mesh discretization by a point cloud"
  - url: /assets/images/voronoi_unif.gif
    image_path: /assets/images/voronoi_unif.gif
    alt: "Standard random uniform mesh discretization by a point cloud"
    title: "Standard random uniform mesh discretization by a point cloud" 
gallery_airplane:
  - url: /assets/images/avion_mongenet.png
    image_path: /assets/images/avion_mongenet.png
    alt: "MongeNet mesh discretization by a point cloud"
    title: "MongeNet mesh discretization by a point cloud"
  - url: /assets/images/avion_uniform.png
    image_path: /assets/images/avion_uniform.png
    alt: "Standard random uniform mesh discretization by a point cloud"
    title: "Standard random uniform mesh discretization by a point cloud" 
---


Recent advances in geometric deep-learning introduce complex computational challenges for evaluating the distance between meshes. From a mesh model, point clouds are necessary along with a robust distance metric to assess surface quality or as part of the loss function for training models. Current methods often rely on a uniform random mesh discretization, which yields irregular sampling and noisy distance estimation. We introduce, a fast and optimal transport based sampler that allows for an accurate discretization of a mesh with better approximation properties. Compared to the ubiquitous random uniform sampling, MongeNet approximation error is almost half with a very small computational overhead.


## Mesh Sampling Example

The image below shows an airplane mesh with sampled point clouds using MongeNet (left) and Random Uniform Sampling (right). We can observe that random uniform sampling produces clustering of points (clamping) along the surface resulting in large undersampled areas and spurious artifacts for flat surfaces. In contrast, MongeNet sampled points are uniformly distributed which better approximate the underlying mesh surfaces without producing sampling artifacts.

<!-- {% include figure image_path="/assets/images/avion_both.png" alt="Mesh sampling example" caption="Plane of the ShapeNet dataset sampled with 5k points. ***Left***: Point cloud produced by MongeNet. ***Right***: Point cloud produced by the random uniform sampler. Note the clamping pattern across the mesh produced by the random uniform sampling approach." %} -->

{% include gallery id="gallery_airplane" caption="Plane of the ShapeNet dataset sampled with 5k points. ***Left***: Point cloud produced by MongeNet. ***Right***: Point cloud produced by the random uniform sampler. Note the clamping pattern across the mesh produced by the random uniform sampling approach." %}

{% include gallery id="gallery_voronoi" caption="Discretization of a mesh by a point cloud. ***Left:*** MongeNet discretisation. ***Right:*** Classical random uniform, with
in red the resulting Voronoi Tessellation spawn on the triangles of the mesh." %}


<!-- 
![image-left]({{ site.url }}{{ site.baseurl }}/assets/images/voronoi_monge.gif){: .align-left}

![image-right]({{ site.url }}{{ site.baseurl }}/assets/images/voronoi_unif.gif){: .align-right} -->

<!-- {% include figure image_path="/assets/images/voronoi_monge.gif" alt="" caption="" %} -->

<!-- {% include figure image_path="/assets/images/voronoi_unif.gif" alt="" caption="" %} -->



## Reconstructing watertight mesh surface from noisy point cloud 

The videos below compare the mesh reconstructing results of the [Point2Mesh](https://ranahanocka.github.io/point2mesh/) model using MongeNet and Random Uniform Sampling for two very complex shapes. MongeNet produces better results mainly in the shape's fine details and areas of high curvature.

{% include video id="RfmZBbSEiz4" provider="youtube" %}
{% include video id="6FGA5JJqM-A" provider="youtube" %}

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