# SMDD-Synthetic-Face-Morphing-Attack-Detection-Development-dataset
Official repository of the paper Privacy-friendly Synthetic Data for the Development of Face Morphing Attack Detectors

*** Accepted at CVPR workshops 2022 ***

![grafik](https://user-images.githubusercontent.com/85616215/158406086-b413c5b9-e4da-4e0e-be01-4de71d279979.png)

# Morph Detect: AI Solution for Detecting Biometric Face Morphing Attacks

This project aims to develop an AI-driven solution for identifying manipulated biometric facial images and detecting biometric face morphing attacks. The goal is to achieve a high detection rate while reducing false-positive cases.

## Project Details

- Duration: January 2023 to April 2023
- Associated with Northeastern University
- Collaborated with Kingdom Capital, MO under the mentorship of Mr. Ernest Smiley

## Project Highlights

- Developed an AI-driven solution for detecting manipulated biometric facial images, resulting in an 80% reduction in false-positive cases and achieving a high detection rate of 95%.
- Trained and evaluated the MixFaceNet model using the CASIA Web-face dataset, which consists of over 25,000 real and synthetic images. The model achieved an accuracy of 98.5% and an F1 score of 0.95 in identifying attacked biometric facial images.
- Implemented the Morph Detect project using CUDA and the latest PyTorch version, resulting in a 50% increase in processing speed. The project utilized MixFaceNet, a deep learning network specifically designed for detecting face morphing attacks. MixFaceNet outperformed VGG16 and ResNet50 models in terms of efficiency and accuracy.

## Repository Structure

- `/Code Files/`: Contains the code files for the Morph Detect project.
- `/Input Files/`: Includes the input files required for running the code.
- `/DataSet/`: Holds the CASIA Web-face dataset used for training and evaluation.

## License

This project is licensed under the Apache License 2.0. Please see the [LICENSE](LICENSE) file for more details.

## Contact Information





The training data split of the SMDD data can be downloaded from this [LINK](https://drive.google.com/file/d/1I6x_gWtu3WxOloK8k-tecXjV3XsRPYYO/view?usp=sharing) (please share your name, affiliation, and official email in the request form).

The testing data split of the SMDD data can be downloaded from: (to be uploaded)

The pretrained weight of MixFaceNet-MAD model on SMDD training data can be downloaded from this [LINK](https://drive.google.com/file/d/1qw6YZ3cpaa9UK2-hRfzKWx5rPvRo0h63/view?usp=sharing) (please share your name, affiliation, and official email in the request form).

## Data preparation
Our face data is preprocessed by the face detection and cropping. The implementation can be found in image_preprocess.py file.
Moreover, for further training and test, the corresponding CSV files should be generated. The format of the dataset CSV file in our case is:
```
image_path,label
/image_dir/image_file_1.png, bonafide
/image_dir/image_file_2.png, bonafide
/image_dir/image_file_3.png, attack
/image_dir/image_file_4.png, attack
```
## Experiment
The main.py file can be used for training and test:
1. When training and test:
    ```
    python main.py \
      --train_csv_path 'train.csv' \
      --test_csv_path 'test.csv' \
      --model_path 'mixfacenet_SMDD.pth' \
      --is_train True \
      --is_test True \
      --output_dir 'output' \
    ```
2. When test by using pretrained weight, first download the model and give the model path:
    ```
    python main.py \
      --test_csv_path 'test.csv' \
      --model_path 'mixfacenet_SMDD.pth' \
      --is_train False \
      --is_test True \
      --output_dir 'output' \
    ```
More detailed information can be found in main.py.

##

**Citation:**

If you use SMDD dataset, please cite the following [paper](https://arxiv.org/abs/2203.06691):

```
@article{SMDD,
    author    = {Damer, Naser and L\'opez, C\'esar Augusto Fontanillo and Fang, Meiling and Spiller, No\'emie and Pham, Minh Vu and Boutros, Fadi},
    title     = {Privacy-Friendly Synthetic Data for the Development of Face Morphing Attack Detectors},
    booktitle = {Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR) Workshops},
    month     = {June},
    year      = {2022},
    pages     = {1606-1617}
}
```
For any inquiries or further information, please contact:
Email: yashwanthbalan75@gmail.com
