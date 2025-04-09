# 🐕 Dog Breed Image Classifier

[![Python 3.6+](https://img.shields.io/badge/python-3.6+-blue.svg)](https://www.python.org/downloads/release/python-360/)
[![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=flat&logo=PyTorch&logoColor=white)](https://pytorch.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

<p align="center">
  <img src="https://miro.medium.com/v2/resize:fit:1400/1*oB3S5yHHhvougJkPXuc8og.gif" alt="Dog Breed Classification" width="600"/>
</p>

## 📋 Project Overview
This project implements a dog breed image classifier that uses pre-trained Convolutional Neural Networks (CNNs) to identify dog breeds in images. The system can distinguish between different dog breeds and also identify if an image contains a dog or not.

## 🎭 Project Context
This project was created as a solution for a dog show registration system. The system needs to confirm whether submitted images contain dogs, as some participants might try to register non-dog pets. The classifier helps the registration system by:
- Validating that submitted images contain dogs
- Identifying the specific breed of each dog
- Flagging non-dog images for review

## 🎯 Project Objectives
- Classify images using pre-trained CNN models (VGG, ResNet, and AlexNet)
- Compare the performance of different CNN architectures
- Demonstrate the effectiveness of transfer learning for image classification tasks
- Provide a framework for both batch processing and individual image classification

## 🔍 Technical Overview
The application uses transfer learning with pre-trained CNN models from PyTorch's model zoo. These models have been trained on the ImageNet dataset, which includes millions of images across thousands of categories. By leveraging these pre-trained models, the system can accurately classify dog breeds without requiring extensive training data or computational resources.

Three different CNN architectures are supported:
- **VGG16**: Deep CNN known for its simplicity and effectiveness
- **ResNet**: Residual Network that uses skip connections to allow training of deeper networks
- **AlexNet**: Pioneering CNN architecture that won the ImageNet challenge in 2012

## 📁 Project Structure

### 📜 Main Scripts
- `check_images.py`: Main script that orchestrates the entire classification workflow
- `get_input_args.py`: Handles command line arguments (directory, architecture, dogfile)
- `get_pet_labels.py`: Extracts pet labels from image filenames
- `classify_images.py`: Uses pre-trained models to classify images
- `adjust_results4_isadog.py`: Verifies if classifier correctly detected dog images
- `calculates_results_stats.py`: Calculates performance statistics
- `print_results.py`: Outputs the results

### 📊 Data Files
- `dognames.txt`: List of valid dog names used to determine if classifier correctly identifies dogs
- `imagenet1000_clsid_to_human.txt`: Mapping of ImageNet class IDs to human-readable labels

### 📂 Directories
- `pet_images/`: Contains 40 test images (30 dog breeds and 10 non-dog images)
- `uploaded_images/`: Contains 4 additional test images for customized testing

### 🛠️ Utility Scripts
- `classifier.py`: Implements the core classification functionality using pre-trained models
- `print_functions_for_lab_checks.py`: Contains functions to validate results throughout the process

## 📦 Dependencies
- Python 3.x
- PyTorch
- torchvision
- Pillow (PIL)

## 💻 Installation
```bash
# Clone the repository
git clone https://github.com/almasoriaw/dog-breed-classifier-ml.git

# Navigate to the project directory
cd dog_image_classifier

# Install required dependencies
pip install torch torchvision pillow
```

## 🚀 Usage

### ⌨️ Command Line Arguments
The main script accepts the following command line arguments:
- `--dir`: Directory path containing images to be classified (default: 'pet_images/')
- `--arch`: CNN model architecture to use (choose from: 'vgg', 'resnet', 'alexnet', default: 'vgg')
- `--dogfile`: Text file containing valid dog names (default: 'dognames.txt')

### ▶️ Running the Application
```bash
# Basic usage with default values
python data/check_images.py

# Specifying custom values
python data/check_images.py --dir data/pet_images/ --arch vgg --dogfile data/dognames.txt

# Running with a different model architecture
python data/check_images.py --arch resnet

# Testing uploaded images
python data/check_images.py --dir data/uploaded_images/ --arch vgg --dogfile data/dognames.txt
```

### 📊 Batch Processing
The project includes shell scripts for batch processing:
- `run_models_batch.sh`: Tests all three architectures on the pet images
- `run_models_batch_uploaded.sh`: Tests all three architectures on the uploaded images

## ⚙️ How It Works

### 🔄 Workflow
1. **Label Extraction**: Extract pet labels from image filenames (e.g., "Boston_terrier_02259.jpg" → "boston terrier")
2. **Image Classification**: Classify images using the selected pre-trained CNN model
3. **Dog Verification**: Compare classification results with dognames.txt to determine if images were correctly classified as dogs
4. **Statistics Calculation**: Calculate performance metrics for the classifier
5. **Results Output**: Display results, including various accuracy metrics

### 📈 Key Metrics Reported
- Percentage of correctly classified dog breeds
- Percentage of correctly classified dog images
- Percentage of correctly classified non-dog images
- Overall classification accuracy
- Runtime performance

## 📊 Performance Comparison
The project allows comparison of the three CNN architectures based on:
- Classification accuracy
- Runtime efficiency
- Ability to correctly identify dog breeds vs. general dog identification

## 🔍 Project Applications
- Educational tool for understanding CNN architectures and transfer learning
- Demonstration of image classification techniques
- Framework for building more sophisticated image recognition systems

## 🔮 Future Enhancements
- Web interface for real-time image classification
- Additional CNN architectures for comparison
- Fine-tuning pre-trained models for improved accuracy
- Support for mobile platforms

## 🙏 Credits
- PyTorch for pre-trained models
- ImageNet for the training data used in the pre-trained models

## 👩‍💻 Author
- **Alma Soria**
- **Date**: July 2024
- **LinkedIn**: [Connect with me](https://www.linkedin.com/in/almasoria/)
- **Portfolio**: [View my portfolio](https://github.com/almasoriaw/)

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
