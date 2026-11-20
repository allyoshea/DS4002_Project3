Instructions for this data:

Copy and paste this Google Drive link into your browser, which will navigate you to their page.
Click on the "Organize" button, and create a shortcut in your personal Google Drive. This allows you to use the data without downloading a large file.

# Metadata 
## Data Summary 

Our dataset contains images of 12 marine organism categories, including marine mammals, fish, invertebrates, a sea turtle, and kelp. We use these images to train and evaluate a MobileNetV2 classifier, with a target test accuracy of at least 90%. Images are the model inputs, and category folder names provide the target labels. Taxon IDs, locations, and contributor information are metadata, not predictors.

Data files include:

README.md: Describes the dataset, its sources, and its uses.

Data Link: Contains the Google Drive link for the image dataset.

Marine_Classification/train/: Contains 4,200 training images in 12 category folders.

Marine_Classification/validation/: Contains 900 validation images in the same 12 category folders.

Marine_Classification/test/: Contains 900 testing images in the same 12 category folders.

Marine_Classification/failed_downloads.csv: Download error log. The supplied file is empty and contains no recorded failures.

The Drive folder also contains mobilenetv2_pretrained.keras, the saved model, and Model_Results/, which holds confusion matrices, precision, recall, F1-score, and misclassified-image figures. Copies of f1_score_by_organism.png, confusion_matrix.png, and precision_vs_recall.png also appear directly inside Marine_Classification.

The downloaded data are RGB JPEG images with different dimensions. During model loading, the images are resized to 224 × 224 pixels and MobileNetV2 preprocessing scales their pixel values to −1 to 1. These model inputs are created in memory and a separate resized image collection is not stored in Drive.

## Provenance
The dataset was collected between November 4th and November 13th, 2026, by three University of Virginia students (Carter Grohe, Coco Zhao, and Ally O'Shea) for their Data science project (aka Prototyping) DS 4002 class. Species were manually found on iNaturalist and verified then the python requests package was used to download the images from the URL and compiled into one dataset linked in the google drive above. EDA was further conducted on this dataset which is available in the GitHub above, image data in google drive above.  

## Ethical Statements
The dataset consists of publicly available individuals’ image and does not have private information. However, original images remain subject to the rights and policies of the original publishers.  

## License
The images used in this project were obtained from iNaturalist which retains rights to the individuals who uploaded the images. As such, the copyright and licensing terms fall under the Creative Commons Attribution-NonCommercial (CC BY-NC) license. This allows other people (such as researchers, educators, or the public) to use these photos without asking permission, provided they give you credit and do not make money from them. Following this, we do not claim ownership of the original content. The code, metadata, and analysis are original project materials shared through the GitHub repository.  

## Data Dictionary

| Variable | Description | Data Type | Uncertainty |
|---|---|---|---|
| `Taxon_ID` | Animal's taxonomic ID in iNaturalist | Numeric (identifier) | Low |
| `Scientific_Name` | Latin name of the genus and species | Character (descriptive) | Low |
| `Common_Name` | Common name of the animal | Character (descriptive) | Low |
| `Taxonomic_Rank` | Taxonomic classification (species, genus, etc.) | Character (categorical) | Low |
| `Available_Observations` | Number of usable, licensed observations available for the animal | Numeric (predictor) | Medium |
| `Valid_Images` | Number of downloaded images that can be opened and processed | Numeric | Low |
| `Image` | The original image downloaded from iNaturalist | Image | Variable |
| `Image (224 x 224)` | The image used in the model | Image | Medium |

## Exploratory Plots
<img width="1442" height="700" alt="image" src="https://github.com/user-attachments/assets/f6c7aeb4-5f76-4781-9cc4-04186281a31c" />

<img width="1516" height="778" alt="image" src="https://github.com/user-attachments/assets/da4d7e6b-1bc5-4076-9af7-9bd7ca8b59d1" />
