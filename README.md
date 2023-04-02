# Hotel Booking Data Analysis

### Intro
The dataset used can be found in this github repository and is originally retrieved from [here](https://www.sciencedirect.com/science/article/pii/S2352340918315191). It contains booking information for city hotels and resort hotels, and includes information such as when the booking was made, length of stay, the number of adults, children, and the number of available parking spaces, and more. All personally identifying information has been removed from the data and replaced with fictitious data. To analyze this dataset, we'll be using MySQL to write the queries. 

## Schema 

<img width="195" alt="Schema" src="https://user-images.githubusercontent.com/60675257/229370755-0d44dcf5-9a8b-4932-bc32-fe2a05d45db2.png">

### 1) Exploratory Analysis
 
 <p> Taking a look at the data to identify any potential issues or limitations that may affect our analysis.</p>

<img width="1234" alt="Screen Shot 2023-04-02 at 12 23 24 PM" src="https://user-images.githubusercontent.com/60675257/229365721-2173b35d-ff9a-4739-a5da-5bad24f2d1f3.png">

<img width="1242" alt="Screen Shot 2023-04-02 at 1 28 41 PM" src="https://user-images.githubusercontent.com/60675257/229369040-492d77ab-2db5-4dc4-bbba-5fb93bd8506c.png">

The data in the **'company'** and **'agent'** columns typically contain company and agent numbers. However, some customers choose not to use an agent or company to book a hotel, resulting in null values for these columns. This indicates that the booking was made directly with the hotel or through some other means not tracked.

### 2) Removing null values 

Replacing 'company' and 'agent' null values with 0. This will allow less issues when performing calculations or aggregations on the dataset.

<img width="1228" alt="Screen Shot 2023-04-02 at 1 19 18 PM" src="https://user-images.githubusercontent.com/60675257/229368552-9fe26250-e219-4926-ae24-947ef68ddefe.png">

<img width="1421" alt="Screen Shot 2023-04-02 at 2 02 52 PM" src="https://user-images.githubusercontent.com/60675257/229370621-fe0fcd04-30f0-4b4b-941b-7ff228488cfc.png">


### 3) Adding the necessary columns

Total staying days in hotels:

<img width="1421" alt="Screen Shot 2023-04-02 at 1 58 49 PM" src="https://user-images.githubusercontent.com/60675257/229370427-2febdb6a-181a-4230-8382-98568ad39d43.png">

 <img width="1238" alt="Screen Shot 2023-04-02 at 1 56 41 PM" src="https://user-images.githubusercontent.com/60675257/229370337-b37ac51a-839c-4e0a-ad23-a202dda3201d.png">
 
 ### 4) Retrieving insights from data
 
 Q1) Which agent makes the most bookings?
 
 <img width="1216" alt="Screen Shot 2023-04-02 at 2 39 22 PM" src="https://user-images.githubusercontent.com/60675257/229372276-559e223f-92af-48f2-9e8a-cb9147bbf9a2.png">
 
 Q2) What is the most popular month for bookings?
<img width="1217" alt="Screen Shot 2023-04-02 at 2 47 33 PM" src="https://user-images.githubusercontent.com/60675257/229372656-6a12fa98-6dbd-4aa4-9e67-550c8fce682e.png">
