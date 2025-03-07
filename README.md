# SqueezeNet CNN for FPGA

This repository contains a Jupyter notebook for working with SqueezeNet v1.1 using PyTorch and PyOpenCL.

## Requirements

- Miniconda or Anaconda (if not installed, download from https://docs.conda.io/en/latest/miniconda.html)

## Setting up the Environment

### Automatic Setup (Recommended)

1. Make the setup script executable:
   ```
   chmod +x setup_environment.sh
   ```

2. Run the setup script:
   ```
   ./setup_environment.sh
   ```

### Manual Setup

If you prefer to set up the environment manually:

1. First, set the classic solver as default:
   ```
   conda config --set solver classic
   ```

2. Create the conda environment:
   ```
   conda env create -f environment.yml
   ```

3. Activate the environment:
   ```
   conda activate squeezenet
   ```

4. Install the Jupyter kernel:
   ```
   python -m ipykernel install --user --name squeezenet --display-name "Python (squeezenet)"
   ```

### Troubleshooting Conda Errors

If you encounter errors like "Error while loading conda entry point: conda-libmamba-solver", this is related to issues with the libmamba solver. The setup instructions above use the classic solver, but you can also try:

1. Updating conda:
   ```
   conda update -n base conda
   ```

2. Fixing the libmamba installation:
   ```
   conda install -n base conda-libmamba-solver
   ```

## Running the Notebook

1. Activate the environment:
   ```
   conda activate squeezenet
   ```

2. Start Jupyter Notebook:
   ```
   jupyter notebook
   ```

3. Open the `SqueezeNet.ipynb` notebook

4. Make sure to select the `Python (squeezenet)` kernel in Jupyter

## Environment Details

The conda environment includes:
- Python 3.9
- PyTorch with torchvision
- PyOpenCL
- NumPy
- Matplotlib
- Pillow (PIL)
- Jupyter Notebook

### Note for macOS Users

For macOS, we don't include CUDA dependencies since PyTorch on macOS doesn't typically use CUDA. If you're using Apple Silicon (M1/M2/M3), PyTorch will automatically use Metal Performance Shaders (MPS) for GPU acceleration if available.

If you encounter any issues with PyOpenCL, you may need to install the OpenCL drivers for your system. 