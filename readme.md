# Starbuck's Capstone Challenge

## Dataset overview
The program used to create the data simulates how people make purchasing decisions and how those decisions are influenced by promotional offers.
Each person in the simulation has some hidden traits that influence their purchasing patterns and are associated with their observable traits. People produce various events, including receiving offers, opening offers, and making purchases.
As a simplification, there are no explicit products to track. Only the amounts of each transaction or offer are recorded.
There are three types of offers that can be sent: buy-one-get-one (BOGO), discount, and informational. In a BOGO offer, a user needs to spend a certain amount to get a reward equal to that threshold amount. In a discount, a user gains a reward equal to a fraction of the amount spent. In an informational offer, there is no reward, but neither is there a requisite amount that the user is expected to spend. Offers can be delivered via multiple channels.
The basic task is to use the data to identify which groups of people are most responsive to each type of offer, and how best to present each type of offer.

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
