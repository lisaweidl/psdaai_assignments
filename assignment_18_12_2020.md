# Assignment 18.12.2020

On Friday 11.12., we have looked at the basic functionality of an API and we should have a basic understanding of the corresponding technologies (HTTP, JSON).

## Part 1

Please watch these 3 videos carefully and also do the exercises using the [Postman](https://www.postman.com/) application.

- [Intro to APIs Part 1: What is an API?](https://www.youtube.com/watch?v=iFMLyMgCUTs)
- [Intro to APIs Part 2: How to use an API?](https://www.youtube.com/watch?v=jCadnlO9xSQ)
- [Intro to APIs Part 3: HTTP protocol explained](https://www.youtube.com/watch?v=FAnuh0_BU4c&t=34s)

You should understand the following concepts:
- What is the difference between an API and a regular web site?
- What is a protocol and what is HTTP?
- Who sends a HTTP request? Who sends a HTTP response?
- What is an HTTP error code? What is the error code for "no error"?
- What is the base URL of an API?
- What is an API endpoint?
- What is an HTTP method?
- What is the difference between the HTTP methods GET, POST, PUT, and DELETE?
- Why does a HTTP message consist of a header and a body?


## Part 2

### Clone the repository https://github.com/martingasser/todo_api.git to your machine

```
git clone https://github.com/martingasser/todo_api.git
```

This repository implements a very simple API for our Todo application.

It consists of two endpoints:

```
- /todos
- /todos/{id}
```

Todo data is in JSON format. A typical todo item would look like this:

```json
{
  "text": "Go shopping",
  "date": "15-12-2020",
  "done": false,
  "id": 3244529534
}
```

`GET /todos` returns a list of all todos in the database.

`POST /todos` creates a new todo item in the database.

The message body must contain the todo data. You only have to specify `text`, `date`, `done`. The field `id` is generated automatically by the server.

`GET /todos/{id}` returns a specific todo item from the database. Replace `{id}` with the id of the todo item.

`PUT /todos/{id}` updates a specific todo item. The message body should contain a JSON document containing the fields that should be updated.

`DELETE /todos/{id}` deletes a specific todo item from the database.

All requests return a status code `200` if executed successfully. Otherwise an error code and a corresponding error message will be returned.

### Start the API server

Change the current directory (`cd`) in your commandline to the repository you just cloned from Github.

Then type

ˋˋˋ
npm install
ˋˋˋ

to install the required additional libraries and

```
npm run serve
```

to start the server.

You will see

```
Server running on port 8081.
```

Opening [http://localhost:8081](http://localhost:8081) in a browser should say

```json
{
  "message": "Welcome to Todo API"
}
```

## Part 3

From part 1 of this assignment, you should know how to use Postman.

As we know from part 2, the base URL of the API is `http://localhost:8081/`, so the full endpoints would be

- `http://localhost:8081/todos`
- `http://localhost:8081/todos/{id}`

Using the Postman application, try to
- create todo items in the database
- retrieve the list of all todos
- retrieve a single todo item
- update a todo item (e.g., change its date, or set the `done` field to true)
- delete a todo item

# Consultation hours

I'm offering consultation hours next Thursday (17.12.2020) from 17:00-19:00.

On Friday we will connect the existing todo list application to the API server. A proper understanding of the things we did so far will greatly 
benefit your learning progress. So if you think that you could need more support/explanations, please let me know and drop in on Thursday.
