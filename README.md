# Used Car Price Analysis - Data Mining Project

This project is about analyzing a used cars dataset and trying to figure out what actually affects the selling price. It covers cleaning the data, exploring it, clustering the cars into market segments, and building a couple of different models to predict prices.

## Dataset

The data is the Vehicle Dataset from CarDekho, available on Kaggle:
https://www.kaggle.com/datasets/nehalbirla/vehicle-dataset-from-cardekho

It has details about used cars like the manufacturing year, kilometers driven, fuel type, transmission, number of owners, engine specs, and of course the selling price.

## What's in the notebook

- Basic data exploration (checking nulls, duplicates, distributions, plotting price against year/km driven, etc.)
- Cleaning the messy columns - a lot of the original columns like mileage, engine, torque and max_power come as text with units mixed in, so these get split into proper numeric columns
- Handling missing values and removing outliers
- Scaling the numeric features and one-hot encoding the categorical ones
- PCA to reduce the number of features while keeping most of the variance
- Clustering with K-Medoids and Hierarchical clustering to split the cars into market segments (budget, mid-range, premium)
- A fuzzy logic system that estimates price ranges based on car age, power, torque and segment
- A genetic algorithm used for feature selection, then a final linear regression model trained on the selected features

## Libraries used

pandas, numpy, matplotlib, seaborn, scikit-learn, scikit-learn-extra (for KMedoids), scipy (for hierarchical clustering / dendrograms), scikit-fuzzy

## Running it

1. Download the dataset from the Kaggle link above.
2. Put the csv file in the project folder (or a `data/` folder).
3. Change the path in the data loading cell to point to wherever you put the csv - right now it's set to a local path on my machine so you'll need to update it.
4. Run the notebook cell by cell.

## Some notes

-Place the downloaded CSV file (named `Car details v3.csv`) inside a `data/` folder in the project's root directory. The notebook already points to a relative path (`data/Car details v3.csv`), so no code changes should be needed as long as the file is in the right place.
- The clustering results ended up giving 3 clear segments (premium/mid/budget) that mainly differ by price, age and mileage.
- Newer cars with less mileage sell for noticeably more, and most cars in the dataset are first-owner and sold by individuals rather than dealers.

This was done as part of a Data Mining course project.
