```python
pwd

#The field beginning with In[] is called a cell. This is the place you type Unix commands or Python codes for execution.

```




    'C:\\Users\\riyta\\MIS3320CourseData\\notebook'




```python
ls
#The result will list the directories and files under the current directory.
```

     Volume in drive C is OS
     Volume Serial Number is B64B-072A
    
     Directory of C:\Users\riyta\MIS3320CourseData\notebook
    
    02/20/2022  04:29 PM    <DIR>          .
    02/20/2022  04:29 PM    <DIR>          ..
    02/14/2022  02:25 AM             6,148 .DS_Store
    02/20/2022  03:38 PM    <DIR>          .ipynb_checkpoints
    02/20/2022  04:29 PM            12,762 M2Exercise.ipynb
    02/14/2022  12:40 PM            48,443 M3exercise.ipynb
    02/14/2022  12:06 PM            15,254 Module3Exercise.ipynb
    02/14/2022  02:25 AM               113 README.md
    02/20/2022  03:37 PM                72 Untitled.ipynb
                   6 File(s)         82,792 bytes
                   3 Dir(s)  30,336,753,664 bytes free
    


```python
man ls  # this is a unix comment to display manual
#mine doesn't work some reason lol

#man ls, which shows the manual page for the ls command
```


      File "C:\Users\riyta\AppData\Local\Temp/ipykernel_4168/3812953402.py", line 1
        man ls  # this is a unix comment to display manual
            ^
    SyntaxError: invalid syntax
    



```python
ls -F ..\Data    #Don't worry about File not found the answer is correct what is shown, even prof said so

#windows uses the \ slash versus for Mac
```

     Volume in drive C is OS
     Volume Serial Number is B64B-072A
    
     Directory of C:\Users\riyta\MIS3320CourseData\notebook
    
    
     Directory of C:\Users\riyta\MIS3320CourseData\Data
    
    02/14/2022  02:29 AM    <DIR>          .
    02/14/2022  02:29 AM    <DIR>          ..
    02/14/2022  02:25 AM                 0 .gitkeep
    02/14/2022  02:25 AM         2,407,517 acs_ny.csv
    02/14/2022  02:25 AM            46,158 banklist.csv
    02/14/2022  02:25 AM            90,190 billboard.csv
    02/14/2022  02:25 AM             5,385 bladder.csv
    02/14/2022  02:25 AM                56 concat_1.csv
    02/14/2022  02:25 AM                56 concat_2.csv
    02/14/2022  02:25 AM                64 concat_3.csv
    02/14/2022  02:25 AM             5,674 country_timeseries.csv
    02/14/2022  02:25 AM               311 doctors.csv
    02/14/2022  02:25 AM               298 doctors_unicode.csv
    02/14/2022  02:25 AM        49,439,217 epi_sim.zip
    02/14/2022  02:25 AM            81,932 gapminder.tsv
    02/14/2022  02:25 AM           267,845 housing.csv
    02/14/2022  02:25 AM           270,670 housing_renamed.csv
    02/14/2022  02:25 AM               965 pew.csv
    02/14/2022  02:25 AM            11,318 raw_data_urls.txt
    02/14/2022  02:25 AM               433 scientists.csv
    02/14/2022  02:25 AM               122 survey_person.csv
    02/14/2022  02:25 AM                74 survey_site.csv
    02/14/2022  02:25 AM               391 survey_survey.csv
    02/14/2022  02:25 AM               168 survey_visited.csv
    02/14/2022  02:25 AM           136,637 tesla_stock_yahoo.csv
    02/14/2022  02:25 AM             2,898 weather.csv
    02/14/2022  02:25 AM            11,498 wine.csv
                  25 File(s)     52,779,877 bytes
                   2 Dir(s)  31,273,885,696 bytes free
    

    File Not Found
    


```python
import pandas as pd    #Import pandas library and name it pd
```


```python
df = pd.read_csv('../data/gapminder.tsv', sep='\t')   #Load tsv data file, separated by Tab. Save the data as df
```


```python
type(df)    #Show the object type of df, which is DataFrame here
```




    pandas.core.frame.DataFrame




```python
df   #Show data df
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
      <th>country</th>
      <th>continent</th>
      <th>year</th>
      <th>lifeExp</th>
      <th>pop</th>
      <th>gdpPercap</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1952</td>
      <td>28.801</td>
      <td>8425333</td>
      <td>779.445314</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1957</td>
      <td>30.332</td>
      <td>9240934</td>
      <td>820.853030</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1962</td>
      <td>31.997</td>
      <td>10267083</td>
      <td>853.100710</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1967</td>
      <td>34.020</td>
      <td>11537966</td>
      <td>836.197138</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Afghanistan</td>
      <td>Asia</td>
      <td>1972</td>
      <td>36.088</td>
      <td>13079460</td>
      <td>739.981106</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>1699</th>
      <td>Zimbabwe</td>
      <td>Africa</td>
      <td>1987</td>
      <td>62.351</td>
      <td>9216418</td>
      <td>706.157306</td>
    </tr>
    <tr>
      <th>1700</th>
      <td>Zimbabwe</td>
      <td>Africa</td>
      <td>1992</td>
      <td>60.377</td>
      <td>10704340</td>
      <td>693.420786</td>
    </tr>
    <tr>
      <th>1701</th>
      <td>Zimbabwe</td>
      <td>Africa</td>
      <td>1997</td>
      <td>46.809</td>
      <td>11404948</td>
      <td>792.449960</td>
    </tr>
    <tr>
      <th>1702</th>
      <td>Zimbabwe</td>
      <td>Africa</td>
      <td>2002</td>
      <td>39.989</td>
      <td>11926563</td>
      <td>672.038623</td>
    </tr>
    <tr>
      <th>1703</th>
      <td>Zimbabwe</td>
      <td>Africa</td>
      <td>2007</td>
      <td>43.487</td>
      <td>12311143</td>
      <td>469.709298</td>
    </tr>
  </tbody>
</table>
<p>1704 rows × 6 columns</p>
</div>




```python
df.shape   #get the number of rows and columns
```




    (1704, 6)




```python
df.columns  #Get column names
```




    Index(['country', 'continent', 'year', 'lifeExp', 'pop', 'gdpPercap'], dtype='object')




```python
df.dtypes   #get the data type of each column
```




    country       object
    continent     object
    year           int64
    lifeExp      float64
    pop            int64
    gdpPercap    float64
    dtype: object


