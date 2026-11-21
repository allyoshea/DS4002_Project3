# DS4002_Project3

This repository contains the process for developing and running a MobileNetV2 CNN transfer-learning model with images to classify unseen marine organism images. 
*CONTEXT HERE: did not get access to HPC until friday at arund 10:00am. As such I will attempt to use it for MI4 but did not have time to use it for this assignment. 
## Contents of the Repository
### Software and Platform

- **IDE**: Visual Studio Code (VS Code) & Google Colab
- **OS**: Windows 11 or Mac OS 15.1.1 (Sequoia)
- **Terminal**: VS Code Integrated Terminal or Windows PowerShell
- **Programming Language**: Python
- **Version Control / Repository**: GitHub
- **Data Storage**: Google Drive
  
#### Add-On Packages and Libraries

The project uses the following Python packages:
- pandas 2.2.2
- matplotlib 3.8.4
- numpy 1.26.4
- seaborn  0.13.2
- tensorflow 2.21.0
- scikit-learn 1.9.1
- pillow 13.0.0
See `requirements.txt` for the complete list of required packages.
 

### Map of the Documentation

The repository is organized as follows:
```text
DS4002_Project3/
├── LICENSE
├── README.md
├── data
│   ├── Data Link
│   └── README.md
├── output
│   ├── 11_organism_precision_comparison.png
│   ├── 12_overall_accuracy_comparison.png
│   ├── CNN
│   │   ├── 09_cnn_accuracy.png
│   │   └── 10_cnn_confusion_matrix.png
│   ├── EDA plots
│   │   ├── 01_observation_availability.png
│   │   ├── 02_original_image_aspect_ratios.png
│   │   ├── 02_original_image_heights.png
│   │   └── 02_original_image_resolutions.png
│   └── MobileNetV2
│       ├── 03_misclassified_images.png
│       ├── 04_f1_score_by_organism.png
│       ├── 05_confusion_matrix_original.png
│       ├── 06_precision_vs_recall.png
│       ├── 07_precision_by_organism.png
│       └── 08_confusion_matrix.png
└── scripts
    ├── 01_MobileNetV2.ipynb
    └── 02_BaselineModel.ipynb
```
**Folder and File Descriptions**

- `data/` — Contains the link to the Google Drive image dataset used to train, validate, and test the marine organism classification models.
    - `Data Link`: Provides access to the Google Drive image dataset, which contains images already split into training, validation, and test sets.
    - `README.md`: Provides additional documentation and instructions for accessing and using the dataset.

- `output/` — Contains figures generated during exploratory data analysis (EDA), model training, and model evaluation.
    - `EDA plots/`: Contains visualizations of dataset characteristics, including image availability, aspect ratios, heights, and resolutions.
       -  `01_observation_availability.png`
       -  `02_original_image_aspect_ratios.png`
       -  `02_original_image_heights.png`
       -  `02_original_image_resolutions.png`
  - `MobileNetV2/`: Contains visualizations evaluating MobileNetV2 performance, including misclassified images, F1 scores, confusion matrices, precision, and recall.
      - `
    - `CNN/`: Contains visualizations of the baseline CNN model's training accuracy and confusion matrix.
    - `11_organism_precision_comparison.png`: Compares classification precision across organism categories for both models.
    - `12_overall_accuracy_comparison.png`: Compares the overall test accuracy of both classification models.

- `scripts/` — Contains the Jupyter notebooks used to prepare data, train, evaluate, and compare the marine organism classification models.
    - `01_MobileNetV2.ipynb`: Implements the MobileNetV2 transfer learning model, including data preparation, model training, evaluation, and generation of performance visualizations.
    - `02_BaselineModel.ipynb`: Implements a baseline convolutional neural network (CNN) for marine organism classification and evaluates its performance for comparison with MobileNetV2.

- `README.md` — Provides an overview of the project, its organization, software requirements, dataset access instructions, and steps for reproducing the analysis.

- `LICENSE` — Specifies the terms under which the project's code and other covered materials may be used, modified, and distributed.

### Instructions for Reproducing the Results

The following steps describe how to access the dataset, run the classification models in Google Colab, and generate the results.

#### Step 1: Set Up the Dataset

1. Navigate to the **Data Link** provided in the `data/` folder of this repository.
2. Open the linked Google Drive folder containing the marine organism image dataset.
3. Make a copy of the entire folder and save it to your own Google Drive.
4. Keep the original folder organization, including the training, validation, and test image directories.

#### Step 2: Open the Notebooks in Google Colab

The `scripts/` directory contains two Jupyter notebooks:

- `01_MobileNetV2.ipynb`: Implements the MobileNetV2 transfer learning model.
- `02_BaselineModel.ipynb`: Implements the baseline convolutional neural network (CNN) for comparison.

For each notebook:

1. Navigate to the `scripts/` directory in this GitHub repository.
2. Open the desired `.ipynb` file and select **Open in Colab** (or download the notebook and upload it directly to [Google Colab](https://colab.research.google.com/)).
3. Connect your Google account and authorize Google Drive access when prompted.
4. Update the Google Drive folder path in the notebook, if necessary, to point to your copied dataset.
5. Run all notebook cells in order by selecting **Runtime → Run all**.

Repeat these steps for the second notebook.

#### Step 3: Generate and Review the Results

Both notebooks train and evaluate their respective classification models using the same dataset. The notebooks generate visualizations and evaluation metrics to assess model performance, including accuracy, confusion matrices, precision, recall, and F1 scores.

Generated figures and model results are automatically saved to the designated project folders in your Google Drive. The `output/` directory in this repository contains the figures generated for our final analysis.

The comparative visualizations evaluate MobileNetV2 performance against the baseline CNN using overall test accuracy and organism-level precision.

### Project Workflow

```text
Access Google Drive Dataset
        ↓
Make a Copy of the Dataset in Your Google Drive
        ↓
Open Jupyter Notebooks in Google Colab
        ↓
Connect Google Drive and Update Dataset Path
        ↓
Run MobileNetV2 Notebook
        ↓
Run Baseline CNN Notebook
        ↓
Generate and Save Model Results to Google Drive
        ↓
Review Performance Metrics and Comparative Figures```

**References**
[1] X. Liu, Z. Jia, X. Hou, M. Fu, L. Ma, and Q. Sun, “Real-Time Marine Animal Images
Classification by Embedded System Based on Mobilenet and Transfer Learning,” in
OCEANS 2019 - Marseille, IEEE, June 2019, pp. 1–5. doi: 10.1109/oceanse.2019.8867190.
[2] “iNaturalist,” iNaturalist. Accessed: Nov. 04, 2026. [Online]. Available:
https://www.inaturalist.org/
