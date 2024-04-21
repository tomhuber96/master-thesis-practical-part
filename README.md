# Master thesis practical part

## Contact

If you have questions to the thesis please message me per email 'thomashuber96@gmail.com'.

## structure

- azure
- datasets 
  - gabor
    - preprocessed_datasets
      - gabor
      - retailrocket
  - Retailrocket Recommender System dataset
- DL
- EDA
- models
- open_ai
- RL
- testing
- tutorials

## Guide

The dataset folders need to be created, as the dataset would be to large for git.

To train the models under DL the preprocessing has to be done first. 
For that run the notebooks under EDA. 
1) detail_rocket_eda.ipynb
2) gabor_eda.ipynb
3) gabor-only-products-remove-variants.ipynb
4) gabor_user_item_interactions.ipynb

These notebooks will create the preprocessed datasets in the folder datasets/gabor/preprocessed_datasets/gabor and datasets/gabor/preprocessed_datasets/retailrocket.

To use the OpenAI notebooks an OpenAI API key has to be added to .env.local.

To use Amazon Personalize use the files in EDA/AWS to prepare the datasets. 
The generated files can be found in datasets/preprocessed_datasets. 
These files can be uploaded to an S3 bucket in AWS.


The folders azure, RL, testing and tutorials are not used in the thesis and can be seen as legacy code. 



