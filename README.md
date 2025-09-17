# Ternary Exploration Project  

This project generates ternary phase diagrams with experimental (EDX) sample points and calculated phase regions from CIF files. Students must **customize the notebook** and **set up their Python environment** before running.  

---

## 1. Code Adjustments in `Ternary_Plot_Generator.ipynb`  

The following lines must be modified for each new system you study, the elements should be plotted accordingly so that the most electronegative elemen is on the bottom left corner, the most electronegative on top and intermediate on the bottom right corner:  

```python
# Define your ternary elements
ternary_elements = ['Gd', 'Os', 'Ge']  # <--- CHANGE

# Define CIF folders for pairwise combinations
folder1 = f"/Users/username/Desktop/Gd-Os-X/CIFs/{el1}-{el2}"  # <--- CHANGE to your directory
folder2 = f"/Users/username/Desktop/Gd-Os-X/CIFs/{el2}-{el1}"  # <--- CHANGE to your directory as above

# EDX samples: update keys and values to match ternary_elements
edx_samples = [  # <--- CHANGE
    {
        "label": "Sample 1",
        "composition": {el: val for el, val in zip(ternary_elements, [39.47, 19.58, 40.45])},  
        # <--- CHANGE values to your sample composition
        "color": "#0066FF",
        "edge_color": "#003399",
        "arrow": True,
        "phases": ["GdGe", "Gd3Os", "Os"],  # <--- CHANGE phases based on XRD and SEM/EDX analysis
    },
]

# Save figure output
plt.savefig("/Users/username/Downloads/ternary_plot.png", dpi=300, bbox_inches='tight')  # <--- CHANGE based on your output directory
```
---

## 2. Environment Setup in VS Code  

Follow these steps to ensure everything runs smoothly:  

### Step 1. Install Conda  
Download and install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/).  

### Step 2. Create a Conda Environment  
Open a terminal in VS Code and run:  

```bash
conda create -n ternary python=3.10 -y
conda activate ternary
```

### Step 3. Install Dependencies
Inside the activated environment, install the required Python libraries:
```bash
pip install numpy matplotlib ipywidgets mplcursors PyCifRW
```
---
## 3. Running the Project
- Open Ternary_Plot_Generator.ipynb in VS Code.
- Adjust the ternary elements, CIF folder paths, EDX samples, and save path as shown above.
- Run all cells in the notebook (Shift + Enter for each, or Run All).
- The ternary diagram will be saved to your specified output path.
