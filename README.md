# Application-of-the-cluster-algorithm (KMeans).

* We are provided with data from the sales team with an expection to identify the existing sub-groups there in
 
* The dataset has various features of which are expected to identify the one that will be relevant in the exercise

#### Below is the guide to how the algorithm will be implemented effectively

*  the relevant python libraries shall be implemented.

*  a wrangling function shall be build to aid in the cleaning of the availed dataset to make it ready for the algorithm

*  the default model shall be built and trained to act as our refernce for the final model

*  with aid of the elbow technique, the required values of the number of clusters will be determined

*  then the final model shall be built

*  the obtained labels shall be appended to the original for analysis

*  and finally a dictinary for the different groups shall be created based on which further analysis shall be conducted to clearly understand the clusters

#### importing of the relevant python libraries

#### Building a wrangling function with below functionalities

*  identifying the object features wthin the dataset with the number of unique values not exceeding a count of 12

* it also identifies the numerical features while eliminating the ID feature

* later the columns are combined to call the reuired columns that shall relevant for the exercise

* it then applies the OneHotEncoder to the categorical features using the caterigorical names as the column headings

#### scaling the data features

Since the data various scales of the values, there is need to harmonise the values. This was effected with the aid of the standard scaler that 

produced features values with a mean  of zero (0) and standard deviation of one (1) as shown below from the execution of the code 

"data_scaled.describe()" in the proceeding line of code

#### Principal component analysis (PCA)
application of the principal component analysis (PCA) on the available scaled features to extract the variance in the features

for this PCA, the first two columns of variance were exxtracted as they represent most of the variance in the featrures

Principal Component 1 (PC_1) and Principal Component 2 (PC_2)

* a scatter plot was made for the extracted principal components to look out for available groups in the data

* from the scatter plot, there are two visible clusters, how this will be further evaluated to confirm the number of clusters

#### Building the initial clustering model

* the initial model is build on the asumption that there are only two cluster, therefore k = 2
* evaluating the model using the inertia error and the silhouette score values which will later be compared with those of the final model

#### Implementation of the elbow technique

* lets initialize our range of the number of clusters as ranging from 2 to 20 (range(2,21,1))

* we shall build different models using the various values of number of clusters

* for each model, the inertia errors and the silhouette scores shall be obtained and appended to our initialzed lists of inertia_errors and Silohuette_scores
  
* a plot of the number of clusters and the obtained inertia errors will give us the elbow structure

* from the obtained plot, the value of number of clusters in the range 5 to 7,

* the number will be confirmed with the plot of silhouette scores against number clusters and the one with a higher silhouette scores shall be taken

* from the above plot, the number of clusters to be considered are 5, as it has the highest silhouette score

* therefore our final model is to built with n_clusters = 5

* Finally, we append the labels from the model to the original data for further analysis and understanding of the clusters.
