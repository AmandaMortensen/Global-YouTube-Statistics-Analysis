# Global-YouTube-Statistics-Analysis

Data analysis in Python using pandas, matplotlib, seaborn and NumpPy 

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

As part of the data exploration I used pandas to import and get a better understanding og the data, including it's size, it's content and null values. A biref code previww below 


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

#### Claening  Exploration 



