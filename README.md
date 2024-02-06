# The Double-Edged Sword: Identifying Authentication Pages and their Fingerprinting Behavior (WWW'24)

This repository contains **the data and notebooks** that we used in our paper [The Double-Edged Sword: Identifying Authentication Pages and their Fingerprinting Behavior](https://cosicdatabase.esat.kuleuven.be/backend/publications/files/conferencepaper/3756).

The paper introduces a novel machine learning-based approach for automated identification of authentication pages (i.e. login and signup pages) and measures the prevalence of fingerprinting scripts on those pages.


# Model Training

🕸 We used the TensorFlow framework to
train a multi-class classifier. For each visited page, we generate an 88-dimensional feature vector and a label, which we fed to a neural network with two dense hidden layers containing 8 and 16 units. The output layer is mapped to the three classes, i.e., login, sign-up, and neither. We trained the model for 200 epochs using
the cross-entropy loss function. The notebook along with the required data that we used to train our model made publicly available with this repository.


# Auxiliary data
The auxiliary data we use in the analysis and model training includes the following:

1. 2023_08_25_top_100k_crawl_res_df.csv: Information about the pages that we visited our crawler about whether the page is a login or signup page.
2. 2023_08_25_top_100k_fps.csv: For each visited page, details about fingerprinting scripts such as fingerprinting type, script domain etc.
3. classifiers_comparison_random_sample.csv: Randomly selected 1000 site URLs to measure which login signup page classifier (our ML, Fathom, Autofill, previous heuristics) works better.
4. crux_fqdn_top_100k_202304_with_rank.csv: Rank of URLs that we visited.
5. inner_links.csv: Visited inner links by each homepage we visited.
6. signals.csv: Login and signup related page signals used in model training.




### Reference

```tex
@article{
    author    = {Asuman Senol, Alisha Ukani, Dylan Cutler and Igor Bilogrevic},
    title     = {{The Double Edged Sword: Identifying Authentication Pages and their Fingerprinting Behavior}},
    booktitle = {Proceedings of The Web Conference 2024},
    year      = 2024,
    month     = May
}
```
