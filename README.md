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

## Methods

Here are some of the main methods available:

- `GET`: Fetch data information from the server.

- `POST`: Send information to the server.

- `PUT`: Change information.

- `PATCH`: Change specific information.

- `DELETE`: Delete information.

## Params

The routes accept some `params`. Some of them are:

- **Route Params**: edit, delete and search a resource.

In the example below the `:id` is the param we need to know what `todo` we are talking about. To get the `id` we use the request `params` property, like this: `req.params.id`.

```javascript
app.put("/todo/:id", (req, res) => {
  const id = req.params.id;
});
```

<br>

---

**_NOTE_**

Once we define a `param` if we don't pass it to the _url_ param we get a error. So if we call just `example.com/todo` and we didn't define a basic _url_ we get an error. We need to specify the param, like this: `example.com/todo/1`.

---

<br>

- **Query Params**: used to dynamically pass information in URL.

It is commonly used to create pagination. For example:

```javascript
example.com/pagination?page=1&total=20
```

Everything after `?` is a query string.

We can access query strings with request `query` property. Check it out!

```javascript
app.put("/pagination", (req, res) => {
  const page = req.query.page;
});
```

<br>

---

**_NOTE_**

Different from the `Route Params`, the `Query Params` are optional, so something like: `examle.com/pagination` will work just fine. Then `?page=1&total=20` is not required.

---

<br>

- **Body Params**: used to insert and alter information, usually in a json format.

We can access body params with request `body` property.

```javascript
app.put("/todo", (req, res) => {
  const title = req.body.title;
});
```

Or using [destructuring](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment):

```javascript
app.put("/todo", (req, res) => {
  const { id, title } = req.body;
});
```

Assuming we have something like this:

```json
{
  "id": 1,
  "title": "New Title"
}
```

<br>

---

**_NOTE_**

Express accept several format files, so in order to it understand we are using a `json` file we need to use a `middleware`:

```javascript
app.use(express.json());
```

---
