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

1. **Recreate the environment from environment.yml file**:
  ```cmd
   conda env create -f environment.yml 
   ```
   or 
   ```cmd 
   conda env update -f environment.yml --prune
   ```
   to update the enivroment.

2. **Activate the environment**:
   If the `environment.yml` file is already in the repository, recreate the environment:

   - **Windows** (Command Prompt or Anaconda Prompt):
     ```cmd
     conda activate xai-env
     ```
---

### Step 3: Export the Conda Environment (If Changes Are Made)

If you make changes to the environment (e.g., installing additional packages), update the `environment.yml` file to share the environment with others:

```cmd
conda env export --name xai-env --no-builds > environment.yml

```

Add the updated `environment.yml` file to the Git repository:

```bash
git add environment.yml
git commit -m "Update environment.yml"
git push
```

---

### Step 5: Run the Project in Jupyter Notebook

1. Navigate to the notebook file in the project directory (if any) or create a new notebook.
2. Select the kernel for your Conda environment (`Python (xai-env)`) from the dropdown menu.
3. Run cells to test or execute the project code.

---

## Workflow: Before, During, and After Working on the Project

### **Before Starting a Session**

1. **Pull the Latest Changes**:
   Ensure your local repository is up to date:
   ```cmd
   git pull origin main
   ```
2. **Activate the Conda Environment**:
   Activate the Conda environment for the project:
   - **Windows**:
     ```cmd
     conda activate xai-env
     ```
3. **Start Jupyter Notebook**:
   Launch Jupyter Notebook in the project directory:
   ```cmd
   jupyter notebook
   ```

### **During the Session**

1. **Work on Code or Notebooks**:
   - Ensure you are using the correct kernel (`Python (xai-env)`) in Jupyter Notebook.
   - Save your work regularly.
2. **Test Changes**:
   Run and test your code to ensure functionality.
3. **Document Changes**:
   Keep notes on what you are modifying or add comments in the code for clarity.

### **After Finishing a Session**

1. **Save and Commit Your Changes**:
   
2. **Deactivate the Conda Environment**:
   Deactivate the environment to avoid conflicts:
   ```cmd
   conda deactivate
   ```
3. **Export Updated Environment (if needed)**:
   If you added new dependencies, update the `environment.yml` file:
   ```cmd
   conda env export > environment.yml
   git add environment.yml
   git commit -m "Update environment dependencies"
   git push
   ```
---
