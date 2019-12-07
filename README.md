![Image of Burnaby School](https://burnabyschools.ca/wp-content/uploads/2019/04/MentalHealthWell-beingforAll_graphic.png)
# *Data Analytics Tools -- DATA 1202*
## Final Project: Mental Health in the United States companies


 
The purpose of this project is to evaluate the attitude towards Mental health from companies located in the United States. 

The dataset analyzed contained the answers of a survey about Mental Health from several male and female workers of ages between 18 to 72 years old. Also, this population belongs to various countries, that is Australia, Canada, Finland, United States, Finland, etc. 
In this survey each individual was asked about the mental health awareness from their workplace.

Some of the examples of the questions are:
1. benefits: Does your employer provide mental health benefits?
2. care_options: Do you know the options for mental health care your employer provides?


First, the CSV format dataset called "survey" was loaded to be transformed and analized to solve the problem statement.

``` python
#Read CSV
DataSurvey = pd.read_csv("./survey.csv")
```



Due to the purpose of the evaluate attitude towards the Mental Health of the **United States companies**, the dataset was transformed into a new one. It contains exclusively informartion of workers from the USA.
``` python
#Create a new dataset that contains just "United State"

USA_states = DataSurvey[DataSurvey["Country"] == "United States"]
```

The variable selected to evaluate the attitude towards Mental Health was the **wellness_program**. It indicates whether the company offers a wellness program to the employees. This program should promote practices to enhance and treat mental health.

The dataset was processed to understand the top 10 of states from the United States that have more positive answer from the workers about the existence of wellness programs in their companies.

``` python
#Group by State
wellness_program_groupby = wellness_program.groupby('state',as_index=False)['wellness_program'].count()
wellness_program_groupby = wellness_program_groupby.sort_values('wellness_program', ascending=False)
wellness_program_groupby = wellness_program_groupby.reset_index(drop=True)
wellness_program_groupby = wellness_program_groupby.head(10)
print(wellness_program_groupby)
```


