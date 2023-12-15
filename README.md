# MRI-Brain-Tumor-Classification

MRI Brain Tumor Classification using Supervised Machine Learning with the K-nn method written in Python.


## About The Project

### Abstract 
Brain tumors, affecting both children and adults, comprise 85-90% of primary Central Nervous System (CNS) tumors, with around 11,700 annual diagnoses. The 5-year survival rates for cancerous brain or CNS tumors are 34% for men and 36% for women. Proper treatment, planning, and accurate diagnostics are crucial for improving life expectancy. For now, Magnetic Resonance Imaging (MRI) detection technique and its large amount of image data generated remains the best solution, however, manual examination is error-prone due to the complexities of brain tumors, emphasizing the need for advanced diagnostics.

### What is a brain tumor ?
A brain tumor is an aberrant accumulation of cells within the brain, categorized as either cancerous (malignant) or noncancerous (benign). The rigid enclosure of the skull intensifies the impact of these growths, as their expansion within this confined space raises intracranial pressure. This heightened pressure poses risks, potentially causing brain damage and presenting a life-threatening scenario.

### Context 
Brain tumors present a complex challenge due to variations in size and location. Understanding their nature becomes especially challenging, requiring the expertise of a professional neurosurgeon for MRI analysis. In developing countries, the scarcity of skilled doctors and limited knowledge about tumors exacerbate the issue, making the generation of MRI reports both challenging and time-consuming. Introducing an automated cloud-based system is a potential solution to address these challenges and streamline the diagnostic process.


## Getting Started
Here you are provided instructions on how to use this repository to recreate your project locally.

### Development Environment
| Package Name | Version |
| --- | ----------- |
| ```ubuntu``` | 20.04 |
| ```python``` | 3.7.12 |
| ```numpy``` | 1.24.4 |
| ```scikit-learn``` | 1.3.2 |
| ```scikit-image``` | 0.21.0 |

### Installation
<ol>
  <li>Clone the repository (git clone https://github.com/deemd/MRI-Brain-Tumor-Classification.git)</li>
  <li>Setup (and activate) your environment</li>
</ol>


## Usage

### Dataset

<img src='https://github.com/deemd/MRI-Brain-Tumor-Classification/assets/146414960/abc7f4e4-019e-49e8-9cab-5678122e981e' width=180 height=auto />
<br><br>
This dataset contains <strong>3264</strong> images of human brain MRI images which are classified into 4 classes:
<ul>
  <li>Glioma Tumor</li>
  <li>Meningioma Tumor</li>
  <li>Pituitary Tumor</li>
  <li>No Tumor</li>
</ul>
In this project we will only have access to the Training folder, and as such, we will consider about 30% of the images as intended for model testing and the rest for model training. 
<br><br>

> [!NOTE]
> Pay attention that the size of the images in this dataset is different. To avoid some issues with the lattest, an automatic resizing of each image is implemented.

### Model
Selected sckit-learn model for MRI Brain Tumor Classification : ```sklearn.neighbors.KNeighborsClassifier```<br>
The KNeighborsClassifier is a <strong>supervised machine learning algorithm</strong> based on the k-nearest neighbors principle. It classifies a data point based on the majority class of its k-nearest neighbors. <br>
In the context of brain tumor classification, the algorithm's flexibility in capturing complex relationships in image data makes it well-suited. The choice is grounded in its ability to handle intricate patterns often present in medical images, offering a promising approach for identifying tumor characteristics in MRI scans. <br>
You can find more about the KNeighborsClassifier model on the online scikit-learn documentation, or on the sklearn repository (```sklearn/neighbors/_classification.py```).

### Hyperparameters 
After testing with cross validation and Grid Search techniques, the tuning of hyperparameters chosen for the KNeighborsClassifier is described as follows:
* ```n_neighbors=2``` : This parameter specifies the number of neighbors to consider during classification. A lower value was chosen to allow the model to be sensitive to local variations in the image data.
* ```weights='distance'``` : The choice of 'distance' assigns weights to neighbors based on their distance to the query point. This way, closer neighbors have a stronger influence on the classification, which is advantageous for capturing fine details in image data.
* ```algorithm='auto'``` : The 'auto' setting automatically selects the most suitable algorithm for the given dataset. It adapts to the characteristics of the MRI image data for optimal performance.
* ```leaf_size=30``` : This parameter affects the speed of the algorithm but does not significantly impact accuracy. A standard value was chosen for efficiency.
* ```p=3``` : The Minkowski distance metric parameter with p=3 corresponds to the use of the L3 norm, which is suitable for three-dimensional data like MRI images.
* ```metric='minkowski'``` : This parameter specifies the distance metric used for the k-neighbors query. 'Minkowski' is a generalization of Euclidean and Manhattan distances and is suitable for multidimensional data.
* ```n_jobs=-1``` : Setting n_jobs to -1 allows the algorithm to utilize all available CPU cores, accelerating the computation process for large datasets.

### Use 
The tuned KNeighborsClassifier is utilized for Brain Tumor Classification using labeled MRI images across four classes. Applying the k-nearest neighbors approach, the model classifies new MRI images based on proximity in the feature space. Hyperparameter choices aim to enhance sensitivity to local patterns. The implementation involves training on a labeled dataset, cross-validation for validation, and deployment for accurate predictions on new, unseen MRI images in brain tumor classification.


## Roadmap
- [x] Implement a model using scikit-learn library
- [ ] Introduce new data using Kaggle
- [ ] Implement data augmentation using keras
- [ ] Compare scikit-learn knn model with keras' one


## Contribution
Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are greatly appreciated. <br>
If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement". Thanks again !
<ol>
  <li>Fork the Project</li>
  <li>Create your Feature Branch (git checkout -b feature/AmazingFeature)</li>
  <li>Commit your Changes (git commit -m 'Add some AmazingFeature')</li>
  <li>Push to the Branch (git push origin feature/AmazingFeature)</li>
  <li>Open a Pull Request</li>
</ol>
Make sure to add a detailed README File.

## License
Distributed under the MIT License. See ```LICENSE.txt``` for more information.


## Author Contact 
Héloïse Robin (헬로이스 로빈) - heloise.robin.pro@gmail.com <br>
Project Link: https://github.com/deemd/MRI-Brain-Tumor-Classification



