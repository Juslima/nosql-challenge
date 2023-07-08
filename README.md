# nosql-challenge

# NoSQL_setup_starter

The data demonstrates a process of working with the UK Food Standards Agency's food hygiene ratings data. The task at hand is to evaluate and manipulate the ratings data to assist the editors, journalists, and food critics of the food magazine "Eat Safe, Love" in selecting establishments for future articles. By analyzing the ratings and performing database operations, the data can be used to make informed decisions regarding which establishments to feature in the magazine's articles.

# Part 1: Database and Jupyter Notebook Set Up
   - A MongoClient is created, connecting to the local MongoDB instance.
   - The "uk_food" database is assigned to the variable `db`.
   - The available collections in the "uk_food" database are listed, and the "establishments" collection is found.

# Part 2. Update the Database:
   - A new restaurant named "Penang Flavours" is created as a dictionary called `new_restaurant`.
   - The `insert_one()` method is used to add the new restaurant document to the "establishments" collection.
   - The presence of the new restaurant in the collection is verified using the `find_one()` method.

   Find BusinessTypeID for "Restaurant/Cafe/Canteen":
   - The `find_one()` method is used to retrieve a document with the "BusinessType" field equal to "Restaurant/Cafe/Canteen".
   - Only the "BusinessTypeID" and "BusinessType" fields are returned.

   Update the new restaurant with the BusinessTypeID:
   - The `update_one()` method is used to update the new restaurant document with the correct "BusinessTypeID".

   Remove establishments in Dover Local Authority:
   - The `count_documents()` method is used to count the number of documents with "LocalAuthorityName" equal to "Dover".
   - The `delete_many()` method is used to remove all documents with "LocalAuthorityName" equal to "Dover".
   - The presence of any remaining documents with "LocalAuthorityName" equal to "Dover" is checked.

   Data Type Conversion:
   - The `update_many()` method is used to convert the data types of "longitude" and "latitude" fields from string to decimal numbers.
   - The `update_many()` method is used to convert the data type of "RatingValue" field from string to integer numbers.
   - Non-rating values are set to null using the `$set` operator.

The code snippets demonstrate how to set up a MongoDB database, insert new documents, update existing documents, and perform data type conversions on specific fields within the documents.

# NoSQL_analysis_starter
# Part 3: Exploratory Analysis

This data represents the results of exploratory analysis performed on a collection of establishments. Let's break down each part:

1. Which establishments have a hygiene score equal to 20? There are 41 establishments with a hygiene score of 20. Here is an example of one:

- Establishment Name: The Chase Rest Home
- Address: 5-6 Southfields Road, Eastbourne, East Sussex
- Business Type: Caring Premises
- Rating Value: 0

2. Which establishments in London have a RatingValue greater than or equal to 4? There are 34 establishments in London that have a RatingValue greater than or equal to 4. Here is an example of one:
   
- Establishment Name: Charlie's
- Address: Oak Apple Farm Building 103 Sheerness Docks, Sheppy Kent
- Business Type: Other catering premises
- Hygiene Score: 0

4. What are the top 5 establishments with a RatingValue rating value of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"? Here are the top 5 establishments with a `RatingValue` rating value of 5, sorted by the lowest hygiene score and nearest to the new restaurant "Penang Flavours":

1. **Establishment 1: Volunteer**
   - Business Name: Volunteer
   - Address: 130 - 132 Plumstead High Street, Plumstead, Greenwich
   - Business Type: Pub/bar/nightclub
   - Hygiene Score: 0

2. **Establishment 2: Plumstead Manor Nursery**
   - Business Name: Plumstead Manor Nursery
   - Address: Plumstead Manor School Old Mill Road, Plumstead, Greenwich
   - Business Type: Caring Premises
   - Hygiene Score: 0

3. **Establishment 3: Atlantic Fish Bar**
   - Business Name: Atlantic Fish Bar
   - Address: 35 Lakedale Road, Plumstead, Greenwich
   - Business Type: Takeaway/sandwich shop
   - Hygiene Score: 0

4. **Establishment 4: Iceland**
   - Business Name: Iceland
   - Address: 144 - 146 Plumstead High Street, Plumstead, Greenwich
   - Business Type: Retailers - supermarkets/hypermarkets
   - Hygiene Score: 0

5. **Establishment 5: Howe and Co Fish and Chips - Van 17**
   - Business Name: Howe and Co Fish and Chips - Van 17
   - Address: Restaurant And Premises 107A Plumstead High Street, Plumstead, Greenwich
   - Business Type: Mobile caterer
   - Hygiene Score: 0

5. How many establishments in each Local Authority area have a hygiene score of 0? There are 55 Local Authority areas in total, and the number of establishments with a hygiene score of 0 in each area is as follows:
   
- Thanet: 1130 establishments
- Greenwich: 882 establishments
- Maidstone: 713 establishments
- Newham: 711 establishments
- Swale: 686 establishments
- Chelmsford: 680 establishments
- Medway: 672 establishments
- Bexley: 607 establishments
- Southend-On-Sea: 586 establishments
- Tendring: 542 establishments
These are the first 10 results, and there are 55 rows in total. Each row represents a Local Authority area, and the 'count' column indicates the number of establishments in that area with a hygiene score of 0.





