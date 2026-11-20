# DS4002_Project3

This repository contains the process for developing and running a MobileNetV2 CNN transfer-learning model with images to classify unseen marine organism images. 
## Contents of the Repository
### Software and Platform

- **IDE**: Visual Studio Code (VS Code) & Google Colab
- **OS**: Windows 11 or Mac OS 15.1.1 (Sequoia)
- **Terminal**: VS Code Integrated Terminal or Windows PowerShell
- **Programming Language**: Python
- **Version Control / Repository**: GitHub
  
#### Add-On Packages and Libraries

The project uses the following Python packages:
- pandas 2.2.2
- matplotlib 3.8.4
- numpy 1.26.4
- statsmodels 0.14.4
- seaborn
- tensorflow
- scikit-learn
- pillow 
See `requirements.txt` for the complete list of required packages.
 

### Map of the Documentation

The repository is organized as follows:
```text
DS4002_Project3/
├── LICENSE
├── README.md
├── data
│   ├── Link to Google Drive
│   └── readme.md
├── output
└── scripts
    ├── mi2_baseline.ipynb
    └── mi2.py
```
**Folder and File Descriptions**

### Folder and File Descriptions

- `data/` — Contains the link to google drive with images already split that are used to train, validate, and test the CNN to classify unseen marine organisms
    - `Data Link`: Link to our Google Drive image dataset. When used with our mi2 Notebook script, produces the training, development, and test image sets.
    - `README.md`: Provides additional documentation and instruction for the dataset.

- `output/` — Contains figures generated during exploratory data analysis and model evaluation.

- `scripts/` — Contains the scripts used to prepare data, conduct exploratory analysis, and fit and evaluate the SARIMAX model.
    - `mi2_baseline.ipynb`: Provides a random pretrained Mobilenetv2 model for comparison with our results.
    - `mi2.py`: Our model, along with its training weights and connection to the images in Google Drive.

- `README.md` — Provides an overview of the project, its organization, software requirements, and instructions for reproducing the analysis.
- `LICENSE` — Specifies the terms under which the project's code and other covered materials may be used, modified, and distributed.
  
### Instructions for Reproducing the Results

The following steps describe how to download the project, set up the Python environment, prepare the data, run the exploratory data analysis, and generate the model results.

#### Step 1: Download the Repository

1. Navigate to the GitHub repository and click the green **Code** button. Copy the HTTPS URL:

   ```text
   https://github.com/allyoshea/DS4002_Project2.git
   ```

2. Open the Terminal application on your computer.

3. Navigate to the location where you want to save the project, such as your Desktop:

   ```bash
   cd ~/Desktop
   ```

4. Clone the repository:

   ```bash
   git clone https://github.com/allyoshea/DS4002_Project2.git
   ```

5. Navigate into the project folder:

   ```bash
   cd DS4002_Project2
   ```

6. Open the `DS4002_Project2` folder in Visual Studio Code or another compatible coding environment.

#### Step 2: Set Up the Python Environment

The project uses Python for exploratory data analysis, SARIMAX modeling, and visualization. R is used to process the power plant generation data.

1. In Visual Studio Code, select **Terminal → New Terminal** from the top menu.

2. Confirm that the terminal is located in the `DS4002_Project2` directory.
#### Step 2: Set Up the Python and R Environments

The project uses Python for exploratory data analysis, SARIMAX modeling, and visualization. R is used to process power plant generation data and perform additional exploratory data analysis. Both languages can be run from the integrated terminal in Visual Studio Code.

**Python setup**

1. In Visual Studio Code, select **Terminal → New Terminal** from the top menu.
2. Confirm that the terminal is located in the `DS4002_Project2` directory.
3. Create a Python virtual environment:

   ```bash
   python3 -m venv .venv
   ```

4. Activate the virtual environment on macOS:

   ```bash
   source .venv/bin/activate
   ```

   On Windows PowerShell, use:

   ```powershell
   .venv\Scripts\Activate.ps1
   ```

5. Install the required Python packages:

   ```bash
   python -m pip install -r requirements.txt
   ```

**R setup**

R must be installed separately on your computer. You do not need to create a separate R environment to run this project. You can run R and Python scripts from the same VS Code terminal, even while the Python virtual environment is activated.

The R scripts require the packages `readxl`, `dplyr`, and `purrr`. To install these packages, open an R console and run:

```r
install.packages(c("readxl", "dplyr", "purrr"))
```

After installing R and the required packages, you can run R scripts from the VS Code terminal using `Rscript`, just as you run Python scripts using `python`. For example:

```bash
Rscript scripts/01_PowerPlantGenerationCalculation.R
```

Make sure the terminal is open in the `DS4002_Project2` project directory before running the scripts.
6. To run the power plant generation processing script, ensure that R is installed. The script uses the R packages `readxl`, `dplyr`, and `purrr`.

#### Step 3: Prepare the Data and Run Exploratory Data Analysis

The `data/` directory contains the source datasets and the combined dataset used for modeling.

The R script `01_PowerPlantGenerationCalculation.R` processes monthly power plant generation data from the source Excel workbook, combines the relevant annual worksheets, standardizes the variables, and aggregates electricity generation by year and month. The script is expected to produce `data/us_monthly.csv`.

If the required source workbook is available in the `data/` directory, run the script using:

```bash
Rscript scripts/01_PowerPlantGenerationCalculation.R
```

The combined dataset, `data/data.csv`, contains the residential electricity price data and selected predictor variables used by the SARIMAX model.

To run the exploratory data analysis script, execute:

```bash
python scripts/02_eda.py
pyton scripts/02_VIF.py
Rscript scripts/02_eda.R
```


#### Step 4: Run the SARIMAX Model

The SARIMAX modeling script is located in the `scripts/` directory. To run the model, execute:

```bash
python scripts/03_sarimax_price_model.py
```


The script fits the SARIMAX model using the combined dataset and generates forecast and diagnostic figures in the `output/` directory.


If cross-validation is run and configured to save its results, the corresponding results file will also be saved in the `output/` directory.

#### Step 5: Review the Results

After running the scripts, the processed datasets will be located in the `data/` directory, and the generated figures will be located in the `output/` directory. Expected outputs for each scripts are labeled at the top of the respective scripts.

The intended analysis covers monthly U.S. residential electricity prices from January 2015 through June 2026, depending on the observations available in the combined dataset. 
The analysis considers the following nine potential predictors:

- Data center spending
- Crude oil prices
- Inflation rate
- Power plant generation
- Retail sales
- Average temperature
- Natural gas prices (Henry Hub)
- Heating degree days
- Cooling degree days

The resulting datasets, forecast plots, and diagnostic figures can be used to evaluate electricity price trends, seasonal patterns, and the potential contribution of external predictors to forecast accuracy.

### Project Workflow

```text
Clone GitHub Repository
        ↓
Open Project in VS Code
        ↓
Create and Activate Python and R Environments
        ↓
Install Required Packages
        ↓
Verify the Combined Dataset
        ↓
Run Exploratory Data Analysis
        ↓
Run SARIMAX Model and Evaluation
        ↓
Review Forecasts and Diagnostic Figures
```
```
## References
