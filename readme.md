## Blog Link: https://medium.com/@bbyers3/udacity-capstone-starbucks-user-data-for-best-offers-40e4415d4f3c
# Starbuck's Capstone Challenge

## Dataset overview
The goal of this is to use the data to figure out the users that would be most responsive depending on the offer. This will allow the business to create new offers or target specific groups with the offer that they are most likely to respond to.
It will simulate users buying products from starbucks and how much of their decision was influenced by an offer.

Only 3 types of offers are studied, BOGO, Discount, and Informational. Discount is a flat discount, Bogo requires buy a specific amount of something, and informational is just information for the user like a new product or a reminder of a popular product.

Members can get the offers many ways, web,email,mobile and social being the major methods.

# Data Dictionary
## profile.json
Rewards program users (17000 users x 5 fields)

gender: (categorical) M, F, O, or null
age: (numeric) missing value encoded as 118
id: (string/hash)
became_member_on: (date) format YYYYMMDD
income: (numeric)

## portfolio.json
Offers sent during 30-day test period (10 offers x 6 fields)

reward: (numeric) money awarded for the amount spent
channels: (list) web, email, mobile, social
difficulty: (numeric) money required to be spent to receive reward
duration: (numeric) time for offer to be open, in days
offer_type: (string) bogo, discount, informational
id: (string/hash)

## transcript.json
Event log (306648 events x 4 fields)

person: (string/hash)
event: (string) offer received, offer viewed, transaction, offer completed
value: (dictionary) different values depending on event type
offer id: (string/hash) not associated with any "transaction"
amount: (numeric) money spent in "transaction"
reward: (numeric) money gained from "offer completed"
time: (numeric) hours after start of test

### Data Results
Based on there data set there are some characteristics that we have discovered:

Total number of people - 14,825

Total Men - 8484

Total Women - 6129

Total Undisclosed - 212

A large part of the members are new members

Most users are 50 years or greater

Median Income - 64000

Mean Income - 65405

Mean Age - 54.4

#### f1 scores
[0.72727272727272718,
 0.71964679911699769,
 0.75568181818181812,
 0.7821522309711284,
 0.80833333333333335,
 0.84090909090909105,
 0.84595300261096606,
 0.75,
 0.73857404021937834,
 0.77720207253886009]
 
### Conclusion
Performance of the Classification Models
The model with the highest fscore of 0.85 it discount_10_2_10. While the lowest score still met our evalutation criteria at 0.72 which is the bogo_10_10_7. The processing time for all of the models felt long (around 6 hours for my PC to run it all) but it could be nominal for larger companies like Starbucks who have much strong processing power than a single dual core laptop.

Performance of the Regression Model
Overall it did not do well, with an low R2 it would not be a good model for predicting behavior for users. Part of the reason could be due to the complex nature of the data and large variation without enough detail. More features such as race/location/etc could provide a clearer picture on how to market to the users more efficently.

Possible Improvements
More data can be collected, stronger processing power can be used, and a larger variety of offers could provide more insight into customer

### References
https://www.oreilly.com/library/view/hands-on-machine-learning/9781789346411/e17de38e-421e-4577-afc3-efdd4e02a468.xhtml

https://seaborn.pydata.org/tutorial/color_palettes.html

https://kite.com/blog/python/pandas-groupby-count-value-count/

https://www.programcreek.com/python/example/53771/progressbar.ProgressBar

https://joblib.readthedocs.io/en/latest/generated/joblib.dump.html

https://docs.python.org/3/library/math.html

https://towardsdatascience.com/basic-datetime-operations-in-python-2d706be82c63

https://scikit-learn.org/stable/auto_examples/bicluster/plot_spectral_coclustering.html#sphx-glr-auto-examples-bicluster-plot-spectral-coclustering-py

https://scikit-learn.org/stable/auto_examples/gaussian_process/plot_gpr_on_structured_data.html#sphx-glr-auto-examples-gaussian-process-plot-gpr-on-structured-data-py

https://towardsdatascience.com/random-forest-in-python-24d0893d51c0
