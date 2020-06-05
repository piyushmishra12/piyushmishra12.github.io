---
layout: project
type: project
image: images/garj.png
title: Get a Real Job
permalink: projects/getarealjob
# All dates must be YYYY-MM-DD format!
date: 2020-06-04
labels:
  - NLP
  - Classification
  - Language Model
summary: Detecting fake job postings online to get a real job
projecturl: 
---
During the destitution that was the period of the last few months for me, I came across many a job posting that seemed rather fishy to me. So, I decided to build a classifier that detects fake job postings. Thankfully, [this dataset](https://www.kaggle.com/shivamb/real-or-fake-fake-jobposting-prediction) was available to work on. My entire notebook, including an outline of the thought process is available [here](https://www.kaggle.com/piyushmishra1999/get-a-real-job). If you like it, please upvote it. That would really help me.

## Data Handling

The data has 18000 job descriptions out of which 800 are fake. So, clearly there is a class imbalance. Now working with such a class imbalance can pose a threat to the validation of the model. Since a significantly large number of job postings are, as a matter of fact, real, the model can always predict that the test instance is real and basically et away with it. There are [different manœevres](https://www.researchgate.net/publication/288228469_Classification_with_class_imbalance_problem_A_review) for it, however I chose to opt for three: use Cohen's Kappa as a metric in lieu of simple percentage based accuracy, use F1 score in lieu of simple percentage based accuracy, and a little sub-sampling never hurts.
