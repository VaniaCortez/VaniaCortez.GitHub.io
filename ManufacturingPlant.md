# Silica Concentrate Prediction in Iron Ore

It’s not a typical day where I am searching on google for the meaning of froth flotation. 

I was surprised to learn about the process of mineral separation through a process called froth flotation. It is satisfying and intriguing to see how this method is used to separate minerals. 

Froth flotation is a method used in the mining industry to separate valuable minerals from unwanted material. It involves a mixture of ore and water into a tank known as a flotation cell. Then, it forms air bubbles, and the valuable minerals attach to the bubbles form a frothy layer on the surface. This frothy material, called the concentrate, is then skimmed off the top, while the unwanted material sinks to the bottom. 

The process is named froth flotation because it relies on the formation of a frothy layer on the surface.

## The Data

This dataset is from March 2017 – September 2017.
Click [here](https://www.kaggle.com/datasets/edumagalhaes/quality-prediction-in-a-mining-process?resource=download) to obtain the dataset. 

The purpose of this project is to predict the % Silica concentrate.  

Silica is considered a gangue mineral, meaning that it is a mineral that is unwanted and not valuable. In iron ore flotation, silica is often present in the ore and can be separated from the valuable iron minerals using various reagents such as Amina. 

In this analysis, we can provide an approximation of the concentration of silica in iron ore, thus reducing the amount of time and resources needed for the detection process during iron ore processing.

To conduct this data analysis, I used a browser-based Python called Deepnote. 

### Importing the libraries

![image](https://user-images.githubusercontent.com/120342460/215173547-d03e27a4-2b9f-43b6-a910-6be32103a4ad.png)

### Importing the dataset
converting the commas to decimal

![image](https://user-images.githubusercontent.com/120342460/215173740-1bb24719-2666-482a-8549-5790426bddad.png)

Show the first 5 rows of the data and all columns

<img src="images/df2.png?raw=true"/>

### Basic Analysis of Dataset

The dataset has 737,453 rows and 24 columns.

<img src="images/df3.png?raw=true"/>

<img src="images/df4.png?raw=true"/>

We can see that the date column is being read as a string

<img src="images/df5.png?raw=true"/>

Using Pandas function called *to_datetime()*, to convert the date to datetime

![image](https://user-images.githubusercontent.com/120342460/215181974-c70862f5-375e-4edb-9be4-2bef05572002.png)

Filter the rows and create a new data frame called df_sept to only show 9/1/2017

![image](https://user-images.githubusercontent.com/120342460/215182197-29c7c4aa-9383-4d9c-96d3-faec32be0a02.png)

<img src="images/df8.png?raw=true"/>

Heatmap to illustrate correlation between each column

![image](https://user-images.githubusercontent.com/120342460/215182349-1570323f-2545-4fbd-a19a-ebb8ea49f125.png)

<img src="images/df10.png?raw=true"/>

Create a variable that is a list of all the important columns we want to focus on

![image](https://user-images.githubusercontent.com/120342460/215182509-365852f5-cc82-4f05-9b6d-fae7b93ca82b.png)

<img src="images/df12.png?raw=true"/>

Focusing on the correlation between important columns only

<img src="images/df13.png?raw=true"/>

Taking a closer look at the % iron concentrate by the hour to see if there are any trends

<img src="images/df14.png?raw=true"/>

Create line charts for all important columns 

![image](https://user-images.githubusercontent.com/120342460/215183924-723e5c5b-42ca-4e49-94b7-ed0a9783c8c1.png)

<img src="images/df16.png?raw=true"/>

<img src="images/df17.png?raw=true"/>

<img src="images/df18.png?raw=true"/>

<img src="images/df19.png?raw=true"/>

<img src="images/df20.png?raw=true"/>

Iron Concentrate increases between 4 AM – 6 AM and 7 PM – 9 PM. 

Silica Concentrate decreases between 12 AM – 6 AM and 8 PM – 10 PM. 

It appears that as the **concentration of Iron increases, the concentration of Silica decreases**. 

We can also note that Ore Pulp Flow and Amina Flow both had peaks during the early morning hours when the concentration of silica was at its lowest. This suggests that there may be a relationship between silica concentrate, Ore Pulp Flow and Amina Flow, whereas **Silica decreases, Ore pulp flow and Amina flow increase**. 

As Amina is used as a reagent to separate the gangue mineral such as silica from iron ore, it is likely that the concentration of Amina and the concentration of silica are inversely related. The increased usage of Amina would lead to decreased concentration of silica in the ore pulp and vice versa. 

This relationship also explains how Ore Pulp Flow and Amina Flow are related, as the increase in Amina flow is likely to result in a decrease in silica concentration, which in turn leads to an increase in Ore Pulp Flow.

However, it is important to note that this conclusion is based on data from September 1st and may not be representative of the overall relationship between the variables. 

If you enjoyed this blog, please feel free to connect with me on [Linkedin!](https://www.linkedin.com/in/vaniacortez/) 







