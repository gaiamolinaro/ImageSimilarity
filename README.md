# Image Similarity

This project looks at creating a simple class for assessing image similarity. 
The approach taken looks to embed images by extracting the final layer feature embeddings from 
pretrained convolution neural networks, before comparing similarity between two images based on Cosine distance.

The class has been written to accomodate some standard neural network architectures, supported by Pytorch's 
torchvision library. At time of publishing these include: resnet50, vgg19, and efficientnet_b0. However, the class 
has deliberately been written in a modular way to accommodate the easy addition of other networks as required.

The main.ipynb contains a brief demonstration of how to utilise the Img2Vec class functionality. 
The class itself can be found in the image_similarity.py module within the "ImgSim" package directory.

## Initial setup
The first thing you are going to want to do is to clone this repository.

```
$ git clone https://github.com/totogot/ImageSimilarity.git
```

Next, set up a virtual environment for installing all package requirements into.

```
$ cd C:\Users\jdoe\Documents\PersonalProjects\image_similarity
$ python -m venv venv
```

Then from within the terminal command line within your IDE (making sure you are in the project folder), you can install all the dependencies for the project, by simply activating the venv and leveraging the setuptools package and the setup.cfg file created in the project repo. 

```
$ .\venv\Scripts\activate
$ pip install --upgrade pip
$ pip install .
```

This last command will install all dependencies outlined in the setup.cfg file. ipykernel has been included to enable the main.ipynb to be run also and for relevant visualisations to be outputted also.

Note: for IDEs where the CLI uses PowerShell by default (e.g. VS Code), in order to run Activate.ps1 you may find that you first need to update your settings such that Command Prompt is the default terminal shell - see here: https://support.enthought.com/hc/en-us/articles/360058403072-Windows-error-activate-ps1-cannot-be-loaded-because-running-scripts-is-disabled-UnauthorizedAccess-


## Usage
For a step-by-step example of the functionality, see the "main.ipynb" file. 
While full documentation can be found in code commentary contained within the "src/ImgSim/image_similarity.py" file


## Data
For the purpose of demonstrating functionality I have included several test images (in this case of different furnitureitesm - tables, sofas, and shelves) 
I curated the dataset to include 10 examples of each category (30 images in total). However, I structured each selected the 10 images in each category, such that there was two themes (with 5 images each). For example, within the "tables" category I included x5 images of coffee tables, and x5 images of dinner tables. 

The purpose of this was to test whether the model could correctly identify the most similar images even within each category - the results can be seen in "main.ipynb" 

*DISCLAIMER: 
The images were sourced from the web, and I do not claim to hold any rights to copyrights or other forms of IP. 
In fact, you could use Google's reverse image search to identify the sources of each image - try out image similarity in a real-world setting!


## Repository formatting
It is worth noting that pre-commit functionality has been included in this repository.
"Flake8" and "black" functionality has been included - specified by .pre-commit-config.yaml file.

If making future edits to a cloned repo, and you wish to access this functionality, you will need to execute the following,
after install all requirements, and prior to making future commits:

```
$ pre-commit install
```