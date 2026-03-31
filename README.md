# MIST-4610-Group-5-Project-1
# Team Name: Group 5

## Team Members
* **Emmy Nguyen** - [View GitHub Profile](https://github.com/emmyn1/MIST-4610-Group-5-1)
* **Catherine Lusick** - [View GitHub Profile](https://github.com/cl95728/MIST-4610-Group-5-Project-1)
* **Diyaa Patel** - [View GitHub Profile](https://github.com/Diyaa-P13/MIST4610---Project-1-Group-5.git) 
* **Caleb Rivers** - [View GitHub Profile](https://github.com/username4)
  

## Project Description
The purpose of this relational database is to model a music group that distributes songs and albums from a variety of different artists that are signed to various different subsidiary record labels. The model tracks artists, albums, songs, record labels, contracts, and revenue generated through both streaming and unit sales, with the central entity being the artists, as their products are the source of revenue.  Managers can use the system to assess artist performance, identify high-performing genres and locations, and make strategic choices about talent acquisition, contract management, and marketing. Through querying the database, our team aims to prove that our database is both reliable and useful for helping the executive team gain insight into the current operations of the music group, as well as ensuring that it can be used to make decisions about the future of the firm.
## Data Model   
<img width="892" height="892" alt="image" src="https://github.com/user-attachments/assets/de6c0221-a936-4248-a618-99ad375cd79e" />

## Explanation of Data Model
The database features the entities Artist, Artist Group, Album, Song, Producer, Song Producer, Song Record Label, Location, Sales, Total Units, and Streams Total. 
 
Record Label represents the subsidiary that each artist is signed to. It is the child table of location, as a location could include many record labels. Other attributes include the albums unique identifier, it’s name, the city in which it is headquartered in, and the year it was founded 
 
Location represents the relevant areas that house producers, record labels, and artists. Since none of these entities can have more than one location, the entity has no foreign keys. state 
 
Each Artist has a single Record Label and a single Location 
An Artist may put out more than one Album 
There are several Songs on each Album 
Songs generate streaming data through the Stream Total table 
Unit Total and Sales tables are how albums make money 
A junction table links Producers to Songs  
## Data Dictionary 
### Artist Table 
| Column Name | Data Type | Description | 
|------------|----------|------------| 
| artistID | INT | Unique identifier for each artist | 
| legalName | VARCHAR | Artist's legal name |  
| stageName | VARCHAR | Artist's stage name | 
| debutDate | INT | Year that artist debuted |  
| artistAge | INT | Current age of the artist |  
| locationID | INT | References the artist's location |  
| recordLabelID | INT | Foreign key referencing the record label associated with the artist | 
 

### Artist Group 
| Column Name | Data Type | Description | 
|------------|----------|------------| 
| groupID | INT | Unique identifier for a collaboration group involving multiple artists on a song | 
| artistID | INT | Foreign key referencing an artist participating in the group |  
| songID | INT | Foreign key referencing the song associated with the group collaboration |  
| groupName | VARCHAR | Name of the artist group or collaboration |  
 

### Location 
| Column Name | Data Type | Description | 
|------------|----------|------------| 
| locationID | INT | Unique identifier for each location |  
| state | VARCHAR | State abbreviation where the location is based |  
| city | VARCHAR | City name of the location |  
| zipCode | INT | ZIP code associated with the location |  
 

### Contract 
| Column Name | Data Type | Description | 
|------------|----------|------------| 
| contractID | INT | Unique identifier for each contract |  
| startDate | DATE | Date the contract begins |  
| endDate | DATE | Date the contract ends |  
| royaltyRate | DECIMAL | Percentage of revenue paid to the artist |  
| advanceAmount | DECIMAL | Upfront payment given to the artist |  
| albumQty | INT | Number of albums required under the contract |  
| artistID | INT | Foreign key referencing the artist associated with the contract |  
 

### Record Label 
| Column Name | Data Type | Description | 
|------------|----------|------------| 
| recordLabelID | INT | Unique identifier for each record label |  
| labelName | VARCHAR | Name of the record label |  
| hqCity | VARCHAR | City where the laebl is headquartered |  
| yearFounded | INT | Year the record label was established |  
| locationID | INT | Foreign key referencing the location of the record label |  
 

### Album  
| Column Name | Data Type | Description | 
|------------|----------|------------| 
| albumID | INT | Unique identifier for each album |  
| albumName | VARCHAR | Name/title of the album |  
| releaseDate | DATE | Date of the album was released |  
| artistID | INT | Foreign key referencing the artist who created the album |  
| unitsSoldID | INT | Foreign key referencing the units sold record associated with the album |  
 

### Song  
| Column Name | Data Type | Description | 
|------------|----------|------------| 
| songID | INT | Unique identifier for each song | 
| songTitle | VARCHAR | Title of the song |  
| songDuration | VARCHAR | Duration of the song in minutes and seconds |  
| songGenre | VARCHAR | Genre classification of the song |  
| explicit | VARCHAR | Indicates whether the song contains explicit content (Yes/No) | 
| trackNumber | INT | Position of the song within the album |  
| albumID | INT | Foreign key referencing the album the song belongs to |  
| streamTotalID | INT | Foreign key referencing the total streaming data for the song |  
 

### Producer 
|Column Name | Data Type | Description | 
|------------|----------|------------| 
| producerID | INT | Unique identifier for each producer |  
| producerName | VARCHAR | Name of the music producer |  
| producerAge | INT | Age of the producer |  
| locationID | INT | Foreign key referencing where the producer is based in |  
 

### Song Producer  
|Column Name | Data Type | Description | 
|------------|----------|------------| 
| songProducerID | INT | Unique identifier for each song-producer relationship | 
| producerID | INT | Foreign key referencing the producer associated with the song |  
| songID | INT | Foreign key referencing the song associated with the producer |  
 

### Sales 
|Column Name | Data Type | Description | 
|------------|----------|------------| 
| salesID | INT | Unique identifier for each sales record |  
| revenueAmount | DECIMAL | Total revenue generated from sales |  
 
### Queries 
Show all of the albums for a specific artist 
Query 1 retrieves album names and release dates for a specific artist by filtering the Album table using the artist’s ID. It provides a simple view of the artist’s discography. 
<img width="534" height="544" alt="image" src="https://github.com/user-attachments/assets/8625a91a-9bb5-469e-ab75-1e7e162ab232" />
    

This query gives management quick access to an artist’s portfolio of work and track their release history. Understanding an artist’s output is important for planning future releases and activities. It also provides an idea of an artist’s content production and an overview of their career progression. 

Which songs are the most popular based on streaming? 
Query 2  retrieves song titles and their total stream counts by joining the Song and Stream Total tables. It ranks songs in descending order and returns the top 10 most-streamed tracks. 
<img width="730" height="528" alt="image" src="https://github.com/user-attachments/assets/a77e4728-cc72-4344-b779-75a69489b0d1" />

 

This query allows management to have a better understanding of which songs are currently the most popular among listeners. High streaming numbers indicate strong audience engagement and can guide the company’s promotion decisions. The results can also be utilized to maximize revenues from streaming platforms. 

Which albums have sold above 9,000,000 albums? 
Query 3 retrieves album names and total units sold by joining Album and Unit Total tables. It filters for albums exceeding 9,000,000 units and orders them from highest to lowest sales. 
<img width="746" height="566" alt="image" src="https://github.com/user-attachments/assets/96b7d072-a627-44f3-99c6-25ceca0d04c9" />

 

This query helps management identify which albums are performing well in terms of sales volume. By focusing on high-selling albums, the label can prioritize its resources for the successful projects. This insight can guide future investment strategies and production decisions. 


Which hip hop feature group has the most streams per collaboration? 
<img width="902" height="440" alt="image" src="https://github.com/user-attachments/assets/de7794d5-bf98-40fc-b244-1065ebf360bf" />


Where should we look for new talent? (Which location generates the most revenue) 
<img width="812" height="534" alt="image" src="https://github.com/user-attachments/assets/dfc98cc2-75ec-4209-a159-d20a8e30daf0" />

Do pre or post 2000s albums generate the most sales? 
<img width="744" height="496" alt="image" src="https://github.com/user-attachments/assets/29663913-b82b-4450-ba9b-89df3a08aa3b" />

 


Which record label has released the most albums? 
<img width="552" height="544" alt="image" src="https://github.com/user-attachments/assets/06121961-0bb9-41db-ae11-8001bc16236b" />
 

This query calculates the total number of albums released by each record label by joining the Album, Artist, and Record Label tables. It organizes the data by record label and counts the number of albums linked to each label, and then it arranges the results in descending order. This query assists management in determining which record labels are generating the most albums. Being able to identify which label is effectively, provides insight into overall label performance and market presence. This data can help make decisions about investments, resource distribution, and collaborations with successful labels.  

Which artists have more total album sales than the average total sales of all artists 
<img width="828" height="384" alt="image" src="https://github.com/user-attachments/assets/152db9d5-e9e0-4f79-bd1e-7410c5cb945d" />


This query calculates the total album sales for each artist by joining the Artist, Album, and Unit total tables. By comparing, each artist’s total sales to the average total sales across all artists using a subquery, it returns only those artists whose sales are higher than the average. This query assists management in determining artists who are exceeding average sales performance. These insights can help make decisions regarding marketing spending, resource distribution, contract extensions, and focusing on top-performing artists within the company.  

 

Which locations have a city name that ends with “ville” 
 <img width="572" height="374" alt="image" src="https://github.com/user-attachments/assets/3c992ce1-c44a-4dfd-9bf6-e13a5f822df2" />


Query 9 was created to pull a list of all cities in the Location table that ends with the letters "ville". To make the list clean and easy to read, I used a Regular Expression to find the pattern and grouped the results by city. This query helps filter through the location data more effectively. Instead of scrolling through rows of data, this helps identify specific areas based on their name. 

Display producers who have never worked on a song in the Hip Hop genre 
<img width="500" height="352" alt="image" src="https://github.com/user-attachments/assets/d80ea62b-5861-4c67-b14f-d2e84b7106ed" />

 
Query 10 is designed to find the names of producers in the Producer table who have never been associated with a "Hip Hop" song. To do this, I used a NOT EXISTS subquery to filter anyone linked to that specific genre. For every producer, the subquery checks the Song Producer table to see if they are linked to any song labeled 'Hip Hop'. If the subquery finds any match, NOT EXISTS becomes false, and that producer is excluded. This logic can be used to isolate producers who work exclusively in other genres like Country or Pop. It’s a great way to find a music producer whose specialty does not fall in Hip Hop. 
 
TABLE FOR QUERIES 
 

Feature 
Query 1 
Query 2 
Query 3 
Query 4 
Query 5 
Query 6 
Query 7 
Query 8 
Query 9 
Query 10 
Multiple table join 
 
              
             
x 
x 
x 
              
             
 
x 
subquery 
 
 
 
 
 
 
 
             
 
 
Group by 
 
 
 
 
 
 
             
 
 
 
Group by and having 
 
 
 
x 
 
 
 
             
 
 
Multi-condition where 
 
 
               
 
 
 
 
 
 
 
Built in functions 
 
              
              
x 
x 
x 
           
             
 
 
regexp 
 
 
 
 
 
x 
 
 
x 
 
Not exists 
 
 
 
 
 
 
 
 
 
x 
WHERE Clause 
                 
 
 
 
 
 
 
 
 
 
Basic SELECT  
                 
 
 
 
 
 
 
 
 
 
 
