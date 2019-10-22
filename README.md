# What matters in schools?
## Explaining children's academic progress in England between the ages of 11 and 16

In England, schools used to be judged solely on GCSE results of their children in Maths and English.  In 2016 the government decided to change the key measure, to be one that assessed how much progress children had made since they were 11 (GCSEs are generally taken at 16 years old), and measure it for a broader range of subjects (up to 8 in total).  This project looked at progress data for GCSE results for children in England in 2018, and used regression models to see how much of the progress that children make can be explained.  (Answer: about half.)

This is my final ('Capstone') project for 3 month Data Science Immersive Course with General Assembly.


## Why is this important?
Over the past 10 years there has been reduced funding for schools. Recently (August 2019), the government announced a £7.1bn increase in spending on education over the next three years. Knowing which areas to invest this money in is crucial to ensure the best possible benefit for children, especially since GCSE results are a key factor in predicting University grades.

Whilst academic results are by no means the sole factor in a child's development, with experience in sports and arts activities and overall health being three other crucial factors of many, they are nevertheless important to future achievement in adult life.

## What ***does*** explain how much progress children make?
There are six key factors that explain the progress made by children in GCSEs taken in 2018. These factors came up in all the different analyses and eight models that were used (more details on them below), and explained just over half of the variation in the progress that schools helped children to make between 11 and 16 years old.

The best performing model was Linear Regression with Lasso Regularisation, which had a mean R2 score of 0.56 on a 5 fold cross-validated training set. Decision Tree Regression and its variants (Ensemble methods of Bagging, Random Forest and AdaBoosting) continually highlighted the same 6 features as being most important (accounting for between 48% and 75% of all Features' Importance depending on the model used). When I ran just those 6 factors in Linear Regression models, I got very similar scores to when I had all data included, except that the 'vanilla' OLS without regularisation became as high as the reguilarised scores.

Note: I excluded all data that I termed 'Academic' since it had circular causality with the Progress 8 measure: for example, doing better than others in Maths will make you progress more than them.

### The six key non-academic factors are:
1) Coming from a disadvantaged background hampers a child's academic progress
2) Pupils with English as an additional language (EAL) progress more than those without it: this is largely due to proficiency in English itself: by the time children with EAL reach 16, they have not only mastered English, but are then ahead of their peers academically.
3) Achieving at least one GCSE is important: most children get at least one GCSE, but there are a few schools which have more than a handful of pupils not getting at least one GCSE
4) Taking a(ny) language at GCSE is a strong indicator of a child progressing more than his or her peers
5) Girls progress faster than boys from 11 to 16 years old
6) The more GCSEs (and equivalent) qualifications that children do, the more they progress


### There were some surprise findings too...
...because they turned out to be unimportant when I had thought that they would be:<br />
a) The ratio of teachers to pupils does not have a significant impact on overall academic progress<br />
b) Children in Selective Schools make on average two thirds of a grade more progress per GCSE than children in Non-Selective ones (remember that the focus in the project is how much progress children make, not their 'raw' academic achievement)<br />
c) The most recent Government Inspection (Ofsted) rating of the school was not a big predictor of progress<br />
d) Educational establishments (Academies) did not progress more than other schools, though it may be too early to see the impact of these institutions<br />
e) Geographic location in the UK was not itself a significant factor in explaining progress<br />

## So what?  Some recommendations for the government
1) Commission research into determining whether learning languages strengthens a child's overall cognitive development, and if so, return to making languages compulsory at GCSE
2) Review the effectiveness of the 'Pupil Premium' funding that was introduced in 2011, and either boost that funding or change the policy for improving the progress that children make
3) Examine why children in Selective Schools make more progress than their peers in non-Selective schools.
4) Encourage schools to offer as broad an education as possible since children who take more GCSEs progress more.

Given that the models explained approximately 50% of the variation in progress that children made, there is one further hypothesis that I believe needs to be explored further: ***that teacher and Head Teacher quality in schools is the primary driver of the amount of progress that children make.***

However, before these recommendations are implemented, the data for other school years needs to be analysed, to ascertain whether the explanatory factors for those years are similar to 2017-18.

### There are three risks to the models that I have built which need to be considered:
1) The 50% of progress that is unexplained by the model could have more important actions that need to be taken. I believe that the most important factor for determining progress is teacher quality (driven itself by Head Teacher quality) but I could not find data on that
2) Schools may focus on influencing the results for their school overall to the detriment of childrens' progress
3) The smallest 30% of schools (accounting for only 5% of children) are excluded from data for reasons of anonymity, but they may affect the overall findings


## Want to find out more?
There are five files that form the core of the analysis:

1) **<title goes here>** Powerpoint presentation of the project
2) **GCSEs_Model_Tech_Report_Sep_19.ipynb**: technical report of the whole project, from data cleaning to modeling to findings and recommendations.

3) **GCSEs_Data_Cleaning_Sep_19.ipynb**: step by step walk through of the data cleaning to get a usable dataset (includes imputation)
4) **GCSEs_Modeling_Sep_19.ipynb**: step by step walk through of all eight models that I built (includes parameter settings, results, and conclusions for each)
5) **GCSEs_Findings_Data_Sep_19**: detail on each of the key findings from the modeling (includes graphs)

#### The data
a) Original raw dataset (from https://www.compare-school-performance.service.gov.uk/download-data)<br />
b) Final, cleaned data file that was used for modeling (xxx.csv)<br />


#### What you need in order to be able to see the files
These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.  You do 

#### Prerequisites and how to install them
What things you need to install the software and how to install them
1) Python
2) Jupyter Notebook
3) Pandas
4) Matplotlib
5) Seaborn

## Questions or feedback?
The files should all load, and hopefully they are self-explanatory, but if they don't or you have any questions or feedback please let me know (jackwhittle@gmail.com).  I'm always interested to hear people's thoughts on something I am passionate about!

Thanks

Jack
