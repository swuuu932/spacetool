# Advanced 3D Geometry Experiment Simulator Blueprint

## Overview
A comprehensive web-based 3D laboratory for exploring geometric properties, cross-sections, and topological characteristics of various polyhedra and primitives.

## Features
- **Advanced Shape Library**: 
    - Standard Primitives: Cube, Rectangular Prism, Sphere, Cylinder, Cone.
    - Regular Polyhedra: Tetrahedron, Octahedron, Dodecahedron, Icosahedron.
    - **Custom Polyhedron**: Generate shapes by providing raw vertex coordinates (Convex Hull).
- **Interactive Geometric Controls**:
    - Real-time adjustment of dimensions (radius, height, width, etc.).
    - Direct vertex coordinate input via text area.
- **Dynamic Cross-section System**:
    - **Plane Equation**: $nx \cdot x + ny \cdot y + nz \cdot z + d = 0$.
    - Sliders for normal vector components ($n_x, n_y, n_z$) and distance ($d$).
    - Real-time visualization of the intersecting plane and the resulting polygon.
- **Geometric Analysis Engine**:
    - **Cross-section Data**: Calculate vertex count, area, and perimeter of the intersection.
    - **Topology (Euler's Formula)**: Automatically calculate Vertices ($V$), Edges ($E$), and Faces ($F$) for the active shape and verify $V - E + F$.
- **Modern UI/UX**: 
    - Dual-pane layout: Left control panel, right full-screen 3D view.
    - Responsive design with detailed numerical readouts.

## Technical Implementation
- **Three.js**: Core 3D engine.
- **ConvexGeometry**: For generating shapes from custom vertex sets.
- **Math Utilities**:
    - **Line-Plane Intersection**: For finding polygon vertices.
    - **Shoelace Formula**: For calculating the area of the 2D projected cross-section.
    - **Polygon Sorting**: Angle-based sorting around the centroid for correct rendering.
- **Topology Analysis**: Extraction of unique vertices and edges from `BufferGeometry`.

## Implementation Plan
1. **Infrastructure**: Setup scene, camera, lights, and layout.
2. **Geometry Factory**: Functions to create primitives and convex hulls from user input.
3. **Topology Engine**: Logic to count $V, E, F$ by analyzing geometry buffers.
4. **Intersection Logic**: High-performance edge-plane intersection and polygon construction.
5. **UI Development**: Multi-section sidebar with parameter inputs and live data display.
6. **Validation**: Test with various shapes and extreme plane orientations.
