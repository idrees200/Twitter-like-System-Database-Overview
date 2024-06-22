# Twitter-like System Database Overview

This repository contains SQL scripts and data for a Twitter-like system database. The database schema is designed to manage users, tweets, hashtags, user interests, user interactions (following), and tweet likes.

## Database Schema

### Tables:

1. **Users:**
   - User_ID (int, primary key)
   - UserName (varchar(20), unique)
   - Age (int)
   - Country (varchar(20))
   - privacy (int)

2. **Following:**
   - FollowerUserName (varchar(20), foreign key references Users(UserName))
   - FollowedUserName (varchar(20), foreign key references Users(UserName))
   - primary key (FollowerUserName, FollowedUserName)

3. **Tweets:**
   - TweetID (int, primary key)
   - UserName (varchar(20), foreign key references Users(UserName))
   - Text (varchar(140))

4. **Likes:**
   - TweetID (int, foreign key references Tweets(TweetID))
   - LikeByUserName (varchar(20), foreign key references Users(UserName))
   - LikeOnDate (date)
   - primary key (TweetID, LikeByUserName)

5. **Interests:**
   - InterestID (int, primary key)
   - Description (varchar(30))

6. **UserInterests:**
   - UserName (varchar(20), foreign key references Users(UserName))
   - InterestID (int, foreign key references Interests(InterestID))
   - primary key (UserName, InterestID)

7. **Hashtags:**
   - HashtagID (int, primary key)
   - Hashtag (varchar(30))

## Usage

This database provides a structured approach to simulating a social media platform similar to Twitter. It includes relationships between users, their tweets, interests, and interactions such as following and liking tweets.

### Files

- **create_database.sql:** SQL script to create the database schema.
- **insert_data.sql:** SQL script to insert sample data into the tables.
- **README.md:** This file, providing an overview of the database structure.

### Dependencies

- **SQL Server:** Ensure you have SQL Server installed to run the provided scripts.
- **SQL Server Management Studio (SSMS)** or another SQL client for executing queries.

## Getting Started

1. **Setup Database:**
   - Execute `create_database.sql` in SQL Server Management Studio (SSMS) to create the database and tables.

2. **Insert Data:**
   - Execute `insert_data.sql` to populate the tables with sample data.

3. **Run Queries:**
   - Use SQL queries to interact with the database schema and retrieve information as needed.


