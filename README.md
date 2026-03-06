# Learning to Solve PDEs on Neural Shape Representations

[![Website](https://img.shields.io/badge/Website-Live-blue)](https://welschinger.github.io/Learning-to-Solve-PDEs-on-Neural-Shape-Representations/)
[![Code](https://img.shields.io/badge/Code-GitHub-black)](https://github.com/welschinger/Learning-to-Solve-PDEs-on-Neural-Shape-Representations/tree/main/release_code)

[![Paper](https://img.shields.io/badge/Paper-arXiv-b31b1b?style=for-the-badge&logo=arxiv)](https://arxiv.org/abs/2512.21311)

This folder contains the code for the paper "Learning to Solve PDEs on Neural Shape Representations" under /release_code.

<p align="center">
  <img src="assets/Teaser.png" width="800"/>
</p>

<p align="center">

## Installation

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/welschinger/Learning-to-Solve-PDEs-on-Neural-Shape-Representations.git
    cd Learning-to-Solve-PDEs-on-Neural-Shape-Representations/release_code
    ```

2.  **Install dependencies:**
    It is recommended to use a virtual environment (e.g., conda or venv).
    ```bash
    pip install -r requirements.txt
    ```
    Install pytorch with:
    ```bash
    pip install torch==2.10.0+cu126 --index-url https://download.pytorch.org/whl/cu126
    ```

## Dataset

The code expects surface features and pretrained weights.
-   **Surface Features:** Located in `data/`. Example: `data/Apple_surface_feature.npy`.
-   **Pretrained Model Weight checkpoints:** Located in `model/weights/`. Example: `model/weights/SurfNO_pretrained_weights.pth`.

## Usage

### 1. Solving Poisson Equation

Run the solver script:
```bash
python Solve_poisson_equation.py
```
This script will:
-   Solve the Poisson equation on the surface of the Apple example.
-   Save the solution to `poisson_solution.npy`.
-   Generate an interactive 3D plot `poisson_solution.html` visualizing the result.

### 2. Solving Heat Equation (Diffusion)

Run the heat equation solver:
```bash
python Solve_heat_equation.py
```
This script will:
-   Simulate heat diffusion over time, on the Apple's surface.
-   Save the final solution to `diffusion_solution.npy`.
-   Generate an animated 3D plot `heat_diffusion.html` visualizing the diffusion process.

### 3. Training

To train the model yourself:
```bash
python train_model.py
```
*The checkpoints will be saved under /release_code/pretrained/multi_reso_spike_training*

## Visualization

The solvers generate HTML files using Plotly. You can open these files (`poisson_solution.html`, `heat_diffusion.html`) in any web browser to interact with the 3D results.

-   **Poisson Solution:** Static 3D point cloud colored by solution values.
-   **Heat Diffusion:** Animated 3D point cloud showing the evolution of heat over time.
