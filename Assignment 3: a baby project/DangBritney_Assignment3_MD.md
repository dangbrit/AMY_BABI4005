## Assignment 3: a baby project\n
ITMG 4J
Britney Dang


```python
# Import necessary libraries
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

%matplotlib inline

# Load the CSV file into a DataFrame
file_path = r'C:/Users/dangb/Assignment_3/enhanced_box_office_data(2000-2024)u.csv'
movies = pd.read_csv(file_path)
```

## Data Analysis


```python
# Looking at the data
display(movies)
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
      <th>Rank</th>
      <th>Release Group</th>
      <th>$Worldwide</th>
      <th>$Domestic</th>
      <th>Domestic %</th>
      <th>$Foreign</th>
      <th>Foreign %</th>
      <th>Year</th>
      <th>Genres</th>
      <th>Rating</th>
      <th>Vote_Count</th>
      <th>Original_Language</th>
      <th>Production_Countries</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>Mission: Impossible II</td>
      <td>546388108.0</td>
      <td>215409889.0</td>
      <td>39.4</td>
      <td>330978219.0</td>
      <td>60.6</td>
      <td>2000</td>
      <td>Adventure, Action, Thriller</td>
      <td>6.126/10</td>
      <td>6741.0</td>
      <td>en</td>
      <td>United States of America</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>Gladiator</td>
      <td>460583960.0</td>
      <td>187705427.0</td>
      <td>40.8</td>
      <td>272878533.0</td>
      <td>59.2</td>
      <td>2000</td>
      <td>Action, Drama, Adventure</td>
      <td>8.217/10</td>
      <td>19032.0</td>
      <td>en</td>
      <td>United Kingdom, United States of America</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Cast Away</td>
      <td>429632142.0</td>
      <td>233632142.0</td>
      <td>54.4</td>
      <td>196000000.0</td>
      <td>45.6</td>
      <td>2000</td>
      <td>Adventure, Drama</td>
      <td>7.663/10</td>
      <td>11403.0</td>
      <td>en</td>
      <td>United States of America</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>What Women Want</td>
      <td>374111707.0</td>
      <td>182811707.0</td>
      <td>48.9</td>
      <td>191300000.0</td>
      <td>51.1</td>
      <td>2000</td>
      <td>Comedy, Romance</td>
      <td>6.45/10</td>
      <td>3944.0</td>
      <td>en</td>
      <td>United Kingdom, United States of America</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>Dinosaur</td>
      <td>349822765.0</td>
      <td>137748063.0</td>
      <td>39.4</td>
      <td>212074702.0</td>
      <td>60.6</td>
      <td>2000</td>
      <td>Animation, Family, Adventure</td>
      <td>6.544/10</td>
      <td>2530.0</td>
      <td>en</td>
      <td>United States of America</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>4995</th>
      <td>196</td>
      <td>Devara Part 1</td>
      <td>7361414.0</td>
      <td>5600000.0</td>
      <td>76.1</td>
      <td>1761414.0</td>
      <td>23.9</td>
      <td>2024</td>
      <td>Action, Drama</td>
      <td>7.0/10</td>
      <td>30.0</td>
      <td>te</td>
      <td>India</td>
    </tr>
    <tr>
      <th>4996</th>
      <td>197</td>
      <td>Kolpaçino 4 4'lük</td>
      <td>7343114.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>7343114.0</td>
      <td>100.0</td>
      <td>2024</td>
      <td>Comedy</td>
      <td>4.0/10</td>
      <td>4.0</td>
      <td>tr</td>
      <td>Turkey</td>
    </tr>
    <tr>
      <th>4997</th>
      <td>198</td>
      <td>Lim Young Woong: Im Hero the Stadium</td>
      <td>7305588.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>7305588.0</td>
      <td>100.0</td>
      <td>2024</td>
      <td>Music, Documentary</td>
      <td>0.0/10</td>
      <td>0.0</td>
      <td>ko</td>
      <td>South Korea</td>
    </tr>
    <tr>
      <th>4998</th>
      <td>199</td>
      <td>Yolo</td>
      <td>7241561.0</td>
      <td>2001584.0</td>
      <td>27.6</td>
      <td>5239977.0</td>
      <td>72.4</td>
      <td>2024</td>
      <td>Drama, Comedy, Action</td>
      <td>6.3/10</td>
      <td>70.0</td>
      <td>zh</td>
      <td>China</td>
    </tr>
    <tr>
      <th>4999</th>
      <td>200</td>
      <td>Sight</td>
      <td>7206741.0</td>
      <td>7206741.0</td>
      <td>100.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>2024</td>
      <td>Drama, History</td>
      <td>6.0/10</td>
      <td>23.0</td>
      <td>en</td>
      <td>United States of America</td>
    </tr>
  </tbody>
</table>
<p>5000 rows × 13 columns</p>
</div>


***What does the data look like?***

The dataset is fairly straight forward. It provides the the rank of movies that produced the highest grossing box office revenue worldwide in a 24 year period. Then it breaks down each movies' revenue by worldwide (total) revenue, domestic (USA) revenue, and foreign (everywhere that is not the USA) revenue. The revenue percentage of each of the categories mentioned (worldwide, domestic, and foreign) are provided as well.

Other columns shown is the release year of the movie, the genre(s) of the movie, the audience average ratings, voter count for those rating, orginal language, and the countries the movies were produced in.


```python
# How many rows and columns there are
print(movies.shape)
```

    (5000, 13)
    


```python
# How many NA values there are
print(movies.isna().sum())
print("")

