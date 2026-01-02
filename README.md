# 3D Haunted House

This project is a 3D interactive scene built with **Three.js** and **Vite**, demonstrating the composition of a complex environment using primitive shapes and procedural techniques.

## Technical Overview

### Scene Composition

The scene is constructed using `THREE.Group` and primitive geometries (`BoxGeometry`, `ConeGeometry`, `PlaneGeometry`) to assemble complex structures like the House, Roof, and Walls.

### Textures & Materials

- **PBR Materials**: Uses `MeshStandardMaterial` for realistic lighting interactions.
- **Texture Mapping**: Implements full texture sets including:
  - **Color** (Diffuse)
  - **ARM** (Ambient Occlusion, Roughness, Metalness) packed textures for efficiency.
  - **Normal Maps** for surface detail.
  - **Displacement Maps** for geometry deformation (e.g., on the floor).
- **Procedural Placement**: Graves are positioned procedurally using basic trigonometry (sin/cos) to create a scattered, organic effect around the house.

### Environment & Lighting

- **Lighting**:
  - `AmbientLight` for base illumination.
  - `DirectionalLight` simulating the moon, with shadow casting enabled.
  - `PointLights` for the door lamp and animated ghosts.
- **Shadows**: `PCFSoftShadowMap` is used for soft, realistic shadows.
- **Sky**: Implements the `Sky` class from `three/addons` to simulate a realistic atmosphere with Rayleigh and Mie scattering.
- **Fog**: `FogExp2` is applied to blend the floor edge into the background color effectively.

### Controls

- **OrbitControls** for camera navigation.
- **lil-gui** for real-time debugging and parameter tweaking (Sky sun position, Fog density, light intensity, etc.).
