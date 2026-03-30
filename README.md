# MIST-4610-Group-5-Project-1
# Team Name: Group 5

### Team Members
* **Catherine Lusick** - [View GitHub Profile](https://github.com/username1)
* **Emmy Nguyen** - [View GitHub Profile](https://github.com/username2)
* **Diyaa Patel** - [View GitHub Profile](https://github.com/username3)
* **Caleb Rivers** - [View GitHub Profile](https://github.com/username4)
* **Isaac Lee** - [View GitHub Profile](https://github.com/username4)

### Project Description
The purpose of this relational database is to model a music group that distributes songs and albums from a variety of different artists that are signed to various different subsidiary record labels. The model tracks artists, albums, songs, record labels, contracts, and revenue generated through both streaming and unit sales, with the central entity being the artists, as their products are the source of revenue.  Managers can use the system to assess artist performance, identify high-performing genres and locations, and make strategic choices about talent acquisition, contract management, and marketing. Through querying the database, our team aims to prove that our database is both reliable and useful for helping the executive team gain insight into the current operations of the music group, as well as ensuring that it can be used to make decisions about the future of the firm.
### Data Model 
The database features the entities Artist, Artist Group, Album, Song, Producer, Song Producer, Song Record Label, Location, Sales, Total Units, and Streams Total. 
 
Record Label represents the subsidiary that each artist is signed to. It is the child table of location, as a location could include many record labels. Other attributes include the albums unique identifier, it’s name, the city in which it is headquartered in, and the year it was founded 
 
Location represents the relevant areas that house producers, record labels, and artists. Since none of these entities can have more than one location, the entity has no foreign keys. state 
 
﻿Each Artist has a single Record Label and a single Location 
﻿An Artist may put out more than one Album 
﻿There are several Songs on each Album 
﻿Songs generate streaming data through the Stream Total table 
﻿Unit Total and Sales tables are how albums make money 
A junction table links Producers to Songs  
