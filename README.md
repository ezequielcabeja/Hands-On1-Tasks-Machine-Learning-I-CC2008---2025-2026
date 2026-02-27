# Hands-On1-Tasks-Machine-Learning-I-CC2008---2025-2026
Hands On1 – Tasks 
- [Setup environment](#setup-env) 
- [Explore Hotel Reservations Dataset](#explore-hotelreservations-dataset)

  <a id="setup-env"></a>
### Setup an environment for AC 1 course

This guide provides instructions for setting up the `ac1` environment using either:

1. **Miniconda**
2. **Python venv (alternative)**

Works on:
- Windows
- macOS
- Linux

We recommend using Miniconda (lighter than full Anaconda and more robust for reproducibility across operating systems, machines, and setups). However, if you prefer to avoid additional installations, you may use `venv`, as it only requires Python.

---

**MINICONDA**

Miniconda is strongly recommended for scientific Python environments because it avoids dependency conflicts that are common in pip-only setups.

---

#### 1) Installation

##### Windows

1. Download Miniconda from:
   https://docs.conda.io/en/latest/miniconda.html
2. Run the installer:
   - Select "Just for Me"
   - Optionally check "Add to PATH" (recommended if comfortable using the command line)
3. Open a new terminal (Anaconda Prompt or PowerShell)
4. Verify installation:

```bash
conda --version
```

---

##### macOS

1. Download the Miniconda installer
2. Run the installer
3. Open Terminal
4. Verify installation:

```bash
conda --version
```

If the command is not found, restart your terminal.

---

##### Linux

Download installer:

```bash
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
```

Install:

```bash
bash Miniconda3-latest-Linux-x86_64.sh
```

Restart your terminal and verify:

```bash
conda --version
```

---

#### 2) Create the AC1 Environment

(**NOTE:** In most cases, you will be provided with an environment file similar to the one below, and will only need to run `conda env create -f <environment_name>.yml`. This makes it easy to replicate results from papers or experiments using the correct versions of Python and packages.)

Create a file named `ac1.yml` in your project folder:

```yaml
name: ac1
channels:
  - conda-forge
dependencies:
  - python=3.11
  - numpy
  - pandas
  - scipy
  - scikit-learn
  - matplotlib
  - seaborn
  - plotly
  - jupyterlab
  - notebook
  - ipywidgets
  - tqdm
  - pip
```

Create the environment:

```bash
conda env create -f ac1.yml
```

(**NOTE:** It is good practice to create and use a different environment per project. This isolates package versions, guarantees reproducibility, and avoids conflicts that may arise when using `pip` only.)

Activate the environment:

```bash
conda activate ac1
```

Launch Jupyter:

```bash
jupyter lab
```

Verify installation:

```bash
python -c "import numpy, pandas, sklearn; print('AC1 ready')"
```

(**NOTE:** After activation, you should see `(ac1)` at the beginning of your terminal prompt. This indicates the environment is active. You may install additional packages using `pip`, but when possible, prefer `conda`, as it automatically manages dependency resolution.)

---

**PYTHON VENV (ALTERNATIVE)**

Use this if you do not want to install Miniconda. However, it is not recommended for larger scientific environments.

---

#### Requirements

- Python >= 3.11
- pip

Check your version:

```bash
python --version
```

If Python is not installed:

- Windows/macOS: https://www.python.org/downloads/
- Linux: use your distribution's package manager

---

#### 1) Create Virtual Environment

##### Windows

```bash
python -m venv ac1
ac1\Scripts\activate
```

If activation is blocked:

```bash
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

---

##### macOS / Linux

```bash
python3 -m venv ac1
source ac1/bin/activate
```

---

#### 2) Upgrade pip

```bash
pip install --upgrade pip
```

---

#### 3) Install Required Packages

```bash
pip install \
numpy \
pandas \
scipy \
scikit-learn \
matplotlib \
seaborn \
plotly \
jupyterlab \
notebook \
ipywidgets \
tqdm
```

---

#### 4) Start Jupyter

```bash
jupyter lab
```

---

### Updating the Environment

If using Conda:

```bash
conda update --all
```

If using venv:

```bash
pip install --upgrade <package_name>
```

---

### Removing the Environment

Conda:

```bash
conda remove -n ac1 --all
```

venv:

Delete the `ac1` folder.
