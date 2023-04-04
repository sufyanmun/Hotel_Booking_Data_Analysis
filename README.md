# Hotel Booking Data Analysis

### Intro
The dataset used can be found in this github repository and is originally retrieved from [here](https://www.sciencedirect.com/science/article/pii/S2352340918315191). It contains booking information for city hotels and resort hotels, and includes information such as when the booking was made, length of stay, the number of adults, children, and the number of available parking spaces, and more. All personally identifying information has been removed from the data and replaced with fictitious data. To analyze this dataset, we'll be using MySQL to write the queries. 

## Schema 
<img width="152" alt="Screen Shot 2023-04-03 at 7 09 58 PM" src="https://user-images.githubusercontent.com/60675257/229645950-f05486a3-e7e7-410e-9342-67dd1196a732.png">


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

Q3) What is the average length of stay for guests? 
<img width="1217" alt="Screen Shot 2023-04-03 at 6 44 08 PM" src="https://user-images.githubusercontent.com/60675257/229642753-7ee920b1-0bcb-4cc9-9b73-b1e9b798091c.png">

 ### 5) Creating Relevant KPIs 
 
 Q1) What is the lifetime value of a customer? & Which customer has the highest Customer Lifetime Value (CTV)?
 
 Since this dataset didn't have any unique identifier for each customer I had to get creative and use the customer's phone number. Assuming that the phone number is uniquely associated with each customer.
 
 <img width="1217" alt="Screen Shot 2023-04-03 at 7 04 37 PM" src="https://user-images.githubusercontent.com/60675257/229645285-24025a6a-b8e2-4cc2-bddc-b637ed678950.png">

Q2) What is the cancellation rate? 

<img width="1216" alt="Screen Shot 2023-04-03 at 10 25 10 PM" src="https://user-images.githubusercontent.com/60675257/229670730-fa55b0a5-3438-4897-b1b2-4fab581e7e4e.png">

Q2) What is the Revenue per available room (RevPAR)? 

<img width="1216" alt="Screen Shot 2023-04-04 at 11 45 05 AM" src="https://user-images.githubusercontent.com/60675257/229846304-91c043e2-9e2f-495a-a2e0-272f1d2860fc.png">
