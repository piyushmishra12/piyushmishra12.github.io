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
During the destitution that was the period of last few months for me, I came across many a job posting that seemed rather fishy to me. There even was one enterprise that reduced the stipend to about 10% of what it was when I applied, and once I finished the screening, pretented as if it was always that low. Fortunately, I never submitted the screening. So, I decided to build a classifier that would detect fake job postings. Thankfully, [this dataset](https://www.kaggle.com/shivamb/real-or-fake-fake-jobposting-prediction) was available to work on. My entire notebook, including an outline of the thought process is available in [my Kaggle kernel](https://www.kaggle.com/piyushmishra1999/get-a-real-job). If you like it, please upvote it. That would really help me.

## Data Handling

The data has 18000 job descriptions out of which 800 are fake. So, clearly there is a class imbalance. Now working with such a class imbalance can pose a threat to the validation of the model. Since a significantly large number of job postings are, as a matter of fact, real, the model can always predict that the test instance is real and basically et away with it. There are [different manœevres](https://www.researchgate.net/publication/288228469_Classification_with_class_imbalance_problem_A_review) for it, however I chose to opt for three: use Cohen's Kappa as a metric in lieu of simple percentage based accuracy, use F1 score in lieu of simple percentage based accuracy, and a little sub-sampling never hurts.

* Cohen's Kappa helps because it basically takes into consideration the possibility of agreement by chance. It gives the value of agreement between two raters who each classify a number of items or instances into separate classes or groups. So, it is a good method to check disproportionate advantage of one class over another.
* F1 Score, simply, is the harmonic mean of precision and recall. So, in lay terms, it seeks to neutralise the effects of class imbalance.
* Sub-sampling the entire dataset helps in giving the class with less instances an equal footing with its counterpart.
