# Natural Language Processing on OkCupid Data

The following project trained on 15989 self-introductions from the dating site OkCupid to find the most simular pairs of profiles and to predict the Age, Sex, Body_Type, and Family Plans, Drinking Preferences, Level of Education, and Feelings about pets. Details can be found by downloading and opening the jupyter-notebook, no execution is required.

The model trained on 60% of the total dataset, and was cross-validated with another 10% of the dataset.

Possible bias in the data due to the pruning of profiles missing any of the outcome variables, and the self-reporting of traits, notably body type.

The notebook also contains cosine simularity scores, finding the most simular profiles compared to 3 other profiles. These will not be shown here due to their length and lack of way comparable measurements.

### Age

For this metric I setup age into 10 year buckets.

Accuracy of model: 43.8%

![Age Outcome](https://github.com/evancosmos/NLP-on-OkCupidData/blob/main/resultsimgs/1.png?raw=true)

Notable Observations:<br>
-The model next predicted never predicted an age of 70 when the person writing was 20.<br>
-The only other time the model did not predict 70 was for the small amount of actual 70 year olds.<br>
-Despite 6 age buckets, the accuracy remains fairly high. Due in part to the high concentration of 30 year olds on the app.

### Sex
Accuracy of model: 68.4%

![Sex Outcome](https://github.com/evancosmos/NLP-on-OkCupidData/blob/main/resultsimgs/2.png?raw=true)

Notable Observations:<br>
-Having only two outcomes allowed the model to score the highest accuracy here out of all the outcome variables. <br>
-The model did not simply weight it's outcomes towards males for higher accuracy, since there were more females identified correctly than as males.

### Body Type
Accuracy of model: 24.0%

![Body Type Outcome](https://github.com/evancosmos/NLP-on-OkCupidData/blob/main/resultsimgs/3.png?raw=true)

Notable Observations:<br>
-When predicting an indivdiual as fit, they were quite often either fit, atheltic, or average. Possibly due to such individuals detailing physical activity in their bio?

### Family Plans
Accuracy of model: 24.0%

![Family Plans Outcome](https://github.com/evancosmos/NLP-on-OkCupidData/blob/main/resultsimgs/4.png?raw=true)

Notable Observations:<br>
-There are 15 actual outcomes and only 12 predicted, representing some options that are so niche evene MLP does not ever predict them.<br>
-These outcomes should probaly be grouped simular to the age buckets in future expansion of the project.

### Drinking Preferences
Accuracy of model: 62.5%

![Drinking Habits Outcome](https://github.com/evancosmos/NLP-on-OkCupidData/blob/main/resultsimgs/5.png?raw=true)

Notable Observations:<br>
-Those predicted as "not at all" drinkers were never "very often" drinkers.

### Level of Education
Accuracy of Model: 35.6%

![Level of Education Outcome](https://github.com/evancosmos/NLP-on-OkCupidData/blob/main/resultsimgs/6.png?raw=true)

Notable Observations:<br>
-Dropped out of Highschool was only predicted for two cases; one of which being individuals who did in fact drop out of highschool.

### Feelings about pets
Accuracy of Model: 27.6%

![Feeling about Pets Outcome](https://github.com/evancosmos/NLP-on-OkCupidData/blob/main/resultsimgs/7.png?raw=true)

Notable Observations:<br>
-The dislike of both dogs and cats was the least predicted outcome, and even then only got reported on for the most popular value (the like of both dogs and cats). Other than prediction bias for more common answers, possible double negation in language may trip the model up.

## Future Work

Possible expainsions to this project include hosting the prediction model online so that individuals may enter an introduction about themselves and have the model try to guess their traits.
