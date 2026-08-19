# LunarDEM-SR
# LunarDEM-SR

Deep learning-based super-resolution of lunar Digital Elevation Models (DEMs), reconstructing **1 m-resolution terrain from 5 m-resolution data** for hazard mapping and autonomous lander navigation.

## Architecture

The current model follows a fully convolutional super-resolution architecture:

**5 m DEM (50×50)**
↓
**Convolutional feature extraction**
↓
**Deep terrain feature reconstruction**
↓
**Upsampling ×5**
↓
**Convolutional refinement**
↓
**1 m DEM (250×250)**

The network operates directly on the spatial elevation data without flattening or dense layers.

## Pipeline

```text
5 m Lunar DEM
      ↓
Super-Resolution CNN
      ↓
1 m Lunar DEM
      ↓
Terrain Analysis
      ↓
Slope / Crater / Boulder / Roughness
      ↓
Hazard Map
```

## Dataset

The prototype uses high-resolution lunar DEM data to create paired training samples:

* **Input:** 5 m/pixel DEM
* **Target:** 1 m/pixel DEM
* **Patch:** 250 m × 250 m
* **Input dimensions:** 50 × 50
* **Target dimensions:** 250 × 250

Additional high-resolution lunar DEM regions can be incorporated as the project develops.

## Goals

* Reconstruct high-resolution lunar terrain from lower-resolution data
* Preserve terrain features important for landing safety
* Generate **1 m × 1 m hazard maps**
* Explore near-real-time inference for autonomous lander navigation

**Status:** 🚧 Prototype / Research

