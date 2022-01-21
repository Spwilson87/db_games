# db_games Created for sifa project
# Games Tracker

### Brief
Create a project which will demonstrate a culmination of all of the topics i have covered in my training. It will involve the following concepts and technologies:
* Project Management
* Python Fundamentals
* Python Testing
* Git
* Linux
* Python Web Development
* Databases
* Continuous Integration and Deployment (CI/CD)
* Cloud Fundamentals
* Containerisation

### Objective
* To create a web application that integrates with a database and demonstrates CRUD functionality.
* To utilise containers to host and deploy your application.
* To create a continuous integration (CI)/continuous deployment (CD) pipeline that will automatically test, build and deploy your application.

## Table of Contents

1. [Approach](#approach)
2. [Project Tracking](#tracking)
3. [Risk Assesment](#risk)
4. [My Application](#app)
5. [Database](#data)
6. [Testing](#test)
7. [CI/CD Pipeline](#pipe)

### How I Approched This <a name="approach"></a>
To acheive the objective I decided to create an game tracking app to allow a user to do the following:

* Store game details(satisfy 'Create')
 * Game name
 * Release year 
 * Genre
 * Developer
 * Publisher
 * Platform
 * Do they own the game
 * Do they want to add the game to a wishlist
 * Are they currently playing the game
 * Have they completed the game
* Allow game to be moved from wishlist to owned, then remove it from wishlist(satisfy 'Update' and 'Delete')
* Allow game to be moved from currently playing to completed, then remove it from currently playing(satisfy 'Update' and 'Delete')
* Allow game to ba added to Currently playing from owend games(satisfy 'Update')
* Allow user to view a table of owned games(satisfy 'Read')
* Allow user to view a table of games in wishlist(satisfy 'Read')
* Allow user to view a table of games currently playing(satisfy 'Read')
* Allow user to view a table of games completed(satisfy 'Read')

## Project Tracking <a name="tracking"></a>
To help manage my project I decided to use jira software to track and manage my project. I used it to display.
* MoSCoW prioritisation
![jira mosocw](https://user-images.githubusercontent.com/94057901/150413623-0f3b8e85-f97f-42d2-914a-b946df67ad68.png)

* User stories
![jira board](https://user-images.githubusercontent.com/94057901/150414854-8a726818-23bf-4d28-83c1-0798b07c4edf.png)


* Estimations of effort (e.g. story points)
I included the story points estimates on each item within jira 
![story point](https://user-images.githubusercontent.com/94057901/150414622-ef7bbf0f-5a6f-4507-ba92-d3597d0369d8.png)

## Version Control
Made use of a dev branch in git which i pushed up to my github repo as i made changes and progress. When i was satisfied the app was working i the merged it into master.

### Risk assesment <a name="risk"></a>
This is my risk assesment.


### My Application <a name="app"></a>
I wrote my application in python using flask and flask mysqldb utilising html and jinja so it can communicate with the back end python code.<br>
it exposes port 5000<br>
Wrote a dockerfile to build the app.<br>
Then wrote a docker-compose.yml which created multiple containers consisting of<br>
* mysql and config for the database exposing port 5506:3306
* php my admin on port 9080:880 which links to mysql, purely for convenience so i can see my database is working quicker.
* It also builds my app which links to mysql image and phpmyadmin image

## Application design
The front end of this application is simple at this stage. All the tables are searchable will auto create new table pages as they get populated and can be set to ascend or descend on each row.

User Brought to this page when they access the app.<br>
![app homepage](https://user-images.githubusercontent.com/94057901/150517785-230c6213-a1bc-4c16-a1e0-4be03835759a.png)

This is the navigation side bar under a hamburger button.<br>
![app nav](https://user-images.githubusercontent.com/94057901/150517842-ac9b0ed9-7356-4330-a9d6-7f97e08fca4d.png)

This is where user can imput game details and takes you to another page showing data entered.<br>
![app add game](https://user-images.githubusercontent.com/94057901/150516606-ac29c793-4aa5-4b98-a5c5-bbf428bef103.png)
![app data entered](https://user-images.githubusercontent.com/94057901/150517375-e53fbc8c-f442-4477-8ed1-964e206262ce.png)

This is where user can see the wishlist table, where you can also enter a game id to move it from wishlist to owned, it will also delete it from wishlist after the move.<br>
![app wishlist table](https://user-images.githubusercontent.com/94057901/150518127-3a7a5acb-aa53-40ac-9d5e-bf26670b5d31.png)
![app wish to own](https://user-images.githubusercontent.com/94057901/150518153-a53179c7-8544-4176-b1fa-49d595581aef.png)

This is where user can see the owned games table, where you can also enter a game id to update a game to playing.<br>
![app owned table](https://user-images.githubusercontent.com/94057901/150518446-68e115c0-2d47-4395-805b-360002426cd9.png)
![app own update play](https://user-images.githubusercontent.com/94057901/150518460-ec5c1869-2f31-4134-9c10-35fe7a65ca9c.png)

This is where user can see the currently playing table, where you can also enter a game id to move it from currently playing to completed, it will also delete it from currently playing after the move.<br>
![app play table](https://user-images.githubusercontent.com/94057901/150518750-dddc3378-98dc-4d18-bd2b-e6114e45bcc2.png)
![app play to comp](https://user-images.githubusercontent.com/94057901/150518759-74f4d3bf-ac22-42ba-a1a7-8c090188c5e2.png)

This is where the user can view games completed table.<br>
![app comp table](https://user-images.githubusercontent.com/94057901/150519314-08d952b0-a5f4-4055-b6eb-963e179ea66d.png)

### Database <a name="data"></a>
Below is an entity relationship diagram showing the structure of the database<br>
![erd](https://user-images.githubusercontent.com/94057901/150520118-eff1aeb6-d413-4155-af72-3c711c0f9393.png)

database is using mysql and flask-mysqldb.

### Testing <a name="test"></a>
Used unittest to run test on the application, which i had to research myself as tutor would not explain how we could incorperate them in our app. I wanted to run more test but did not have the time or knowledge. I wanted to incorparate pytest however we was not showing this and due to time constraints i didn't have time to research how.<br>
These test check the html reposne code for pages and data in body.
![unittest](https://user-images.githubusercontent.com/94057901/150521520-83fb5071-df67-4491-bb0e-ce66c08130d5.png)

### CI/CD Pipeline <a name="pipe"></a>
## his was our pipline breif
You are also tasked with creating a CI/CD pipeline that will automate the integration and deployment of new code.<br>
The automation server you must use is Jenkins.<br>
You have freedom to organise the pipeline however you see fit, but the pipeline must achieve the following<br>
* Run unit tests.
* Build the Docker images.
* Push the Docker images to a registry.
* Deploy to a Swarm.
## Issuses working towards this brie
* I have never used a ci/cd pipline before nor jenkins
* we was only showed how to set up jenkins and get it to retrive a github repo manually
* we was not showed how to use jenkins to run automaticlly in any way
* was not showed what kind of test we can run.
* was not showed how to use jenkins to deploy

I was able to work through some of this issues with extensive googleing and research.<br>

![jenkins build view](https://user-images.githubusercontent.com/94057901/150524444-4865fced-0254-43f7-a4dc-8c4cb1f8ea5c.png)


This is my jenkins pipleine it will detect a push to github from my local machine, then it will run my jenkisfile which does the following.
* it builds the containers using docker-compose up
* then it will run my unittest
* then it wil stop the containers using docker-compose down.





