# AI Lab: Deep Learning for Computer Vision - Medical Image Generation

This repository contains a series of Jupyter Notebooks and a Python web application from the **WorldQuant University "AI Lab: Deep Learning for Computer Vision"** course. The project guides you through the process of understanding, building, and deploying Generative Adversarial Networks (GANs) for creating synthetic medical images.

The labs progress from foundational Python concepts to building a complete GAN from scratch, leveraging pre-trained models, and finally, deploying a user-friendly web application with Streamlit.

## 📚 Project Contents

The repository is structured into weekly labs, each focusing on a different aspect of the project.

###  Week 1: `Week1.ipynb` - Interacting with the Command Line

This notebook serves as an introduction to executing command-line interface (CLI) commands directly from Python.
- **Key Concepts:**
  - Using `os.system` and `subprocess.run` to execute shell commands.
  - Understanding and handling exit status codes to check for successful command execution.
  - Debugging common issues like permission errors (`chmod`) and typos in commands.
  - Capturing the output of system commands for use within a Python script.

### Week 2: `Week2.ipynb` - Building a GAN from Scratch with PyTorch

This lab dives into the theory and implementation of a Generative Adversarial Network (GAN) using PyTorch. The goal is to generate synthetic medical images (brain MRIs).
- **Key Concepts:**
  - **Generator Network:** A deep learning model that takes a random noise vector as input and upsamples it to create a synthetic image.
  - **Discriminator Network:** A classifier model that attempts to distinguish between real images (from the dataset) and fake images (from the generator).
  - **Adversarial Training:** The process of training the generator and discriminator simultaneously, where the generator's goal is to fool the discriminator, and the discriminator's goal is to get better at catching fakes.
  - Setting up data loaders, optimizers (`AdamW`), and loss functions (`BCELoss`) for a GAN architecture.

### Week 3: `Week3.ipynb` - Leveraging Pre-trained GANs with `medigan`

This notebook introduces the `medigan` library, a powerful toolkit for accessing a collection of pre-trained GANs for medical image synthesis.
- **Key Concepts:**
  - Searching and filtering available models in `medigan` based on modality (e.g., X-ray, MRI), organ, and other tags.
  - Generating high-quality synthetic medical images and corresponding segmentation masks using `medigan`.
  - **Transfer Learning:** Using the generated data to train a pre-trained segmentation model (`DeepLabV3_ResNet50`) to perform a new task: polyp detection in endoscopic images.

### Week 4: `Week4.ipynb` & `app.py` - Building a Web App with Streamlit

The final lab focuses on deploying the project as an interactive web application using the Streamlit framework.
- **Key Concepts:**
  - Structuring a Python script for a Streamlit application.
  - Creating UI components like dropdowns (`st.selectbox`), numeric inputs (`st.number_input`), and buttons (`st.button`).
  - Integrating the `medigan` image generation functionality into the web app.
  - Building a user-friendly interface that allows users to select a GAN model, specify the number of images, and view the generated results directly in their browser.

## 🚀 Getting Started

Follow these instructions to set up the project environment and run the code on your local machine.

### Prerequisites

- Python 3.8+
- `pip` package manager

### Installation

1.  **Clone the repository:**
    ```bash
    git clone <your-repository-url>
    cd <repository-directory>
    ```

2.  **Create and activate a virtual environment (recommended):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3.  **Install the required dependencies:**
    A `requirements.txt` file is recommended. You can create one with the following content and install it.
    ```
    # requirements.txt
    torch
    torchvision
    numpy
    matplotlib
    medigan
    streamlit
    tqdm
    ```
    Install the packages using pip:
    ```bash
    pip install -r requirements.txt
    ```
    *Note: If you have a CUDA-enabled GPU, you may need to install a specific version of PyTorch. Please refer to the [official PyTorch website](https://pytorch.org/get-started/locally/) for instructions.*

### Running the Notebooks

To explore the weekly labs, start a Jupyter server:
```bash
jupyter notebook
```
Then, open `Week1.ipynb`, `Week2.ipynb`, or `Week3.ipynb` from the Jupyter interface in your browser.

### Running the Streamlit Web App

The final application is in the `app.py` file. To run it, execute the following command in your terminal:
```bash
streamlit run app.py
```
Your browser should automatically open a new tab with the running application. Here, you can select a medical imaging model, choose the number of images to generate, and see the results instantly.

## ⚖️ License and Attribution

This project is based on materials provided by WorldQuant University.

---
This file © 2024 by [WorldQuant University](https://www.wqu.edu/) is licensed under [CC BY-NC-ND 4.0](https://creativecommons.org/licenses/by-nc-nd/4.0/).