# Microplastics-in-Sewage

Github URL : [https://t.ly/zsKPW](https://t.ly/zsKPW)

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

#### For Binary Segmentation
The Binary Segmentation Dataset includes the following file structure:
- `data/0_train/`: Images with microplastics for train set.
- `data/0_train_bi/`: Mask training images for binary segmentation with a microplastic probability assigned as 0 or 1.
- `data/1_valid/`: Images with microplastics for valid set.
- `data/1_valid_bi/`: Mask validation images for binary segmentation with a microplastic probability assigned as 0 or 1.
- `data/2_test/`: Images with microplastics for test set.
- `data/2_test_bi/`: Mask test images for binary segmentation with a microplastic probability assigned as 0 or 1.

#### For Instance Segmentation
The Instance Segmentation Dataset includes the following file structure:
- `data/0_train/`: Images with microplastics for train set.
- `data/0_train_instance/`: Instance mask images for training set. \[255, 0, x\] is fragment and \[255, 100, x\] is fiber, and 'x' is a unique id starting at 0. You can load as np.load("---.npz")\['data'\]
- `data/1_valid/`: Images with microplastics for valid set.
- `data/1_valid_instance/`: Instance mask images for valid set. \[255, 0, x\] is fragment and \[255, 100, x\] is fiber, and 'x' is a unique id starting at 0. You can load as np.load("---.npz")\['data'\]
- `data/2_test/`: Images with microplastics for test set.
- `data/2_test_instance/`: Instance mask images for test set. \[255, 0, x\] is fragment and \[255, 100, x\] is fiber, and 'x' is a unique id starting at 0. You can load as np.load("---.npz")\['data'\]
- 
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

## Citations

### AMA
Lee G, Jung J, Moon S, Jung J, Jhang K. Microscopic Image Dataset with Segmentation and Detection Labels for Microplastic Analysis in Sewage: Enhancing Research and Environmental Monitoring. Microplastics. 2024; 3(2):264-275. https://doi.org/10.3390/microplastics3020016

### Chicago
Lee, Gwanghee, Jaeheon Jung, Sangjun Moon, Jihyun Jung, and Kyoungson Jhang. 2024. "Microscopic Image Dataset with Segmentation and Detection Labels for Microplastic Analysis in Sewage: Enhancing Research and Environmental Monitoring" Microplastics 3, no. 2: 264-275. https://doi.org/10.3390/microplastics3020016

### BibTex

@Article{microplastics3020016, <br>
AUTHOR = {Lee, Gwanghee and Jung, Jaeheon and Moon, Sangjun and Jung, Jihyun and Jhang, Kyoungson},<br>
TITLE = {Microscopic Image Dataset with Segmentation and Detection Labels for Microplastic Analysis in Sewage: Enhancing Research and Environmental Monitoring},<br>
JOURNAL = {Microplastics},<br>
VOLUME = {3},<br>
YEAR = {2024},<br>
NUMBER = {2},<br>
PAGES = {264--275},<br>
URL = {https://www.mdpi.com/2673-8929/3/2/16},<br>
ISSN = {2673-8929},<br>
ABSTRACT = {We introduce a novel microscopic image dataset augmented with segmentation and detection labels specifically designed for microplastic analysis in sewage environments. Recognizing the increasing concern over microplastics—particles of synthetic polymers smaller than 5 mm—and their detrimental effects on marine ecosystems and human health, our research focuses on enhancing detection and analytical methodologies through advanced computer vision and deep learning techniques. The dataset comprises high-resolution microscopic images of microplastics collected from sewage, meticulously labeled for both segmentation and detection tasks, aiming to facilitate accurate and efficient identification and quantification of microplastic pollution. In addition to dataset development, we present example deep learning models optimized for segmentation and detection of microplastics within complex sewage samples. The models demonstrate significant potential in automating the analysis of microplastic contamination, offering a scalable solution to environmental monitoring challenges. Furthermore, we ensure the accessibility and reproducibility 12 of our research by making the dataset and model codes publicly available, accompanied by detailed 13 documentation on GitHub and LabelBox.},<br>
DOI = {10.3390/microplastics3020016}<br>
}





## License
These datasets are provided under a [CC BY-NC-SA](https://creativecommons.org/licenses/by-nc-sa/4.0/) license. When using the data, attribution must be made.


