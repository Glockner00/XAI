# README: Setting Up and Using Conda and Jupyter Notebook for This Project

## Overview

This document provides step-by-step instructions on setting up and using Conda and Jupyter Notebook to work with this project.

---

## Prerequisites

Ensure you have the following installed on your system:

1. **Anaconda/Miniconda**:

   - [Download Anaconda](https://www.anaconda.com/products/distribution) for a full-featured environment.
   - Alternatively, install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) for a lightweight setup.

2. **Jupyter Notebook**:
   - Installed within the Conda environment.

---

## Setting Up the Project

### Step 1: Clone the Repository

Clone this Git repository to your local machine:

```bash
git clone git@github.com:Glockner00/XAI.git && cd XAI
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

3. **Recreate the Environment from environment.yml**:
   If the `environment.yml` file is already in the repository, recreate the environment:

   ```bash
   conda env create -f environment.yml
   ```

4. **Verify the installation**:
   Test that the libraries are properly installed by running:
   ```bash
   python -c "import numpy, pandas, shap; print('All packages loaded successfully!')"
   ```

---

### Step 3: Export the Conda Environment (If Changes Are Made)

If you make changes to the environment (e.g., installing additional packages), update the `environment.yml` file to share the environment with others:

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

## Workflow: Before, During, and After Working on the Project

### **Before Starting a Session**

1. **Pull the Latest Changes**:
   Ensure your local repository is up to date:
   ```bash
   git pull origin main
   ```
2. **Activate the Conda Environment**:
   Activate the Conda environment for the project:
   - **Linux/Mac**:
     ```bash
     conda activate my_project_env
     ```
   - **Windows**:
     ```cmd
     conda activate my_project_env
     ```
3. **Start Jupyter Notebook**:
   Launch Jupyter Notebook in the project directory:
   ```bash
   jupyter notebook
   ```

### **During the Session**

1. **Work on Code or Notebooks**:
   - Ensure you are using the correct kernel (`Python (my_project_env)`) in Jupyter Notebook.
   - Save your work regularly.
2. **Test Changes**:
   Run and test your code to ensure functionality.
3. **Document Changes**:
   Keep notes on what you are modifying or add comments in the code for clarity.

### **After Finishing a Session**

1. **Save and Commit Your Changes**:
   Save your work and commit changes to Git:
   ```bash
   git add .
   git commit -m "Describe your changes"
   git push origin main
   ```
2. **Deactivate the Conda Environment**:
   Deactivate the environment to avoid conflicts:
   ```bash
   conda deactivate
   ```
3. **Export Updated Environment (if needed)**:
   If you added new dependencies, update the `environment.yml` file:
   ```bash
   conda env export > environment.yml
   git add environment.yml
   git commit -m "Update environment dependencies"
   git push
   ```

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

This README ensures anyone collaborating on the project can set up the environment, follow the workflow, and run the code successfully. For further questions, reach out to the project maintainer.
