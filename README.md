# README: Setting Up and Using Conda and Jupyter Notebook for This Project

## Overview

This document provides step-by-step instructions on setting up and using Conda and Jupyter Notebook to work with this project. It includes guidance on creating and activating Conda environments, installing dependencies, and running Jupyter Notebooks. This ensures reproducibility and ease of collaboration for all contributors.

---

## Prerequisites

Ensure you have the following installed on your system:

1. **Anaconda/Miniconda**:

   - [Download Anaconda](https://www.anaconda.com/products/distribution) for a full-featured environment.
   - Alternatively, install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) for a lightweight setup.

2. **Git**:

   - Install Git to clone the project repository:
     - **Linux**:
       ```bash
       sudo apt install git
       ```
     - **Windows**:
       Download Git from [git-scm.com](https://git-scm.com/) and follow the installation instructions.

3. **Jupyter Notebook**:
   - Installed within the Conda environment.

---

## Setting Up the Project

### Step 1: Clone the Repository

Clone this Git repository to your local machine:

```bash
git clone <repository-url>
cd <repository-name>
```

---

### Step 2: Create and Activate a Conda Environment

1. **Create a new Conda environment**:

   ```bash
   conda create -n my_project_env python=3.9
   ```

2. **Activate the environment**:

   - **Linux/Mac**:
     ```bash
     conda activate my_project_env
     ```
   - **Windows** (Command Prompt or Anaconda Prompt):
     ```cmd
     conda activate my_project_env
     ```

3. **Install the required dependencies**:
   Install the dependencies listed below:

   ```bash
   conda install numpy pandas matplotlib tensorflow pytorch -c pytorch
   pip install shap lime scikit-learn notebook
   ```

4. **Verify the installation**:
   Test that the libraries are properly installed by running:
   ```bash
   python -c "import numpy, pandas, shap; print('All packages loaded successfully!')"
   ```

---

### Step 3: Export the Conda Environment (Optional)

If you make changes to the environment, update the `environment.yml` file to share the environment with others:

```bash
conda env export > environment.yml
```

Add the updated `environment.yml` file to the Git repository:

```bash
git add environment.yml
git commit -m "Update environment.yml"
git push
```

---

## Using Jupyter Notebook

### Step 4: Add the Conda Environment to Jupyter

1. Install the `ipykernel` package in your Conda environment:

   ```bash
   pip install ipykernel
   ```

2. Add the environment to Jupyter:

   ```bash
   python -m ipykernel install --user --name=my_project_env --display-name "Python (my_project_env)"
   ```

3. Verify that the kernel is available:
   - Start Jupyter Notebook:
     ```bash
     jupyter notebook
     ```
   - In the notebook interface, check the kernel dropdown. You should see `Python (my_project_env)` as an option.

### Step 5: Run the Project in Jupyter Notebook

1. Navigate to the notebook file in the project directory (if any) or create a new notebook.
2. Select the kernel for your Conda environment (`Python (my_project_env)`) from the dropdown menu.
3. Run cells to test or execute the project code.

---

## Reproducing the Environment

To recreate the environment on another system:

1. Clone the repository:

   ```bash
   git clone <repository-url>
   cd <repository-name>
   ```

2. Create the environment from the `environment.yml` file:

   ```bash
   conda env create -f environment.yml
   ```

3. Activate the environment:

   - **Linux/Mac**:
     ```bash
     conda activate my_project_env
     ```
   - **Windows**:
     ```cmd
     conda activate my_project_env
     ```

4. Add the Conda environment to Jupyter (as described in Step 4).

---

## Best Practices

- Always activate your Conda environment before running the project code:

  - **Linux/Mac**:
    ```bash
    conda activate my_project_env
    ```
  - **Windows**:
    ```cmd
    conda activate my_project_env
    ```

- Avoid committing large files (e.g., `.conda` directories) to Git. Use the provided `.gitignore` file to exclude unnecessary files.

- Use `pip freeze` or `conda env export` to track dependencies when installing new libraries.

---

## Troubleshooting

- **Environment Not Found**:
  Ensure you’ve activated the correct Conda environment:

  - **Linux/Mac**:
    ```bash
    conda activate my_project_env
    ```
  - **Windows**:
    ```cmd
    conda activate my_project_env
    ```

- **Kernel Missing in Jupyter**:
  Add the environment to Jupyter again:

  ```bash
  python -m ipykernel install --user --name=my_project_env --display-name "Python (my_project_env)"
  ```

- **Dependency Issues**:
  If you encounter issues with dependency conflicts, consider creating a fresh environment and reinstalling packages.

---

This README ensures anyone collaborating on the project can set up the environment and run the code successfully. For further questions, reach out to the project maintainer.