# Total number of NA values in the entire DataFrame
total_na = movies.isna().sum().sum()
print("The total NA values is", total_na)
```

    Rank                      0
    Release Group             0
    $Worldwide                0
    $Domestic                 0
    Domestic %                0
    $Foreign                  0
    Foreign %                 0
    Year                      0
    Genres                  178
    Rating                  170
    Vote_Count              170
    Original_Language       170
    Production_Countries    200
    dtype: int64
    
    The total NA values is 888
    

## Summaries


```python
print(movies.agg({"$Worldwide":['min']}))
print("")
print(movies.agg({"$Worldwide":['max']}))
print("")
print(movies.query("Year == 2005 & Original_Language == 'en'")
      .groupby(["Original_Language", "Year"])
      .agg({"$Worldwide": ['min', 'max']}))
print("")
print(movies.query("Year == 2019 & Original_Language == 'ko'")
      .groupby(["Original_Language", "Year"])
      .agg({"$Worldwide": ['min', 'max']}))
print("")
```

         $Worldwide
    min   1666028.0
    
           $Worldwide
    max  2.799439e+09
    
                            $Worldwide             
                                   min          max
    Original_Language Year                         
    en                2005  14189860.0  895921036.0
    
                            $Worldwide             
                                   min          max
    Original_Language Year                         
    ko                2019  21386368.0  258129037.0
    
    

***Why did I query these specfic years and these specfic languages?***\n",

_Query by the Year 2005 and the Language English_

I was curious about the minimum and maximum revenue made during my birth year (2005) and in my native language.

_Query by the Year 2019 and the Language Korean_

By current market trends, recently I've noticed a surge in popularity in "foreign" language movies. Korean seems to be the most popular amongst "foreign" languages that native English speakers are watching. The reason I chose the year 2019 is because the movie, "Parasite", was released in 2019. "Parasite" is a Korean Thriller that had won the Oscar for 'Best Picture' in 2020; the first time ever since the Oscars began in 1929.


```python
movies.groupby("Year").agg({"$Worldwide":['min', 'median','mean', 'max','count' ]})
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead tr th {
        text-align: left;
    }

    .dataframe thead tr:last-of-type th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr>
      <th></th>
      <th colspan="5" halign="left">$Worldwide</th>
    </tr>
    <tr>
      <th></th>
      <th>min</th>
      <th>median</th>
      <th>mean</th>
      <th>max</th>
      <th>count</th>
    </tr>
    <tr>
      <th>Year</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2000</th>
      <td>1666028.0</td>
      <td>30645193.5</td>
      <td>6.955243e+07</td>
      <td>5.463881e+08</td>
      <td>200</td>
    </tr>
    <tr>
      <th>2001</th>
      <td>5480653.0</td>
      <td>31158543.0</td>
      <td>8.076565e+07</td>
      <td>9.747554e+08</td>
      <td>200</td>
    </tr>
    <tr>
      <th>2002</th>
      <td>10086514.0</td>
      <td>38171918.0</td>
      <td>8.885957e+07</td>
      <td>9.230152e+08</td>
      <td>200</td>
    </tr>
    <tr>
      <th>2003</th>
      <td>8755325.0</td>
      <td>44484134.0</td>
      <td>9.371740e+07</td>
      <td>1.118887e+09</td>
      <td>200</td>
    </tr>
    <tr>
      <th>2004</th>
      <td>10898337.0</td>
      <td>46367152.0</td>
      <td>9.729675e+07</td>
      <td>9.289742e+08</td>
      <td>200</td>
    </tr>
    <tr>
      <th>2005</th>
      <td>14189860.0</td>
      <td>47213083.5</td>
      <td>9.448475e+07</td>
      <td>8.959210e+08</td>
      <td>200</td>
    </tr>
    <tr>
      <th>2006</th>
      <td>16877870.0</td>
      <td>55745005.0</td>
      <td>9.959327e+07</td>
      <td>1.066180e+09</td>
      <td>200</td>
    </tr>
    <tr>
      <th>2007</th>
      <td>18160598.0</td>
      <td>55751313.5</td>
      <td>1.115311e+08</td>
      <td>9.609965e+08</td>
      <td>200</td>
    </tr>
    <tr>
      <th>2008</th>
      <td>19152009.0</td>
      <td>51301159.0</td>
      <td>1.162683e+08</td>
      <td>1.003845e+09</td>
      <td>200</td>
    </tr>
    <tr>
      <th>2009</th>
      <td>18874808.0</td>
      <td>52130062.0</td>
      <td>1.284723e+08</td>
      <td>2.743578e+09</td>
      <td>200</td>
    </tr>
    <tr>
      <th>2010</th>
      <td>18495045.0</td>
      <td>60706384.5</td>
      <td>1.278470e+08</td>
      <td>1.066970e+09</td>
      <td>200</td>
    </tr>
    <tr>
      <th>2011</th>
      <td>19971259.0</td>
      <td>62458932.5</td>
      <td>1.346259e+08</td>
      <td>1.341511e+09</td>
      <td>200</td>
    </tr>
    <tr>
      <th>2012</th>
      <td>21107746.0</td>
      <td>61663992.0</td>
      <td>1.475370e+08</td>
      <td>1.518813e+09</td>
      <td>200</td>
    </tr>
    <tr>
      <th>2013</th>
      <td>23980000.0</td>
      <td>68586212.0</td>
      <td>1.453890e+08</td>
      <td>1.280802e+09</td>
      <td>200</td>
    </tr>
    <tr>
      <th>2014</th>
      <td>22706304.0</td>
      <td>72084134.0</td>
      <td>1.499789e+08</td>
      <td>1.104054e+09</td>
      <td>200</td>
    </tr>
    <tr>
      <th>2015</th>
      <td>24817852.0</td>
      <td>72145657.0</td>
      <td>1.637093e+08</td>
      <td>2.068224e+09</td>
      <td>200</td>
    </tr>
    <tr>
      <th>2016</th>
      <td>22955486.0</td>
      <td>75353022.5</td>
      <td>1.618727e+08</td>
      <td>1.153296e+09</td>
      <td>200</td>
    </tr>
    <tr>
      <th>2017</th>
      <td>20460352.0</td>
      <td>60999583.0</td>
      <td>1.710455e+08</td>
      <td>1.332540e+09</td>
      <td>200</td>
    </tr>
    <tr>
      <th>2018</th>
      <td>22075730.0</td>
      <td>73714586.5</td>
      <td>1.706677e+08</td>
      <td>2.048360e+09</td>
      <td>200</td>
    </tr>
    <tr>
      <th>2019</th>
      <td>18653107.0</td>
      <td>63349461.0</td>
      <td>1.771581e+08</td>
      <td>2.799439e+09</td>
      <td>200</td>
    </tr>
    <tr>
      <th>2020</th>
      <td>4693664.0</td>
      <td>10995388.0</td>
      <td>3.927872e+07</td>
      <td>4.732304e+08</td>
      <td>200</td>
    </tr>
    <tr>
      <th>2021</th>
      <td>7388603.0</td>
      <td>26511473.0</td>
      <td>9.124175e+07</td>
      <td>1.910983e+09</td>
      <td>200</td>
    </tr>
    <tr>
      <th>2022</th>
      <td>7177868.0</td>
      <td>21745864.0</td>
      <td>1.043694e+08</td>
      <td>2.320250e+09</td>
      <td>200</td>
    </tr>
    <tr>
      <th>2023</th>
      <td>8184539.0</td>
      <td>36061386.5</td>
      <td>1.224004e+08</td>
      <td>1.446938e+09</td>
      <td>200</td>
    </tr>
    <tr>
      <th>2024</th>
      <td>7206741.0</td>
      <td>21502018.5</td>
      <td>9.267937e+07</td>
      <td>1.698773e+09</td>
      <td>200</td>
    </tr>
  </tbody>
