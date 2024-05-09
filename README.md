# Microplastics-in-Sewage

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
- `data/0_train/`: Images with microplastics for train set.
- `data/0_train_bi/`: Mask training images for binary segmentation with a microplastic probability assigned as 0 or 1.
- `data/0_train_instance/`: Instance mask images for training set. \[255, 0, x\] is fragment and \[255, 100, x\] is fiber, and 'x' is a unique id starting at 0. You can load as np.load("---.npz")\['data'\]
- `data/1_valid/`: Images with microplastics for valid set.
- `data/1_valid_bi/`: Mask validation images for binary segmentation with a microplastic probability assigned as 0 or 1.
- `data/1_valid_instance/`: Instance mask images for valid set. \[255, 0, x\] is fragment and \[255, 100, x\] is fiber, and 'x' is a unique id starting at 0. You can load as np.load("---.npz")\['data'\]
- `data/2_test/`: Images with microplastics for test set.
- `data/2_test_bi/`: Mask test images for binary segmentation with a microplastic probability assigned as 0 or 1.
- `data/2_test_instance/`: Instance mask images for test set. \[255, 0, x\] is fragment and \[255, 100, x\] is fiber, and 'x' is a unique id starting at 0. You can load as np.load("---.npz")\['data'\]

- image: 24bit RGB PNG 
- binary mask: 24bit RGB PNG, 0 is background, and 1 is microplastics. 
- instance mask: npz file, key is 'data'. You can load as np.load("---.npz")\['data'\]

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


