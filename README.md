# Mercado Libre Challenge 2020

https://ml-challenge.mercadolibre.com/

## The Challenge 

Mercado Libre presents millions of publications of products and services. Users browse through them countless times, looking for what they want to buy or simply to find ideas for an upcoming purchase.

Better understanding what may be of interest to them is critical to our business, as we can help them find what they are looking for, providing personalized recommendations based on the publications that are closest to the needs and preferences of each user.

Given the record of a user's browsing period, we challenge you to predict the ten (10) items most likely to be chosen in their next purchase.

## The Code

 - Stack: Python + Keras + TensorFlow + SciKitLearn.
 - Train/Test data: Provided by MercadoLibre in CSV format.
 - Platform: (Windows | Linux) + Laptop with dedicated graphics card.

### Files

#### analyze.py
Analyze & visualize data.

#### re-data.py
Apply regex to raw data and save.

#### models.py
Contains different models to train and predict.

#### ensemble.py
Applies trained models from models.py and performs predictions in an ensemble in order to improve accuracy.

#### model.{sh|ps1}, ensemble.{sh|ps1}
Launchers.

#### config.json
Configuration file.

### Pipeline of a model for training
 1. Read raw datasets from disk.
 2. Parse data with regex and store the new dataset.
 3. Tokenize all the universe of words from titles and categories and add padding.
 4. Store token data in disk. This is the new data.
 5. Load a fraction of the train data into memory, and perform a few epochs training.
 6. Save progress, and process more data from the dataset.
 
Train data is very large (20M rows) to process and load into memory. In order to sweep all the dataset the training loop process fractions of the data a few epochs each, and saves the progress, and so on. Each model consumes about one hour of GPU, and gives 0.8 score individually.
 

## ToDo ##

 - [ ] Modify code to new challenge.
 - [ ] Improve pipeline, models, classes, and modules.
 - [ ] Add new prediction models.
