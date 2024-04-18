# Microplastics-in-Sewage

## Overview
This GitHub repository is dedicated to sharing the datasets used in the research on "Using a Sewage Microplastic Collection Device for Organic Material Removal and Microplastic Separation". There are two primary datasets available:

- **Segmentation Dataset**: This dataset is used to identify the exact locations of microplastics.
- **Detection Dataset**: This dataset is used to detect the presence of microplastics.

Each dataset has been processed for specific purposes and is published to enhance the reliability and reproducibility of our research.

## Download the Datasets
You can download the datasets using the following links:

For detection:
[Download](https://drive.google.com/file/d/16AxDVzRzm6eEe8APx02x6eWGrGx8cmmz/view?usp=sharing)

For segmentation:
[Download](https://drive.google.com/file/d/1-VEBTmn7p71ZTuyMgiD5qY13pBLq_XCN/view?usp=sharing)

## Data Structure
### Segmentation Dataset
The Segmentation Dataset includes the following file structure:
- `data/plain/512/`: Contains 512-cropped images with microplastics.
- `data/seg/512/`: Contains 512-cropped segmentation masks corresponding to each image.
- `data/plain/og/`: Contains original images with microplastics.
- `data/seg/og/`: Contains original segmentation masks corresponding to each image.

- plain(image): 24bit RGB PNG, 512x512x3 
- seg(mask): 

### Detection Dataset
The Detection Dataset includes the following file structure:
- `*/*.tfrecord`: Contains images and detection labels that follow YOLO.
- `how_to_parse`: Contains how to parse the dataset for detection.

- image: 224x224x3, uint8
- label: 16x16x6x7, float32, (grid_y, grid_x, default_boxes, box), for last dimension: box(x,y,w,h,confidence,Fragment,Fiber)

## Usage Instructions
Before using the datasets, please refer to the `README.md` files in each dataset directory to understand the characteristics and usage guidelines.

## License
These datasets are provided under a [CC BY-NC-SA](https://creativecommons.org/licenses/by-nc-sa/4.0/) license. When using the data, attribution must be made.

## Contact Information
For more information or questions about the research, please contact us via the following email:
- Email: [sun@cnu.ac.kr](mailto:sun@cnu.ac.kr)
