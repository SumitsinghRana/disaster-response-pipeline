# Disaster Response Pipeline Project

## Table of Contents
- [Overview](#overview)  
- [Project Structure](#project-structure)  
- [Setup Instructions](#setup-instructions)  
- [How to Use](#how-to-use)  
- [Application Snapshots](#application-snapshots)  
- [Credits](#credits)  

---

## Overview

This project is part of the **Udacity Data Scientist Nanodegree**, developed in collaboration with Figure Eight. The goal is to build a machine learning pipeline that classifies real-time messages received during natural disasters. This allows emergency response teams to quickly identify and prioritize aid based on message content.

The solution also includes a web interface where end users (e.g., responders or coordinators) can enter a message and receive its classification across multiple emergency-related categories.

---

## Project Structure

The repository is organized into three key directories:

### 1. [`app/`](app/)
- `run.py`: Launches the Flask web app.  
- `templates/`: Contains the HTML files (`master.html` and `go.html`) for rendering the web interface.

### 2. [`data/`](data/)
- `disaster_messages.csv`: Raw messages dataset.  
- `disaster_categories.csv`: Category labels for messages.  
- [`process_data.py`](data/process_data.py): Script to clean and transform the raw data, saving it into an SQLite database.  
- [`ETL Pipeline Preparation.ipynb`](data/ETL%20Pipeline%20Preparation.ipynb): Jupyter Notebook outlining the data preprocessing steps.  
- `DisasterResponse.db`: The resulting SQLite database after preprocessing.

### 3. [`models/`](models/)
- [`train_classifier.py`](models/train_classifier.py): Builds and trains a multi-output classification model, then saves it as a pickle file.  
- `classifier.pkl`: The trained model file used by the web app.  
- [`ML Pipeline Preparation.ipynb`](models/ML%20Pipeline%20Preparation.ipynb): Notebook containing initial model exploration and experimentation.

---

## Setup Instructions

This project requires **Python 3.5 or higher** and should run smoothly with any standard Anaconda Python distribution.

#### Steps to get started:

1. **Run the data pipeline**  
   ```bash
   python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/DisasterResponse.db
   
2. **Train the machine learning model**
   ```bash
   python models/train_classifier.py data/DisasterResponse.db models/classifier.pkl

3. **Launch the web application**
   Navigate into the app/ folder and run:
   ```bash
   python run.py
   
4. View the app
   Open your browser and visit:
   http://0.0.0.0:3001/
   