</table>
</div>



## Graphs


```python
# Line Chart for Yearly Revenue Trends\n",
movies.groupby("Year")["$Worldwide"].sum().plot(kind="line", marker="o", title="Total Worldwide Revenue Over Time")
plt.show()
```


    
![png](output_12_0.png)
    


this line chart is used to understand the total revenue over time and to see what year the peak of going to the movie theatre is.


```python
# Bar Chart for the top 5 movies by worldwide revenue
movies.nlargest(5, "$Worldwide").plot(kind="bar", x="Release Group", y="$Worldwide", title="Top 5 Movies by Worldwide Revenue")
plt.show()

# Bar Chart for the top 5 movies by domestic(USA) revenue
movies.nlargest(5, "$Domestic").plot(kind="bar", x="Release Group", y="$Domestic", title="Top 5 Movies by Domestic Revenue")
plt.show()

# Bar Chart for the top 5 movies by foreign(everywhere that is not USA) revenue
movies.nlargest(5, "$Foreign").plot(kind="bar", x="Release Group", y="$Foreign", title="Top 5 Movies by Foreign Revenue")
plt.show()
```


    
![png](output_14_0.png)
    



    
![png](output_14_1.png)
    



    
![png](output_14_2.png)
    


These bar graphs are to show the movies that generated the most revenue worldwide, domestically (USA), and in foreign countries (everywhere except the USA). From there I was able to see the 2 movies that are consistent throughout the 3 grpahs is Avatar and Avengers: Endgame.


