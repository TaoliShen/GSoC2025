## GSoC2025: Enhanced Dual Contouring
I participated in **Google Summer of Code 2025** with [CGAL](https://www.cgal.org/), where I developed methods for robust manifold isosurface extraction in the `Isosurfacing_3` package.
## Introduction
**Dual Contouring (DC)** is a classical mesh extraction method implemented in CGAL. A key limitation of the standard DC method is that it can generate **nonmanifold surfaces**, leading to topological inconsistencies and computational challenges. The overall objective is to enhance CGAL's dual contouring solver to ensure that the generated surfaces are always **2-manifold**. Several variants have been proposed in the literature to address this issue. Among them, we decided to implement the **Manifold Dual Contouring (MDC)** method introduced by Schaefer, Ju and Warren. 

- In the **uniform voxel grid** setting, MDC reduces to the **Dual Marching Cubes (DMC)** method, which constructs meshes using dual vertices derived from patches in the marching cubes lookup table.  
- In the **adaptive octree** setting, MDC further incorporates **vertex clustering** and a **manifold criterion** to avoid the generation of non-manifold configurations.
  
However, during the implementation, we observed that even MDC does not always guarantee manifold output. For this reason, the project trajectory shifted to focus specifically on **enforcing manifold guarantees in the uniform voxel case**, laying a robust foundation before tackling adaptive refinement.  
