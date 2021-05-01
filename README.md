# Movie Recommendation Engine
Build a Netflix Style Recommendation Engine with Amazon SageMaker

## Use Case and Data
For a Netflix-style recommendation engine, I decided to recommend movies. I [downloaded](https://datasets.imdbws.com/) `title.akas.tsv.gz`, `title.basics.tsv.gz`, and `title.ratings.tsv.gz` from [IMDb](https://www.imdb.com/interfaces/).

## Jupyter Hosted Notebook
To start the data inspection process, I launched a Jupyter hosted notebook via the `jupyter notebook` command on my command line. For the Jupyter notebook, I used Python and data science libraries Pandas and Matplotlib to work with my data.

## Data Preparation & Transformation
I put the data in a format a machine can learn from by narrowing down to movies with original titles, removing unnecessary columns, removing null values, converting some string columns into integers, and merging the DataFrames.

## Data Inspection & Visualization
To gain domain knowledge of my data, I created scatter plots so that I can easily detect anomalies and outliers.

## Training
After transforming and inspecting the data, I started the training process using k-means clustering with the sci-kit learn library so I can group my data to make recommendations.
```
# Import KMeans
from sklearn.cluster import KMeans

# Create an instance of KMeans to find 20 clusters
km = KMeans(n_clusters=20, random_state=0)

# Use fit_predict to cluster the dataset
# Returns a cluster prediction for each student / ie cluster labels
predictions = km.fit_predict(movies_list)
```
## Recommend
After identifying my clusters, as part of recommending movies, I analyzed the clusters to find commonalities.

## Amazon SageMaker
Aftering finishing the Jupyter notebook, I wrote a CloudFormation template that creates a notebook instance of SageMaker that associates with this Git repository.
