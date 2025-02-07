## README

### Folder Structure
This project is organized into the following folders:

**Datasets:** This folder contains the datasets required for the model.

**Original Data\development:** Contains the development dataset.
**Preprocessed Data:** Contains the training dataset used to train the model.
Model: This folder contains a Jupyter notebook with the model implementation. The notebook is fully commented to guide you through the model creation, training, and evaluation process.

**Input:** To receive predictions from the model, place both the dataset you want to predict and its corresponding audio files in this folder.

**Predictions:** After running the model, the predictions will be saved in this folder. You can find the output here once the model has completed the prediction process.

### How to Use
Prepare the Input Folder:

Place your dataset and audio files that you wish to predict in the Input folder.
Ensure the audio files are correctly matched with the dataset (i.e., the dataset should reference the correct audio files).
Run the Model:

Open the model notebook in the Model folder.
Run the notebook to train and generate predictions. Make sure the paths to the input data are correctly referenced in the code.
Check the Predictions:

After the model has finished running, check the Predictions folder for the output. The predicted values will be saved here.