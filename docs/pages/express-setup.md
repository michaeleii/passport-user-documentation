## Overview

This section will guide you through the process of setting up Express for our project.

[Express](http://expressjs.com/) is a Node.js web application framework that provides a robust set of features for web and mobile applications.

To learn more about Express, visit the official [Express website](http://expressjs.com/).

## Setting up Express

In this section we will be creating the Express app and create the homepage.

#### 1. Create an Express app

Put the following code in the `app.js` file:

```javascript
const express = require("express");
const app = express();

app.set("view engine", "ejs");
app.use(express.urlencoded({ extended: false }));
app.use(express.static("public"));

app.get("/", (req, res) => {
	res.render("index");
});

app.get("/login", (req, res) => {
	res.render("login");
});

app.listen(3000, () => {
	console.log("Login App listening on port 3000!");
});
```

This will create a basic Express app that listens on port 3000 and renders the `index.ejs` file when the `/` route is requested. It also renders the `login.ejs` file, which will be the login page when the `/login` route is requested.

The `login.ejs` file will created later in the tutorial.

#### 2. Edit the `index.ejs` file

```html
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8" />
		<meta name="viewport" content="width=device-width, initial-scale=1.0" />
		<link rel="stylesheet" href="/style.css" />
		<title>Login</title>
	</head>
	<body>
		<h1>Not Logged In</h1>
		<a href="/login">Login</a>
	</body>
</html>
```

This will create a simple home page that will be rendered when the `/` route is requested. There is also a link to the `/login` route. Before we create the `login.ejs` file, let's create a sample database with users to test our login form.

## Conclusion

In this section we set up Express for our project. We created a basic Express app that listens on port 3000 and renders the `index.ejs` file when the `/` route is requested. It also renders the `login.ejs` file when the `/login` route is requested.

In the next section, we will create a sample database with users to test our login form.
