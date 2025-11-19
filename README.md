```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```


```python
employee=pd.read_csv('Employee_profile.csv')
```


```python
employee.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Unnamed: 0</th>
      <th>work_year</th>
      <th>experience_level</th>
      <th>employment_type</th>
      <th>job_title</th>
      <th>salary</th>
      <th>salary_currency</th>
      <th>salary_in_usd</th>
      <th>employee_residence</th>
      <th>remote_ratio</th>
      <th>company_location</th>
      <th>company_size</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>2020</td>
      <td>MI</td>
      <td>FT</td>
      <td>Data Scientist</td>
      <td>70000</td>
      <td>EUR</td>
      <td>79833</td>
      <td>DE</td>
      <td>0</td>
      <td>DE</td>
      <td>L</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>2020</td>
      <td>SE</td>
      <td>FT</td>
      <td>Machine Learning Scientist</td>
      <td>260000</td>
      <td>USD</td>
      <td>260000</td>
      <td>JP</td>
      <td>0</td>
      <td>JP</td>
      <td>S</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>2020</td>
      <td>SE</td>
      <td>FT</td>
      <td>Big Data Engineer</td>
      <td>85000</td>
      <td>GBP</td>
      <td>109024</td>
      <td>GB</td>
      <td>50</td>
      <td>GB</td>
      <td>M</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>2020</td>
      <td>MI</td>
      <td>FT</td>
      <td>Product Data Analyst</td>
      <td>20000</td>
      <td>USD</td>
      <td>20000</td>
      <td>HN</td>
      <td>0</td>
      <td>HN</td>
      <td>S</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>2020</td>
      <td>SE</td>
      <td>FT</td>
      <td>Machine Learning Engineer</td>
      <td>150000</td>
      <td>USD</td>
      <td>150000</td>
      <td>US</td>
      <td>50</td>
      <td>US</td>
      <td>L</td>
    </tr>
  </tbody>
</table>
</div>




```python
employee.tail()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Unnamed: 0</th>
      <th>work_year</th>
      <th>experience_level</th>
      <th>employment_type</th>
      <th>job_title</th>
      <th>salary</th>
      <th>salary_currency</th>
      <th>salary_in_usd</th>
      <th>employee_residence</th>
      <th>remote_ratio</th>
      <th>company_location</th>
      <th>company_size</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>602</th>
      <td>602</td>
      <td>2022</td>
      <td>SE</td>
      <td>FT</td>
      <td>Data Engineer</td>
      <td>154000</td>
      <td>USD</td>
      <td>154000</td>
      <td>US</td>
      <td>100</td>
      <td>US</td>
      <td>M</td>
    </tr>
    <tr>
      <th>603</th>
      <td>603</td>
      <td>2022</td>
      <td>SE</td>
      <td>FT</td>
      <td>Data Engineer</td>
      <td>126000</td>
      <td>USD</td>
      <td>126000</td>
      <td>US</td>
      <td>100</td>
      <td>US</td>
      <td>M</td>
    </tr>
    <tr>
      <th>604</th>
      <td>604</td>
      <td>2022</td>
      <td>SE</td>
      <td>FT</td>
      <td>Data Analyst</td>
      <td>129000</td>
      <td>USD</td>
      <td>129000</td>
      <td>US</td>
      <td>0</td>
      <td>US</td>
      <td>M</td>
    </tr>
    <tr>
      <th>605</th>
      <td>605</td>
      <td>2022</td>
      <td>SE</td>
      <td>FT</td>
      <td>Data Analyst</td>
      <td>150000</td>
      <td>USD</td>
      <td>150000</td>
      <td>US</td>
      <td>100</td>
      <td>US</td>
      <td>M</td>
    </tr>
    <tr>
      <th>606</th>
      <td>606</td>
      <td>2022</td>
      <td>MI</td>
      <td>FT</td>
      <td>AI Scientist</td>
      <td>200000</td>
      <td>USD</td>
      <td>200000</td>
      <td>IN</td>
      <td>100</td>
      <td>US</td>
      <td>L</td>
    </tr>
  </tbody>
