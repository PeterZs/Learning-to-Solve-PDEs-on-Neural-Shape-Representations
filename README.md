# Learning to Solve PDEs on Neural Shape Representations

[![Website](https://img.shields.io/badge/Website-Live-blue)](https://welschinger.github.io/Learning-to-Solve-PDEs-on-Neural-Shape-Representations/)
[![Code](https://img.shields.io/badge/Code-GitHub-black)](https://github.com/welschinger/Learning-to-Solve-PDEs-on-Neural-Shape-Representations/tree/main/release_code)

This folder contains the code for the paper "Learning to Solve PDEs on Neural Shape Representations".

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
    *Note: For GPU support with PyTorch, please install the appropriate version for your CUDA setup from [pytorch.org](https://pytorch.org/).*

## Dataset

The code expects surface features and pretrained weights.
-   **Surface Features:** Located in `data/`. Example: `data/Apple_surface_feature.npy`.
-   **Model Weights:** Located in `model/weights/`. Example: `model/weights/SurfNO_pretrained_weights.pth`.

## Usage

### 1. Solving Poisson Equation

Run the solver script:
```bash
python Solve_poisson_equation.py
```
This script will:
-   Load the pretrained SurfNO model.
-   Solve the Poisson equation on the surface.
-   Save the solution to `poisson_solution.npy`.
-   Generate an interactive 3D plot `poisson_solution.html` visualizing the result.

### 2. Solving Heat Equation (Diffusion)

Run the heat equation solver:
```bash
python Solve_heat_equation.py
```
This script will:
-   Simulate heat diffusion over time.
-   Save the final solution to `diffusion_solution.npy`.
-   Generate an animated 3D plot `heat_diffusion.html` visualizing the diffusion process.

### 3. Training

(Optional) To train the model yourself:
```bash
python train_model.py
```
*Check the script for configuration options and data paths.*

## Visualization

The solvers generate HTML files using Plotly. You can open these files (`poisson_solution.html`, `heat_diffusion.html`) in any web browser to interact with the 3D results.

-   **Poisson Solution:** Static 3D point cloud colored by solution values.
-   **Heat Diffusion:** Animated 3D point cloud showing the evolution of heat over time.

## File Structure

-   `Solve_poisson_equation.py`: Main script for Poisson problem.
-   `Solve_heat_equation.py`: Main script for Heat diffusion.
-   `train_model.py`: Script for training the model.
-   `model/`: Contains dataset and model definitions (`SurfNO.py`).
-   `utils/`: Utility functions for geometry processing, Laplacian matrix, drawing, etc.
    -   `draw.py`: Visualization utilities (Plotly based).
