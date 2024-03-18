# nosql-challenge
Evaluation of ratings data in order to help journalists and food critics decide where to focus future articles.

In order to help The UK Food Standards Agency as an editor for their food magazine, you will need to accomplish the following:

- Create a new repository for this project called nosql-challenge. Do not add this homework to an existing repository.

- Clone the new repository to your computer.

- Add your Jupyter notebook starter files and your Resources folder containing establishments.json to this folder.

- Push the changes to GitHub.

- Utilize the Module 12 files 

## Part 1: Database and Jupyter Notebook Set Up
The task involves setting up a MongoDB database named uk_food and importing data from the establishments.json file into a collection named establishments. This process is done using NoSQL_setup_starter.ipynb. After importing the data, libraries such as PyMongo and pprint are imported. An instance of the MongoClient is created to connect to the MongoDB server. The correctness of the database creation and data loading is verified by listing the databases and collections. One document from the establishments collection is retrieved and displayed using find_one and pprint. Finally, the establishments collection is assigned to a variable for further analysis.


## Part 2: Update the Database


* Data for the "Penang Flavours" restaurant is inserted into the establishments collection.

* A query is executed to find the BusinessTypeID for "Restaurant/Cafe/Canteen" and returns only the BusinessTypeID and BusinessType fields.

* The "Penang Flavours" document is updated with the correct value for BusinessTypeID.

* Documents in the collection where "Dover Local Authority" is the value for LocalAuthorityName are deleted.

* A count_documents() check is performed before and after the removal of the Dover documents to ensure they were removed.

* An update_many() query is executed to convert the latitude and longitude fields from strings to decimal numbers and RatingValue to integers.


## Part 3: Exploratory Analysis

Here are the questions provided by Eat Safe, Love for exploring the dataset:

1. Which establishments have a hygiene score equal to 20?

   * Use count_documents to display the number of documents and pprint to display the first document in the results.
        
   * Convert the result to a Pandas DataFrame, print the number of rows, and display the first 10 rows.

2. Which establishments in London have a RatingValue greater than or equal to 4?
      
   * Use $regex to search for establishments in London and filter those with a RatingValue greater than or equal to 4.
   
   * Display the results as described in question 1.

3. What are the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"?

   * Compare the geocodes to find the nearest locations to "Penang Flavours".
   
   * Search within 0.01 degree on either side of the latitude and longitude.
   
   * Display the results as described in question 1.

4. How many establishments in each Local Authority area have a hygiene score of 0? Sort the results from highest to lowest, and print out the top ten local authority areas.

   * Use aggregation to count establishments in each Local Authority area with a hygiene score of 0.
   
   * Sort the results from highest to lowest and display the top ten local authority areas.

These questions will help provide valuable insights into the dataset for Eat Safe, Love magazine.

## References

UK Food Standards Agency https://www.food.gov.uk. (2022). UK food hygiene rating data API. https://ratings.food.gov.uk/open-data/en-GB, Contains public sector information licensed under the Open Government Licence v3.0 3 https://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/.
Accessed Sept 9, 2022 and Sept 12, 2022 with the establishment settings as follows: longitude=51.5072, latitude=-0.1276, maxdistancelimit=4567, pagesize=10000, sortoptionkey=distance, pagenumber=(1,2,3,4,5,6,7,8).

Notes: 
* I used LA's to help with this assignment, for example I had trouble importing the json file.When I had first started this assignment, I was doing all the queries on Mongosh/terminal. Unfortunately, I noticed I had to be running my queries on my notebook when I was working on Part 2. I had to go back and change the style of the queries. I included the notebook that included the code of what I used which is pasted in the notebook. Therefore, make sure you are reading and following directions!Other sources will be listed in the notebook. 
  
