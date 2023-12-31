# Global-YouTube-Statistics-Analysis

Data analysis in Python using pandas, matplotlib, seaborn and NumpPy. Please see the attached Juputyer Noterbook for the full code and visulisations. 

### **Situation**
As many other people, I enjoy watching Youtube videos to disconnect and educate myself, which sparked my curiousity about what actually makes for a succesfull Youtube channel. Based on this interest I set out on conducting an analysis on the Global Youtube Statisctic dataset, that would provide me with insights into the key elements that make up a great Youtube channel, including which trends in video veiws and subcribers, as well as the corelation of the featueres 


### **Task**

Prior to conducting the data anslysis, I identified the aim of the project and broke it down iinto several research questions, which would act as out North Star for the project.
The aim of the study was to get an insight into what elements drive a succesfull sucess Yotube channel and what trends are worth keepign an eye on for sipirign Youtubers. 
The research questions developed based on the aim, were the following: 

- What is the trend in video publication over time?
- Which video categories are the most popular based on subscribers?
- What are the current top 5 Yotubers based on subscribers?
- Is there a corelation between video views and subscribers?

### **Action**

For my data analysis, I followed the following steps:

1. Data Exploration
2. Data Cleaning
3. Data Analysis 
- Feature Understanding 
- Feature Relationship

#### Data Exploration 

As part of the data exploration I used pandas to import and get a better understanding og the data, including it's size, it's content and null values. A biref code sample below 


```
#Importing data 

df = pd.read_csv("Global YouTube Statistics.csv", encoding='windows-1254')
```


```
#Identifying null values 
df.isna().sum()
```


```
#Identifying duplicates 
df.duplicated()
```

#### Claening Exploration 

We want to esnure that our data is clean before undertaken any form of analysis on it, to have the most reliable results. As part of my data cleanign process I removed unnecessary columns and renamed column names. A biref code sample below:

```
#Removing unnecessary columns

df2 = df[['rank', 'Youtuber', 'subscribers', 'video views', 'category', 
     #'Title',
     #'uploads', 
     'Country', 
     #'Abbreviation', 'channel_type',
     #'video_views_rank', 'country_rank', 'channel_type_rank',
       'video_views_for_the_last_30_days', 
     #'lowest_monthly_earnings',
     #'highest_monthly_earnings', 'lowest_yearly_earnings',
     #'highest_yearly_earnings', 
     'subscribers_for_last_30_days',
       'created_year', 'created_month', 
     #'created_date',
     #'Gross tertiary education enrollment (%)', 
     'Population',
     #'Unemployment rate', 'Urban_population', 'Latitude', 'Longitude'
    ]].copy()
```

#### Data Analysis

I decided to divide my data analysis into two parts - "Feature understanding", aiming to get a better grasp of the trends in the dataset and "feature relationship", with the objective to view the relationship between the features. 

**Feature understanding**


```
##Understanding the distribution of when the Youtube videos were published over time (years)

df3['Created_Year'].value_counts().head(5)

#Visulaing the above distubition 

ax = df3['Created_Year'].plot(kind='hist',range=(2001, 2022)
                              ,bins=22,
                              title = 'Disribution of Year of Video Publication')

ax.set_xlabel('Year of Publication')            
plt.show()
```

```
#Top 5 dataset to understand the leading 5 elements of every point, used for visulisation later on.

df_top5 = df3[df3["Rank"]<=5]
print(df_top5)

```

**Feature relationship**

```

#Getting a yearly breakdown of the corelation between subscribers and video views 

ax = sns.scatterplot(x='Subscribers',
                y='Video_Views',
                hue='Created_Year',
                data=df3).set(title='Corelation Between Video Views and Subscribers, with Year of Creation Information')
plt.show()

```


```
#Corelation between numeric values

df_corr = df[['rank','video views','subscribers','highest_monthly_earnings']].dropna().corr()
df_corr  
```


### **Results**

The project was concluded by the following list of insights gained from the data analysis:

- Most videos were published in 2014 and second-most in 2006, and has been following a downwarding trends ever since
- "Music", "film animation" and "entertainment" are the three most popular videos categories by subscribers
- T-series is the leading Yotuber with the most subscribers, with 250 million subscribers
- There is a strong relastionship between number of video views and number of subscribers
- According to heatmap displaying the corelation coefficient between our numeric values, most values are moderate correlated or not correlated at all

  





