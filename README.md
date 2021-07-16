# NodeJS ToDo App

This is a very basic app created with `nodejs`.

To make things simple I used this great framework called [Express](https://github.com/expressjs/expressjs.com).

`Express` is a framework that sits on top on `Node.js` to simplify its API and remove some of its complexity and add some nice features like routing and middleware.

**Routing** is a very important feature offered by `express`. According to its documentation:

> **Routing** refers to determining how an application responds to a client request to a particular endpoint, which is a URI (or path) and a specific HTTP request method (GET, POST, and so on).

Each route can have one or more handler functions, which are executed when the route is matched.

Route definition takes the following structure:

```
app.METHOD(PATH, HANDLER)
```

Where:

- _**app**_ is an instance of express.
- _**METHOD**_ is an `HTTP` request method, in lowercase.
- _**PATH**_ is a path on the server.
- _**HANDLER**_ is the function executed when the route is matched.

Here are some of the main methods available:

- `GET`: Fetch data information from the server.

- `POST`: Send information to the server.

- `PUT`: Change information.

- `PATCH`: Change specific information.

- `DELETE`: Delete information.
