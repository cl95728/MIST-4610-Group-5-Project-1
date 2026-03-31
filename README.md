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
The database features the entities Artist, Artist Group, Album, Song, Producer, Song Producer, Song Record Label, Location, Sales, Total Units, and Streams Total. 
 
Record Label represents the subsidiary that each artist is signed to. It is the child table of location, as a location could include many record labels. Other attributes include the albums unique identifier, it’s name, the city in which it is headquartered in, and the year it was founded 
 
Location represents the relevant areas that house producers, record labels, and artists. Since none of these entities can have more than one location, the entity has no foreign keys. state 
 
﻿Each Artist has a single Record Label and a single Location 
﻿An Artist may put out more than one Album 
﻿There are several Songs on each Album 
﻿Songs generate streaming data through the Stream Total table 
﻿Unit Total and Sales tables are how albums make money 
A junction table links Producers to Songs  
<img width="892" height="892" alt="image" src="https://github.com/user-attachments/assets/de6c0221-a936-4248-a618-99ad375cd79e" />
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
 

 
