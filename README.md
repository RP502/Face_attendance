# Face Attendance System

This guide helps you set up and run the Face Attendance system using a pre-configured repository. Follow the steps below to prepare and use the system.

## Step 1: Clone the Repository and Prepare Directories
Open the Command Prompt (CMD) and run the following command to clone the repository:
```bash
git clone https://github.com/RP502/Face_attendance.git
```
Inside the Face_attendance directory:

Create a folder named Dataset.
Inside Dataset, create a folder named FaceData.
Within FaceData, create two subfolders: raw and processed.
Create a folder named Models. This folder will be used later to store the trained model.

## Step 2: Prepare Training Images
Place all image folders for training into the raw folder created above.

## Step 3: Install Dependencies
Run the following command to install the necessary libraries:
```bash
pip install -r requirements.txt
```
## Step 4: Preprocess Images
To preprocess the images for training, run the following command:
```bash
python src/align_dataset_mtcnn.py Dataset/FaceData/raw Dataset/FaceData/processed --image_size 160 --margin 32 --random_order --gpu_memory_fraction 0.25
```
## Step 5: Download Pre-trained Model
Download and extract the pre-trained model from the link below, then place it into the Models directory:
Download Pre-trained Model
## Step 6: Train the Face Recognition Model
To train the model for face recognition, run the following command:
```bash
python src/classifier.py TRAIN Dataset/FaceData/processed Models/20180402-114759.pb Models/facemodel.pkl --batch_size 1000
```
## Step 7: Run the Program
To start the face recognition program, execute:
```bash
python src/face_rec_cam.py
```
