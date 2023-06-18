# Fauna Forecast

## Introduction
The United States National Park Service preserves over 80,000,000 square miles of beautiful nature. In these locations we find over 40,000 unique fauna and flora.

In this analysis we saught to uncover trends in biodiversity in hopes of guiding the National Park Service in how best to direct their future conservation efforts.

![Image of UnCaptcha Poster](./Poster.png)

## Data
We used three main datasets for this project:

* [The US National Park Service's Species Dataset](https://irma.nps.gov/NPSpecies/Search/SpeciesList/)
* [The US National Park Service's Visitation Dataset](https://irma.nps.gov/Stats/SSRSReports/National%20Reports/Annual%20Visitation%20and%20Record%20Year%20by%20Park%20(1904%20-%20Last%20Calendar%20Year))
* [Kaggle's Location Dataset](https://www.kaggle.com/datasets/nationalparkservice/park-biodiversity)

The species dataset contains data for each park of which species have been found there. For example, if an American Bison is found in Yellowstone, there is a row that says as such.
The visitation dataset contains data on the number of visitors to each park since their inceptions. For this project we take an average of the last 5 years of each park.
The location dataset contains information about each park's latitude, longitude, and state. This is used in our machine learning and hypothesis testing.

After collecting and cleaning all of the data, we merge it into one dataset found in `data.db`. We have over 90,000 rows of data, with each row representing a species being found in a park. These rows will contain the specie's information and the park's information, which now includes the information from the visitation and location datasets.

Note, often in this project we refer to biodiversity which is not a column in the data, biodiversity is instead used to describe the distribution of the categories of fauna and flora. In hypothesis testing we also use it to mean the total number of unique species in a given park.

## Hypothesis Testing
First, we hypothesis test, to see if we can uncover any general trends about the National Parks. We run several of our hypothesis tests in `hypothesis_testing.ipynb`. Graphs can be seen in our poster.

Overall we found that very few general trends hold. Little can be said about biodiversity in terms of simple correlation with another statistic or in terms of drawing a line down the map and comparing latitudes and longitudes. We found that there are more varieties of fish in coastal states, but otherwise uncovered little even in the way of seemingly common sense trends. Because of this, we looked to machine learning to uncover more nuanced trends in the data.

## Machine Learning
To look for more nuanced trends we turned to machine learning. Code can be found in `machine_learning.ipynb` and visuals can be found on our poster above.

### Deep Learning to Predict Biodiversity
In hopes of understanding if there were more nuanced trends to even be uncovered, we built a deep learning model to predict biodiversity distributions based on our other data. After 25 epochs of training our model has a loss of 0.02 indicating a 2% absolute difference in actual vs. predicted biodiversity distributions. This means our model is extremely accurate in predictions, suggesting that more nuanced trends are here to be discovered.

### KMeans Clustering the Parks
Now knowing more nuanced trends exist, we saught to KMeans cluster the parks. After clustering and plotting back onto a map of the United States (as seen on our poster) we can see no clear groupings based on location, rather, more nuanced trends reveal themselves as we dive deeper into these results. As shown on our poster, we can group these parks through several more detailed factors such as type of terrain, conditions of the park, and biodiversity distribution oddities. All in all, this data shows us that there is are meaningful relationships between the parks and we can use these to guide future efforts.

## Future Efforts
The goal of this project is to guide future conservation efforts of the United States National Park Service. Trends are more nuanced than simply viewing a map and we've uncovered meaningful groupings to further explore. From our initial observations, the National Park Service should put their next conservation efforts into protecting more areas with the Northern Forests biome, found in the north eastern United States, as well as protecting more areas with extreme conditions such as volcanic activity, reefs, and extreme temperatures.

We hope that future work will build off of our data and analyzed trends to further understand the nuances of the relationships between the parks and how the National Park Service can best build toward protecting more endangered species and delicate ecosystems.
