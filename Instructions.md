# NeurologIQ_Data
Data Set and project description for testing candidates at NIQ.

# Instructions:

This repository contains the basic information for you to develop your first project with us at NIQ. This project will give you an idea of how some projects might look like if you work with us.

For your first task, you are required to fork this repository as to get the basic information and develop your project in your own repository by following the sample structure.

**Note:** We highly advice to use Google Colab as main working station, since neither you or us should configure or have special hardware requirements for this project.

## Project description

You are required to identify and count cells. Among your task will be required to:
- **Label data:** Identify how a cell looks like and document the process, e.g., tools used. A sample image is provided. Please note that **"NOT ALL CELLS ARE LABEL ON THE SAMPLE IMAGE".** You shall label as many as you consider necessary
- **Build ML Model:** You can create your own ML model architecture or take an existing model as base
- **Train ML Model:** You shall train the model and save the trained model as file with extension .h5
-**Document the results:** Please write a short *"RESULTS.MD"* where you briefly describe the obtained results

# Keep in mind

You have total freedom to label the data, select the model, methodology at your will. There are no restrictions from our side. The only points you should take in mind are:
- Use TensorFlow (or Keras) as base for your project
- Document the code: It is highly important to have a well documented code for evaluation purposes.

# Evaluation

The evaluation method will be based on accuracy.

We will test your result on predicted images versus the real count of cells per image. Ideally, your model should be able to detect all cells.

The cell counting will be based on percentage out of the real cell number per image.

# Files

*   **CellSample Folder** - the training set
*   **Training** - the test set
*   **Testing** - a sample submission file in the correct format
*   **Sample** - sample image of how to identify cells in the data set