```python
# Display Avatar and Avengers: Endgame\n",
specific_movies = movies.query("`Release Group` in ['Avatar', 'Avengers: Endgame']")
display(specific_movies)
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
      <th>Rank</th>
      <th>Release Group</th>
      <th>$Worldwide</th>
      <th>$Domestic</th>
      <th>Domestic %</th>
      <th>$Foreign</th>
      <th>Foreign %</th>
      <th>Year</th>
      <th>Genres</th>
      <th>Rating</th>
      <th>Vote_Count</th>
      <th>Original_Language</th>
      <th>Production_Countries</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1800</th>
      <td>1</td>
      <td>Avatar</td>
      <td>2.743578e+09</td>
      <td>749766139.0</td>
      <td>27.3</td>
      <td>1.993811e+09</td>
      <td>72.7</td>
      <td>2009</td>
      <td>Action, Adventure, Fantasy, Science Fiction</td>
      <td>7.583/10</td>
      <td>31654.0</td>
      <td>en</td>
      <td>United States of America, United Kingdom</td>
    </tr>
    <tr>
      <th>3800</th>
      <td>1</td>
      <td>Avengers: Endgame</td>
      <td>2.799439e+09</td>
      <td>858373000.0</td>
      <td>30.7</td>
      <td>1.941066e+09</td>
      <td>69.3</td>
      <td>2019</td>
      <td>Adventure, Science Fiction, Action</td>
      <td>8.246/10</td>
      <td>25780.0</td>
      <td>en</td>
      <td>United States of America</td>
    </tr>
  </tbody>
</table>
</div>


From here, I have made the assumption that the most profitable movies fall under the Action, Science Fiction, and Adventure genres.

## Reflection

***What do your three files look like online?  Which one looks best?***

The ipynb file looks better online. In the html file, all images are gone and replaced with unreadable code.

***Do you think there are any problems with your dataset?  Explain.***

I think the dataset is fairly clean and easy to understand but the only problem that I would point out is the Genres and Production_Countries columns. Since most movies hold multiple genres and production countries, being able to pull specfic genres or production countries is not possible. To fix this I would set a "Primary" for both columns. For genres, I would identify a primary genre that movies falls under. For production countries, I would put the primary as the country that the majority of the movie was filmed in. All other genres and production countries may be placed in a "Secondary" column.
    "\n",
    "***What Questions do you have about the data?  Is there a problem you would want to solve?  Something to predict?***\n",
    "\n",
    "A question I have about the dataset is why was the USA set as the domestic value across all movies? I can understand that most movies are produced in the USA and it may have been for simplicity. But for the movies that are not produced in the USA, the revenue is all grouped in the \"$Foreign\" column; so you are not able to see how much revenue is generated in that home country, it is grouped in with the rest of the world.