</table>
</div>




```python
employee.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 607 entries, 0 to 606
    Data columns (total 12 columns):
     #   Column              Non-Null Count  Dtype 
    ---  ------              --------------  ----- 
     0   Unnamed: 0          607 non-null    int64 
     1   work_year           607 non-null    int64 
     2   experience_level    607 non-null    object
     3   employment_type     607 non-null    object
     4   job_title           607 non-null    object
     5   salary              607 non-null    int64 
     6   salary_currency     607 non-null    object
     7   salary_in_usd       607 non-null    int64 
     8   employee_residence  607 non-null    object
     9   remote_ratio        607 non-null    int64 
     10  company_location    607 non-null    object
     11  company_size        607 non-null    object
    dtypes: int64(5), object(7)
    memory usage: 57.0+ KB



```python
employee.isnull().sum().sort_values()
```




    Unnamed: 0            0
    work_year             0
    experience_level      0
    employment_type       0
    job_title             0
    salary                0
    salary_currency       0
    salary_in_usd         0
    employee_residence    0
    remote_ratio          0
    company_location      0
    company_size          0
    dtype: int64




```python
emp_copy=employee.copy()
```

# 1) Finding the average salary by year.


```python
emp_copy.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Unnamed: 0</th>
      <th>work_year</th>
      <th>experience_level</th>
      <th>employment_type</th>
      <th>job_title</th>
      <th>salary</th>
      <th>salary_currency</th>
      <th>salary_in_usd</th>
      <th>employee_residence</th>
      <th>remote_ratio</th>
      <th>company_location</th>
      <th>company_size</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>2020</td>
      <td>MI</td>
      <td>FT</td>
      <td>Data Scientist</td>
      <td>70000</td>
      <td>EUR</td>
      <td>79833</td>
      <td>DE</td>
      <td>0</td>
      <td>DE</td>
      <td>L</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>2020</td>
      <td>SE</td>
      <td>FT</td>
      <td>Machine Learning Scientist</td>
      <td>260000</td>
      <td>USD</td>
      <td>260000</td>
      <td>JP</td>
      <td>0</td>
      <td>JP</td>
      <td>S</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>2020</td>
      <td>SE</td>
      <td>FT</td>
      <td>Big Data Engineer</td>
      <td>85000</td>
      <td>GBP</td>
      <td>109024</td>
      <td>GB</td>
      <td>50</td>
      <td>GB</td>
      <td>M</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>2020</td>
      <td>MI</td>
      <td>FT</td>
      <td>Product Data Analyst</td>
      <td>20000</td>
      <td>USD</td>
      <td>20000</td>
      <td>HN</td>
      <td>0</td>
      <td>HN</td>
      <td>S</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>2020</td>
      <td>SE</td>
      <td>FT</td>
      <td>Machine Learning Engineer</td>
      <td>150000</td>
      <td>USD</td>
      <td>150000</td>
      <td>US</td>
      <td>50</td>
      <td>US</td>
      <td>L</td>
    </tr>
  </tbody>
</table>
</div>




```python
avg_sal=emp_copy.groupby('work_year')['salary'].mean().reset_index()
```


```python
avg_sal.columns=['Year','Average salary']
```


```python
print(avg_sal)
```

       Year  Average salary
    0  2020   382386.236111
    1  2021   546677.387097
    2  2022   158827.786164


# 2) Showing the ratio of remote or non-remote employees.


```python
remote_counts=emp_copy['remote_ratio'].value_counts()
print('Remote ratio counts:')
print(remote_counts)

remote_percentage=(remote_counts/len(emp_copy))*100

print('\nRatio for remote(100) ,Hybrid(50) and Non-remote(0) employees are:')
print(remote_percentage)
```

    Remote ratio counts:
    remote_ratio
    100    381
    0      127
    50      99
    Name: count, dtype: int64
    
    Ratio for remote(100) ,Hybrid(50) and Non-remote(0) employees are:
    remote_ratio
    100    62.76771
    0      20.92257
    50     16.30972
    Name: count, dtype: float64


