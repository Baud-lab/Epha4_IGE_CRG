# Epha4_IGE_CRG

This repo describes all the work carried out for the *Epha4* indirect genetic effects study

Example data to carry out the analysis provided in `/data`

### Requirements
Software	Version
python: 3.14
NumPy: 2.4.2
pandas: 2.3.3
SciPy: 1.17.0
statsmodels: 0.14.6
Matplotlib: 3.10.8
seaborn: 0.13.2

After installing the proper Python version, you can install the dependencies from `requirements.txt`
```
pip install -r requirements.txt
```

## IGE Analysis
Three phenotypes of the focal mouse were analyzed for this study in terms of the effect of *Epha4* genotype of the cage mate
1. Immobility duration in the first two minutes of the Forced Swim Test
2. Immobility duration in the last four minutes of the Forced Swim Test
3. Ear hole area

1. and 2. are combined in the same notebook (`fst_analysis.ipynb`) as it is the same dataset and 3. is analyzed in two steps (first, `woundhealing_preprocssing.ipynb` and then `woundhealing_analysis.ipynb`)

Social epistasis and model comparison globally uses outputs from all phenotypes and hence uses a separate script `social_epistasis.ipynb`


## FST automated quantification

Note that this pipeline is run with the help of the output of EthVision XT 16 using the Activity analysis module. Find exact method details in the manuscript.

To use this method for another strain, the strain-specific threshold must be first determined using ground-truth manual annotaions and stored as in `/data/metadata/manual_ground_truth_annotations.csv`

Using the script, one can validate the threshold in a training and test dataset as in `/fst_method/threshold_detection.ipynb`

Apply that threshold as in `/ige_analysis/FST_analysis` with the function `process_activity_files()` and ignore the rest of the analysis.

