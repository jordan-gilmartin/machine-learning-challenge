# machine-learning-challenge



## Background

Over a period of nine years in deep space, the NASA Kepler space  telescope has been out on a planet-hunting mission to discover hidden  planets outside of our solar system.

In processing this data, I created machine learning models capable of classifying candidate exoplanets from the raw dataset.

The models were:

- Logistic Regression (LR)
- Deep Learning (DL)
- Support Vector Machine (SVM)



## Model Results

The 'Accuracy' scores for each of the models was fairly aligned.  Both the LR and SVM models returned scores of .89 and the DL model returned a score of .90.  The data was scaled in all of the models and was label encoded in the DL model.  

I included a confusion matrix with the LR and SVM models which reveals a little more detail about each potential category being predicted.  

There were three potential categories in total - 'CANDIDATE', 'CONFIRMED', and 'FALSE POSITIVE'.  Again both LR and SVM models were very close in their results here.  

'CANDIDATE' was the only category where the F1 showed a difference, LR showed .74 and SVM showed .71.  

Otherwise for 'CONFIRMED' and 'FALSE POSITIVE' they were tied at .80 and .99 respectively.  

The F1 score being so high for 'FALSE POSITIVE' warrants further digging, not sure if that bar is really just so low that it is highly easy to predict or if there is something else going on there.  

I used Random Forest initially to weigh all the features and wound up eliminating a handful that were less than 1% significance.  So all 3 models were run using 34 features instead of the 40 found in the raw dataset.  The top 5 features by significance were:

```
(0.107606009505025, 'koi_fpflag_co'),
 (0.09336042425938637, 'koi_fpflag_nt'),
 (0.0688098263891143, 'koi_fpflag_ss'),
 (0.05945211575639642, 'koi_model_snr'),
 (0.05437757028609435, 'koi_prad'),
```

Overview of data dictionary can be found [here](https://exoplanetarchive.ipac.caltech.edu/docs/API_kepcandidate_columns.html) at the NASA Exoplanet Archive.  

All in all the models are basically suggesting 90% accuracy rate here so the features included are highly relevant and it seems that false positives are fairly easily discarded and that we just need to spend a bit more time with candidates and confirmed to verify accuracy on those.  





