# Data Partitioning

### 1. Partitioning Methods <a href="#1.-partitioning-methods" id="1.-partitioning-methods"></a>

There are many different schemes one could use to decide how to break up an application database into multiple smaller DBs. Below are three of the most popular schemes used by various large-scale applications.\


![](<../../.gitbook/assets/image (24).png>)

**a. Horizontal Partitioning:** In this scheme, we put different rows into different tables. For example, if we store different places in a table, we can decide that locations with ZIP codes less than 10000 are stored in one table and places with ZIP codes greater than 10000 are stored in a separate table. This is also called range-based Partitioning as we are storing different ranges of data in separate tables. Horizontal Partitioning is also known as Data Sharding.

The key problem with this approach is that if the value whose range is used for Partitioning isn’t chosen carefully, then the partitioning scheme will lead to unbalanced servers. In the previous example, splitting locations based on their zip codes assume that places will be evenly distributed across the different zip codes. This assumption is not valid as there will be a lot of places in a thickly populated area like Manhattan as compared to its suburb cities.

**b. Vertical Partitioning:** In this scheme, we divide our data to store tables related to a specific feature in their own server. For example, if we are building an Instagram-like application - where we need to store data related to users, photos they upload, and people they follow - we can decide to place user profile information on one DB server, friend lists on another, and photos on a third server.

Vertical Partitioning is straightforward to implement and has a low impact on the application. The main problem with this approach is that if our application experiences additional growth, then it may be necessary to further partition a feature specific DB across various servers (e.g. it would not be possible for a single server to handle all the metadata queries for 10 billion photos by 140 million users).

**c. Directory-Based Partitioning:** A loosely coupled approach to work around issues mentioned in the above schemes is to create a lookup service that knows your current partitioning scheme and abstracts it away from the DB access code. So, to find out where a particular data entity resides, we query the directory server that holds the mapping between each tuple key to its DB server. This loosely coupled approach means we can perform tasks like adding servers to the DB pool or changing our partitioning scheme without having an impact on the application.
