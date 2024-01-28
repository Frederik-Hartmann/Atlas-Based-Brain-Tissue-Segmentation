# A Hybrid Approach for Brain Tissue Segmentation: Integrating Gaussian Mixture Models with Atlas-based and Tissue Modeling Techniques
Authors: [Frederik Hartmann](https://frederik-hartmann.github.io/) and [Xavier Beltran Urbano](https://xavibeltranurbano.github.io/)

## Further Information
More information such as a detailed report and a short summary can be found on [my website](https://frederik-hartmann.github.io).

## Setting Up the Project
1. Clone the project:
  ```bash
  git clone https://github.com/Frederik-Hartmann/Atlas-Based-Brain-Tissue-Segmentation.git
  cd Atlas-Based-Brain-Tissue-Segmentation
  ```
2. Using a virtual environment is strongly recommended.
```bash
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```
## Reproducing the Results
The project utilizes the following folder structure
```
Atlas-Based-Brain-Tissue-Segmentation/
├── images
│ ├── testing-images
│ │ ├── 1003.nii.gz
│ │ ├── ...
│ ├── testing-labels
│ │ ├── 1003_3C.nii.gz
│ │ ├── ...
│ └── testing-mask
│ ├── 1003_1C.nii.gz
│ ├── ...
├── models
│ ├── atlas.nii.gz
│ ├── meanImage.nii.gz
│ └── TissueModel.csv
├── Par0038
│ ├── Par0038affine.txt
│ ├── Par0038bspline.txt
│ └── Par0038rigid.txt
├── src
```
To reproduce the results, execute the following scripts:
```bash
python src/registration.py
python src/segmentationWithoutEM/combinationBoth.py
python src/segmentationWithoutEM/segmentationLabelPropagation.py
python src/segmentationWithoutEM/segmentationTissueModel.py
python src/segmentationEM/initializationTest.py
```
This will produce the registered atlases and segmentations for each image.

