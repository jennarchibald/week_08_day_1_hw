# Homework: Full Stack Games Hub App

### Learning Objectives

- Understand the relationship between client, server and database
- Be able to navigate a codebase that you haven't written

## Brief

Your boss has asked to you look over the codebase of a full-stack JavaScript application. The front-end is written in JavaScript using no frameworks, the back-end uses an Express server and a MongoDB database. Your task is to make yourself familiar with the codebase.

The application includes a README.md with instructions on running the application.

![Overview of the tech stack and tooling with commands](images/tech_stack_with_commands.png)

*Overview of the tech stack and tooling with commands*

## MVP

### Task

Draw a diagram showing the dataflow through the application starting with a form submission, ending with the re-rendering of the page. This will involve a multi-direction data-flow with the client posting data to the server and the server sending data back to the client with the response. Detail the client, server and database in the diagram and include the names of the files involved in the process.

### Questions

1. What is responsible for defining the routes of the `games` resource?

create_router.js defines the routes of the games resource using the data and path supplied in the server.js file.

2. What are the the responsibilities of server.js?


server.js connects to the db using MongoClient, defines the routes of the 'games' resource using create_router and starts listening for requests to the server.

3. What are the responsibilities of the `gamesRouter`?

the games router listens on the RESTful routes on the /api/games and makes post and get requests to the db.

4. What process does the the client (front-end) use to communicate with the server?

games.js uses the request helper to make post get and delete requests to the server.

5. What optional second argument does the `fetch` method take? And what is it used for in this application? Hint: See [Using Fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch) on the MDN docs

'an init object that allows you to control a number of different settings'

this is used to specify the method of the request (get/post/delete) and the type of data e.g. json

6. Which of the games API routes does the front-end application consume (i.e. make requests to)?

GET 'http://localhost:3000/api/games'
POST 'http://localhost:3000/api/games'
DELETE 'http://localhost:3000/api/games/:id'

7. What are we using the [MongoDB Driver](http://mongodb.github.io/node-mongodb-native/) for?

to connect to the DB within the server.js file and perform CRUD actions

## Extension

Why do we need to use [`ObjectId`](https://mongodb.github.io/node-mongodb-native/api-bson-generated/objectid.html) from the MongoDB driver?

we need ObjectID to use the ObjectID function to create objectid objects in order to use deleteOne and be sure we are deleting the correct document from the collection by identifying it by its unique id.
