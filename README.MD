# QAcinema Backend Template

This repository acts as a basic sample to represent the backend of the QAcinema project.

The current functionality includes being able to **POST** to a `movies` collection in the `QAcinemaBE` database and also **GET** the list of movies in the collection.

## Getting started

- Fork this repository
- Clone it down using: `git clone [URL of the foreked repository]`
- Open the cloned folder in VS Code
- Open an integrated terminal and run: `npm install` -> to get all the dependencies
- You may need to also run: `npm i -g nodemon` -> to be able to run the app with nodemon which works similar to devtools in Spring
- Then run: `npm start` -> to start the app
- Then check the code works with postman

### How to check the code works with postman

#### POST

- Select **POST**
- Paste this in the url section: `http://localhost:5000/movies/createMovie`
- Click on **Body** and then choose **raw** and then **JSON**
- Sample body you can use:
  ```
  {
      "title": "Minions",
      "description": "Animation",
      "runtime": 120
  }
  ```
- Click **SEND** and observe the response

#### GET

- Select **GET**
- Paste this in the url section: `http://localhost:5000/movies/readMovies`
- Click **SEND** and observe the response

## Adding more collections(tables)

The `models` folder should consist of javascript files for the schema of each collection for your database.

You can modify the schema in the existing _movies.js_ file and add/remove fields from the movies collection.

Follow the steps below to add more collections, such as for listings, bookings, etc:

- In the _models_ folder, create another _.js_ file with the name of your collection.
- Follow the same format of the _movies.js_ to create another schema but with the appropriate field names for that collection.
- You can create as many collections as you need.

## Adding more routes

The `routes` folder should consist of javascript files which would handle the rquests made to each collection.

You can modify the code in the existing _moviesRoute.js_ file and add/remove the current completed requests. You would need to do the update and delete requests for this route as only create and read have been done.

Follow the steps below to add more routes, such as for listings, bookings, etc:

- In the _routes_ folder, create another _.js_ file with the name of the collection you want to route to, **for example: the models/movies.js is linked to the routes/moviesRoute.js**.
- Follow the same format of the _moviesRoute.js_ to create another all the other route files.
- Create the same amount of routes to correspond with the number of models you have and make sure each route has full CRUD (create, read, update and delete requests).

## Update the index.js

The following lines would need to be replecated in the _index.js_ file for each new route added to the _routes_ folder.

```
const movieRouter = require("./routes/moviesRoute");

myapp.use("/movies", movieRouter);
```
