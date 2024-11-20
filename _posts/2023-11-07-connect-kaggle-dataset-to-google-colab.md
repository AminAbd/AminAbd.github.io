---
layout: post
title: "How to Connect a Kaggle Dataset to Google Colab"
date: 2023-11-07
author: "Ameen Abdelmutalab"
tags: [data science, kaggle, google colab, dataset, tutorial]
image: "/assets/img/post_kaggle_colab.png"
categories: LangChain
---

Integrating datasets from Kaggle into Google Colab is a powerful way to simplify your data science workflow. This tutorial will guide you through each step to seamlessly access Kaggle datasets in Colab for your analysis.

## Step 1: Get the Kaggle API Key

1. **Access your Kaggle account settings:**
   - Log in to [Kaggle](https://www.kaggle.com/).
   - Click on your profile picture at the top right, then select **Account**.

2. **Download the API Key:**
   - Scroll down to the **API** section in your account settings.
   - Click **Create New API Token** to download a file called `kaggle.json`, which contains your Kaggle API credentials.

## Step 2: Upload the API Key (`kaggle.json`) to Colab

1. **Upload the `kaggle.json` file:**
   - In your Colab notebook, run the following code to upload `kaggle.json`:

    ```python
    from google.colab import files
    files.upload()  # This will open a file dialog to upload kaggle.json
    ```

2. **Move `kaggle.json` to the correct location:**
   - Once uploaded, move it to the `.kaggle` directory and set permissions:

    ```python
    !mkdir -p ~/.kaggle
    !mv kaggle.json ~/.kaggle/
    !chmod 600 ~/.kaggle/kaggle.json
    ```

## Step 3: Install the Kaggle API in Colab

To make sure the `kaggle` package is available, install it using:

```python
!pip install kaggle

