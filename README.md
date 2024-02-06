# The Double-Edged Sword: Identifying Authentication Pages and their Fingerprinting Behavior (WWW'24)

This repository contains **the data, notebooks and the [model output](https://github.com/asumansenol/double_edged_sword_data/tree/main/multiclass_classifier)** that we used in our paper [The Double-Edged Sword: Identifying Authentication Pages and their Fingerprinting Behavior](https://cosicdatabase.esat.kuleuven.be/backend/publications/files/conferencepaper/3756).

The paper introduces a novel machine learning-based approach for automated identification of authentication pages (i.e. login and signup pages) and measures the prevalence of fingerprinting scripts on those pages.

# ML Pipeline

![ml_pipeline](https://github.com/asumansenol/double_edged_sword_data/assets/48864422/997f73bc-61c6-4935-8183-98a8e4922b9a)

## Model Training
We used the TensorFlow framework to train a multi-class classifier. For each visited page, we generate an 88-dimensional feature vector and a label, which we fed to a neural network with two dense hidden layers containing 8 and 16 units. The output layer is mapped to the three classes, i.e., login, sign-up, and neither. We trained the model for 200 epochs using the cross-entropy loss function. The [notebook](https://github.com/asumansenol/double_edged_sword_data/blob/main/Signup%20Login%20Classifier%20-%20Model%20Trainig.ipynb) along with the required [data](https://github.com/asumansenol/double_edged_sword_data/tree/main/csvs) that we used to train our model made publicly available with this repository.


# Auxiliary data
The auxiliary data utilized in our analysis and model training comprises the following:

1. 2023_08_25_top_100k_crawl_res_df.csv: Contains information regarding the pages visited by our crawler, indicating whether they are login or signup pages.
2. 2023_08_25_top_100k_fps.csv: Provides details about fingerprinting scripts found on each visited page, including fingerprinting type(canvas, font etc), domain, etc.
3. classifiers_comparison_random_sample.csv: A randomly selected sample of 1000 site URLs used to evaluate the performance of different login/signup page classifiers (including our ML model, Fathom, Autofill, and previous heuristics).
4. crux_fqdn_top_100k_202304_with_rank.csv: Includes the rank of the URLs visited during the analysis.
5. inner_links.csv: Records the inner links visited by each homepage examined.
6. signals.csv: Contains login and signup-related page signals used in model training.



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
