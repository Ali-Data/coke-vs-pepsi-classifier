# Coke vs. Pepsi: An End-to-End Image Classifier

![fastai](https://img.shields.io/badge/Made%20with-fastai-blue.svg)
![Python](https://img.shields.io/badge/Python-3.9%2B-blue.svg)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)

An end-to-end deep learning project to train and evaluate a computer vision model capable of distinguishing between Coca-Cola and Pepsi products. This project demonstrates a full, iterative machine learning workflow, achieving a final **accuracy of 96.5%** on a held-out test set.

This project was developed by following the methodologies taught in the [fast.ai "Deep Learning for Coders"](https://course.fast.ai/) book.

---

## **Project Goal**

The objective of this project was to build a robust image classification model that can accurately identify whether an image contains a Coca-Cola or a Pepsi product. This serves as a practical example of creating a custom dataset from a real-world source (Kaggle), training a model, analyzing its errors, and iteratively improving its performance with advanced techniques.

---

## **Workflow & Process**

The project followed a standard, professional machine learning workflow:

1.  **Data Collection & Preparation:**
    * The dataset of Coke and Pepsi images was sourced from a public Kaggle dataset.
    * The `fastai` **DataBlock API** was used to create a flexible and robust data pipeline, reading labels directly from the filenames.
    * The **presizing** technique with data augmentation (`aug_transforms`) was applied to efficiently prepare images for the model.

2.  **Iterative Model Training & Refinement:**
    * **Baseline Model:** An initial `resnet34` model was trained using a simple `fine_tune` command, achieving a baseline accuracy of **91.3%**.
    * **Error Analysis:** `ClassificationInterpretation` was used to analyze the model's mistakes, particularly with `plot_top_losses`, which was crucial for identifying mislabeled images.
    * **Interactive Data Cleaning:** The `ImageClassifierCleaner` widget was used to review, delete, and correct problematic images in the dataset.
    * **Advanced Training:** A new model was trained on the cleaned data using a more controlled, two-stage **freeze/unfreeze** strategy with discriminative learning rates. This advanced technique improved the final accuracy significantly.

3.  **Final Evaluation:**
    * The final, improved model was evaluated on a held-out **test set** to get an unbiased measure of its real-world performance, confirming the final accuracy of **96.5%**.

---

## **Final Results**

The advanced training strategy on the cleaned dataset was the clear winner, outperforming the baseline model by over 5%.

* **Baseline Model Accuracy (Simple `fine_tune`):** `91.30%`
* **Final Model Accuracy (Advanced Freeze/Unfreeze):** `96.52%`

This demonstrates the significant value of careful data cleaning and advanced fine-tuning techniques.

### **Confusion Matrix on Test Set**
*(You can add a screenshot of your final confusion matrix here)*

---

## **How to Run**

1.  Clone this repository:
    ```bash
    git clone [https://github.com/your-username/coke-vs-pepsi-classifier.git](https://github.com/your-username/coke-vs-pepsi-classifier.git)
    ```
2.  Install the necessary libraries. The core dependency is `fastai`.
    ```bash
    pip install "fastai[vision]"
    ```
3.  Open the main Jupyter Notebook (`.ipynb`) and run the cells. The notebook contains the full, documented code from data preparation to final evaluation.

---

## **License**

This project is licensed under the MIT License. See the `LICENSE` file for details.