# 3) Visualize the company size based on the years.


```python
size_by_year=emp_copy.groupby('work_year').company_size.value_counts().reset_index(name='count')
print(size_by_year.T)
```

                     0     1     2     3     4     5     6     7     8
    work_year     2020  2020  2020  2021  2021  2021  2022  2022  2022
    company_size     L     S     M     L     M     S     M     L     S
    count           33    25    14   119    53    45   259    46    13



```python
plt.figure(figsize=(8,5))
ax = sns.barplot(data=size_by_year,x='work_year',y='count',hue='company_size',palette='husl',
                hue_order=['S','M','L'])

# Add labels above bars
for value in ax.containers:
    ax.bar_label(value) 
    

plt.title('Company Size Distribution by Year', fontsize=16)
plt.xlabel('Work Year')
plt.ylabel('Number of Companies')
plt.legend(title='Company Size',loc='best',bbox_to_anchor=(1,1))
plt.tight_layout()
plt.show()
```


    
![png](output_16_0.png)
    


# 4) Printing out the top 5 job titles



```python
jobs=emp_copy['job_title'].value_counts().head().reset_index(name='job Count')
print(jobs)
```

                       job_title  job Count
    0             Data Scientist        143
    1              Data Engineer        132
    2               Data Analyst         97
    3  Machine Learning Engineer         41
    4         Research Scientist         16



```python
plt.figure(figsize=(8,5))

ax=sns.barplot(data=jobs,x='job_title',y='job Count',hue='job_title',palette='husl')

for value in ax.containers:
    ax.bar_label(value)

plt.title('Top 5 companies')
plt.xlabel('Job title')
plt.xticks(rotation=30,ha='right')
plt.ylabel('Jobs count')
plt.show()
```


    
![png](output_19_0.png)
    


# 5)Finding the distribution of salary by company size.


```python
sal_distribution=emp_copy.groupby('company_size').salary.sum().reset_index(name='salary_sum')

print(sal_distribution)
```

      company_size  salary_sum
    0            L   117551772
    1            M    47766335
    2            S    31349931



```python
#color=[]
plt.figure(figsize=(6,6))
exp=[0.1,0.1,0.1]
plt.pie(sal_distribution['salary_sum'],labels=sal_distribution['company_size'],autopct='%0.2f%%',
             explode=exp,shadow=True,startangle=90)

plt.title('Distribution of salary by company size',fontsize=15)
plt.tight_layout()
plt.show()
```


    
![png](output_22_0.png)
    


# 6) Creating a histogram showing the distribution of salaries by company size.


```python
plt.figure(figsize=(10,6))

for size in emp_copy['company_size'].unique():
    subset = emp_copy[emp_copy['company_size'] == size]
    plt.hist(subset['salary'], bins=30, alpha=0.6, label=size)

plt.xscale('log')
plt.xlabel("Salary (log scale)")
plt.ylabel("Count")
plt.title("Salary Distribution by Company Size")
plt.legend(title="Company Size")
plt.show()
```


    
![png](output_24_0.png)
    


# 7)Finding the experience level of employees.
Code	Full Form	                   Meaning
EN	   Entry-Level	     New employees, junior positions, < 2 years experience
MI	   Mid-Level	     Intermediate, 2–5 years experience
SE	   Senior-Level	     Experienced employees, 5–10 years experience
EX	   Executive-Level	 Management roles, > 10 years experience

```python
exp=emp_copy['experience_level'].value_counts().reset_index(name='count')
print(exp)
```

      experience_level  count
    0               SE    280
    1               MI    213
    2               EN     88
    3               EX     26



```python
ax=[0.1,0.1,0.1,0.1]

plt.figure(figsize=(10,8))

plt.pie(exp['count'],labels=exp['experience_level'],autopct='%0.2f%%',
        explode=ax,shadow=True,startangle=90)

plt.title(' Experience level of employees',fontsize=20)

plt.show()
```


    
![png](output_28_0.png)
    



```python

```
