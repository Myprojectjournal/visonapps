#### **\*\*BACKEND TOOLS:\*\***





**res.send(), res.json(), or res.render()**



1. ## **EJS**



###### **<!DOCTYPE html>**

###### **<html>**

###### 

###### **<head>**

######   **<title>Taco Recipes</title>**

######   **<link rel="stylesheet" type="text/css" href="/styles/main.css">**

###### **</head>**

###### 

###### **<body>**

######   **<h1>Taco Town 🌮</h1>**

###### 

###### 

######   **<form action="/recipe" method="POST" class="buttons**

######   **">**

######     **<button type="submit" value="chicken" name="choice">🍗</button>**

######     **<button type="submit" value="beef" name="choice">🥩</button>**

######     **<button type="submit" value="fish" name="choice">🐟</button>**

######   **</form>**

######   **<div id="recipeContainer" class="hidden">**

######     **<%if (locals.recipe) {%>**

###### 

######       **<h2 id="recipeTitle">**

######         **<%= recipe.name %>**

######       **</h2>**

###### 

######       **<h3>Ingredients:</h3>**

######       **<ul id="ingredientsList">**

######         **<li>**

######           **<%= recipe.ingredients.protein.name %>, <%= recipe.ingredients.protein.preparation %>**

######         **</li>**

######         **<li>**

######           **<%= recipe.ingredients.salsa.name %>**

###### 

######         **</li>**

######         **<% recipe.ingredients.toppings.forEach(topping=> { %>**

######           **<li>**

######             **<%= topping.quantity %> of <%= topping.name %>**

######           **</li>**

######           **<% }) %>**

######       **</ul>**

###### 

######       **<%} else {%>**

######         **<h2>Pick your favourite taco ingredient 👆</h2>**

######         **<%}%>**

######   **</div>**

###### **</body>**

###### 

###### **</html>**



#### **1. ###### \*\*SENDING files:\*\***



###### **\* \*\*FOLDER\*\***

###### **\***

###### **\*\*import express from "express";\*\***

###### 

###### **\*\*import bodyParser from "body-parser";\*\***

###### 

###### **\*\*import path, { dirname } from "path";\*\***

###### 

###### **\*\*import { fileURLToPath } from "url";\*\***

###### 

###### **const \_\_filename = fileURLToPath(import.meta.url);\*\***

###### 

###### **const =  \\\_\\\_dirname = dirname(fileUrlToPath);**

###### 

###### 

###### **\*\*const app = express();\*\***

###### 

###### **\*\*const port = 5000;\*\***

###### 

###### 

###### **\*\*app.use (bodyParser.urlencoded({ extended: true }));\*\***

###### 

###### 

###### **\*\*app.use(express.static(path.join(\\\_\\\_dirname, 'public')));\*\***

###### 

###### 

###### **\*\*app.get ("/", (req, res) => {\*\***

###### 

###### **\*\*res.sendFile(path.join(\\\_\\\_dirname, 'public', 'index.html'));\*\***

###### 

###### **\*\*});\*\***

###### 

###### **\*\*app.listen(port, () =>{\*\***

**console.log(${port})**



## **\*\*})\*\*\*\***









## **1. ######  \*\*Middlewares: body-Parser()/Res.send\*\***

###### **1.**

###### **\*\*import express from 'express';\*\***

###### 

###### **\*\*import bodyParser from 'body-parser';\*\***

###### 

###### **\*\*import path, { dirname} from 'path';\*\***

###### 

###### **\*\*import { fileURLToPath } from 'url';\*\***

###### 

###### **\*\*const \\\_\\\_dirname =  dirname(fileURLToPath(import.meta.url));\*\***

###### 

###### **\*\*const app = express();\*\***

###### 

###### **\*\*const port = 5000;\*\***

###### 

###### **\*\*app.use(bodyParser.urlencoded({ extended: true }));\*\***

###### 

###### **\*\*app.use(express.static(path.join(\\\_\\\_dirname, 'public')));\*\***

###### 

###### **\*\*app.get('/', (req, res) => {\*\***

###### 

** \*res.sendFile(path.join(dirname, 'public', 'index.html'));**



**---**

###### 

###### **\*\*})\*\***

###### 

###### 

###### **\*\*app.post('/submit', (req, res) => {\*\***

###### 

** \*const { username, password } = req.body;\*console.log(req.body)\*res.send(`username: ${username}, password: ${password}`)**





**---**

###### **\*\*});\*\*\*\***

###### 

###### **\*\*app.listen(port, () => {\*\***

**\*console.log(`Server is running on http://localhost:${port}`);**



**---**

###### **\*\*})\*\*\*\***











1. ## **API: Application Programming Interface**
1. 
**###### import express from "express";**

###### **import bodyParser from "body-parser";**

###### 

###### **const app = express();**

###### **const port = 5000;**

###### 

###### **const recipeJSON =**

######   **'\[{"id": "0001","type": "taco","name": "Chicken Taco","price": 2.99,"ingredients": {"protein": {"name": "Chicken","preparation": "Grilled"},  "salsa": {"name": "Tomato Salsa","spiciness": "Medium"},  "toppings": \[{"name": "Lettuce",  "quantity": "1 cup",  "ingredients": \["Iceberg Lettuce"]  },      {"name": "Cheese",  "quantity": "1/2 cup",  "ingredients": \["Cheddar Cheese", "Monterey Jack Cheese"]  },      {"name": "Guacamole",  "quantity": "2 tablespoons",  "ingredients": \["Avocado", "Lime Juice", "Salt", "Onion", "Cilantro"]  },      {"name": "Sour Cream",  "quantity": "2 tablespoons",  "ingredients": \["Sour Cream"]  }      ]    }  },{"id": "0002","type": "taco","name": "Beef Taco","price": 3.49,"ingredients": {"protein": {"name": "Beef","preparation": "Seasoned and Grilled"},  "salsa": {"name": "Salsa Verde","spiciness": "Hot"},  "toppings": \[{"name": "Onions",  "quantity": "1/4 cup",  "ingredients": \["White Onion", "Red Onion"]  },      {"name": "Cilantro",  "quantity": "2 tablespoons",  "ingredients": \["Fresh Cilantro"]  },      {"name": "Queso Fresco",  "quantity": "1/4 cup",  "ingredients": \["Queso Fresco"]  }      ]    }  },{"id": "0003","type": "taco","name": "Fish Taco","price": 4.99,"ingredients": {"protein": {"name": "Fish","preparation": "Battered and Fried"},  "salsa": {"name": "Chipotle Mayo","spiciness": "Mild"},  "toppings": \[{"name": "Cabbage Slaw",  "quantity": "1 cup",  "ingredients": \[    "Shredded Cabbage",    "Carrot",    "Mayonnaise",    "Lime Juice",    "Salt"          ]  },      {"name": "Pico de Gallo",  "quantity": "1/2 cup",  "ingredients": \["Tomato", "Onion", "Cilantro", "Lime Juice", "Salt"]  },      {"name": "Lime Crema",  "quantity": "2 tablespoons",  "ingredients": \["Sour Cream", "Lime Juice", "Salt"]  }      ]    }  }]';**

###### 

###### **app.use(express.static("public"));**

###### **app.use(bodyParser.urlencoded({ extended: true }));**

###### 

###### **let data;**

###### 

###### **app.get("/", (req, res) => {**

######   **res.render("solution.ejs", { recipe: data });**

###### **});**

###### 

###### **app.post("/recipe", (req, res) => {**

######   **switch (req.body.choice) {**

######     **case "chicken":**

######       **data = JSON.parse(recipeJSON)\[0];**

######       **break;**

######     **case "beef":**

######       **data = JSON.parse(recipeJSON)\[1];**

######       **break;**

######     **case "fish":**

######       **data = JSON.parse(recipeJSON)\[2];**

######       **break;**

######     **default:**

######       **break;**

######   **}**

######   **res.redirect("/");**

###### **});**

###### 

###### **app.listen(port, () => {**

######   **console.log(`Server running on port: ${port}`);**

###### **});**







1. ## **EJS: Embedded JavaScript**
2. 
3. ###### 
4. 
4. 
**\###### app.set(view engine, ejs)**

###### **app.set("views", "ejs")**

###### **app.get("/", (req, res) => {**

###### **res.render("solution.ejs", { recipe: data }**

###### 

###### 

###### **<form action="/recipe" method="POST" class="buttons**

###### **">**

** **  

**</div>**

**</body>**



**</html>**















1. ## **RES.Render Rules**

###### 

###### **📝 res.render() — RULES SUMMARY**

###### 

###### **res.render() is used to send HTML pages, not raw data.**

###### 

###### **First argument must be a template file, usually:**

###### 

###### **.ejs**

###### 

###### **NOT .js**

###### 

###### **Template files must be inside the views folder.**

###### 

###### **Second argument must always be an object {}**

###### **This object carries data to the template.**

###### 

###### **Keys in the object become variables in EJS.**

###### 

###### **res.render("page.ejs", { title: "Home" });**

###### 

###### **<%= title %>**

###### 

###### 

###### **You can pass strings, numbers, objects, and arrays inside the object.**

###### 

###### **res.render() ends the response — you can only send ONE response per request.**

###### 

###### **You must set a view engine:**

###### 

###### **app.set("view engine", "ejs");**

###### 

###### 

###### **res.render() cannot render .js files — .js is for logic, not views.**

###### 

###### **If you don’t need HTML, don’t use res.render():**

###### 

###### **Use res.send() for text**

###### 

###### **Use res.json() for APIs**

###### 

###### **🧠 Master rule (1 line)**

###### 

###### **res.render(view, dataObject) → HTML + data**





1. # **Axios Rules**
2. 
3. ###### 
4. 
4. 
**\###### ##### 📝 AXIOS — RULES SUMMARY**

###### 

###### **Axios is used to make HTTP requests**

###### **(talk to APIs, servers, databases).**

###### 

###### **Axios always returns a Promise**

###### **→ use await or .then().**

###### 

###### **Use async / await when calling Axios (recommended):**

###### 

###### **const response = await axios.get(url);**

###### 

###### 

###### **API data is always inside response.data**

###### **NOT response directly.**

###### 

###### **Use the correct HTTP method:**

###### 

###### **axios.get() → read data**

###### 

###### **axios.post() → send data**

###### 

###### **axios.put() → replace data**

###### 

###### **axios.patch() → update part of data**

###### 

###### **axios.delete() → remove data**

###### 

###### **Use try...catch for Axios calls**

###### **Because network/API requests can fail.**

###### 

###### **Axios requests are asynchronous**

###### **Code below await axios(...) waits until the request finishes.**

###### 

###### **Axios can send query parameters:**

###### 

###### **axios.get("/api", { params: { type: "education" } });**

###### 

###### 

###### **Axios can send request body data (POST / PUT / PATCH):**

###### 

###### **axios.post("/api", {**

###### **name: "John",**

###### **age: 20**

###### **});**

###### 

###### 

###### **Axios automatically parses JSON**

###### **No need for JSON.parse().**

###### 

###### **Axios can be used on backend and frontend:**

###### 

###### **Backend → Node / Express**

###### 

###### **Frontend → Browser / React**

###### 

###### **Always handle the data before sending it to the client**

###### **(filter, pick one, loop, randomize, etc.).**

###### 

###### **🧠 Master rule (1 line)**

###### 

###### **Axios gets data → data is in response.data → you decide what to do with it**

###### 









1. **Axios Code
   import express from "express";**
   ---
2. ###### **import bodyParser from "body-parser";**
3. ###### **import axios from "axios";**
4. ###### 
5. ###### **const app = express();**
6. ###### **const port = 3000;**
7. ###### 
8. ###### **app.use(express.static("public"));**
9. ###### **app.use(bodyParser.urlencoded({ extended: true }));**
10. ###### 
11. ###### **app.get("/", async (req, res) => {**
12. ###### **try {**
13. ###### **\*\*const response = await axios.get("https://bored-api.appbrewery.com/random");\*\***
14. ###### **\*\*const result = response.data;\*\***
15. ###### **\*\*console.log(result);\*\***
16. ###### **\*\*res.render("solution.ejs", { data: result });\*\***
17. ###### **} catch (error) {**
18. ###### **\*\*console.error("Failed to make request:", error.message);\*\***
19. ###### **\*\*res.render("solution.ejs", {\*\***
20. ###### **\*\*error: error.message,\*\***
21. ###### **\*\*});\*\***
22. ###### **}**
23. ###### **});**
24. ###### 
25. ###### **app.post("/", async (req, res) => {**
26. ###### **try {**
27. ###### **\*\*console.log(req.body);\*\***
28. ###### **\*\*const type = req.body.type;\*\***
29. ###### **\*\*const participants = req.body.participants;\*\***
30. ###### **\*\*const response = await axios.get(\*\***
31. ###### **\*\*`https://bored-api.appbrewery.com/filter?type=${type}\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\&participants=${participants}`\*\***
32. ###### **\*\*);\*\***
33. ###### **\*\*const result = response.data;\*\***
34. ###### **\*\*console.log(result);\*\***
35. ###### **\*\*res.render("solution.ejs", {\*\***
36. ###### **\*\*data: result\\\[Math.floor(Math.random() \\\* result.length)],\*\***
37. ###### **\*\*});\*\***
38. ###### **} catch (error) {**
39. ###### **\*\*console.error("Failed to make request:", error.message);\*\***
40. ###### **\*\*res.render("solution.ejs", {\*\***
41. ###### **\*\*error: "No activities that match your criteria.",\*\***
42. ###### **\*\*});\*\***
43. ###### **}**
44. ###### **});**
45. ###### 
46. ###### **app.listen(port, () => {**
47. ###### **console.log(`Server running on port: ${port}`);**
48. ###### **});**



**127c3627-73ca-4b12-8d99-b171cd8f74e4**

**2584fc63-5f4e-4cb8-9ce3-93759bdef675**





1. # **Authentication:**
2. ##### **Getting data from another API with axious**
3. 
3. 
**\###### import express from "express";**

###### **import axios from "axios";**

###### 

###### **const app = express();**

###### **const port = 3000;**

###### **const API\_URL = "https://secrets-api.appbrewery.com";**

###### 

###### **// TODO: Replace the values below with your own before running this file.**

###### **const yourUsername = "yeshuah";**

###### **const yourPassword = "Emmanuel1998$#";**

###### **const yourAPIKey = "387e92e0-a4a1-47e9-bae0-a0e775bb88a1";**

###### **const yourBearerToken = "31f9bf16-e11c-444a-8faa-f671eb5d69d3";**

###### 

###### **app.get("/", (req, res) => {**

###### **res.render("index.ejs", { content: "API Response." });**

###### **});**

###### 

###### **app.get("/noAuth", async (req, res) => {**

###### **try {**

###### **const result = await axios.get(API\_URL + "/random");**

###### **res.render("index.ejs", { content: JSON.stringify(result.data) });**

###### **} catch (error) {**

###### **res.status(404).send(error.message);**

###### **}**

###### **});**

###### 

###### **app.get("/basicAuth", async (req, res) => {**

###### **try {**

###### **const result = await axios.get(API\_URL + "/all?page=2", {**

###### **auth: {**

###### **username: yourUsername,**

###### **password: yourPassword,**

###### **},**

###### **});**

###### **res.render("index.ejs", { content: JSON.stringify(result.data) });**

###### **} catch (error) {**

###### **res.status(404).send(error.message);**

###### **}**

###### **});**

###### 

###### **app.get("/apiKey", async (req, res) => {**

###### **try {**

###### **const result = await axios.get(API\_URL + "/filter", {**

###### **params: {**

###### **score: 5,**

###### **apiKey: yourAPIKey,**

###### **},**

###### **});**

###### **res.render("index.ejs", { content: JSON.stringify(result.data) });**

###### **} catch (error) {**

###### **res.status(404).send(error.message);**

###### **}**

###### **});**

###### 

###### **const config = {**

###### **headers: { Authorization: `Bearer ${yourBearerToken}` },**

###### **};**

###### 

###### **app.get("/bearerToken", async (req, res) => {**

###### **try {**

###### **const result = await axios.get(API\_URL + "/secrets/2", config);**

###### **res.render("index.ejs", { content: JSON.stringify(result.data) });**

###### **} catch (error) {**

###### **res.status(404).send(error.message);**

###### **}**

###### **});**

###### 

###### **app.listen(port, () => {**

###### **console.log(`Server is running on port ${port}`);**

###### **});**





###### **app.get("/solution", async (req, res) => {**

###### **try {**

###### **const data = await getData()**

###### **res.render("solution.ejs", { data })**

###### **} catch (error) {**

###### **res.status(404).send(error.message)**

###### **}**

###### **})**









1. ## **REST API: Representational State Transfer – Application Programming Interface**
2. 
2. 
**\###### import express from "express";**

###### **import axios from "axios";**

###### **import bodyParser from "body-parser";**

###### 

###### **const app = express();**

###### **const port = 3000;**

###### **const API\_URL = "https://secrets-api.appbrewery.com";**

###### 

###### **//Add your own bearer token from the previous lesson.**

###### **const yourBearerToken = "08f3026d-9c6c-4d88-a3b2-c579dc106247";**

###### **const config = {**

###### **headers: { Authorization: `Bearer ${yourBearerToken}` },**

###### **};**

###### 

###### **app.use(bodyParser.urlencoded({ extended: true }));**

###### 

###### **app.get("/", (req, res) => {**

###### **res.render("index.ejs", { content: "Waiting for data..." });**

###### **});**

###### 

###### **app.post("/get-secret", async (req, res) => {**

###### **const searchId = req.body.id;**

###### **try {**

###### **const result = await axios.get(API\_URL + "/secrets/" + searchId, config);**

###### **res.render("index.ejs", { content: JSON.stringify(result.data) });**

###### **} catch (error) {**

###### **res.render("index.ejs", { content: JSON.stringify(error.response.data) });**

###### **}**

###### **});**

###### 

###### **app.post("/post-secret", async (req, res) => {**

###### **try {**

###### **const result = await axios.post(API\_URL + "/secrets", req.body, config);**

###### **res.render("index.ejs", { content: JSON.stringify(result.data) });**

###### **} catch (error) {**

###### **res.render("index.ejs", { content: JSON.stringify(error.response.data) });**

###### **}**

###### **});**

###### 

###### **app.post("/put-secret", async (req, res) => {**

###### **const searchId = req.body.id;**

###### **try {**

###### **const result = await axios.put(**

###### **API\_URL + "/secrets/" + searchId,**

###### **req.body,**

###### **config**

###### **);**

###### **res.render("index.ejs", { content: JSON.stringify(result.data) });**

###### **} catch (error) {**

###### **res.render("index.ejs", { content: JSON.stringify(error.response.data) });**

###### **}**

###### **});**

###### 

###### **app.post("/patch-secret", async (req, res) => {**

###### **const searchId = req.body.id;**

###### **try {**

###### **const result = await axios.patch(**

###### **API\_URL + "/secrets/" + searchId,**

###### **req.body,**

###### **config**

###### **);**

###### **res.render("index.ejs", { content: JSON.stringify(result.data) });**

###### **} catch (error) {**

###### **res.render("index.ejs", { content: JSON.stringify(error.response.data) });**

###### **}**

###### **});**

###### 

###### **app.post("/delete-secret", async (req, res) => {**

###### **const searchId = req.body.id;**

###### **try {**

###### **const result = await axios.delete(API\_URL + "/secrets/" + searchId, config);**

###### **res.render("index.ejs", { content: JSON.stringify(result.data) });**

###### **} catch (error) {**

###### **res.render("index.ejs", { content: JSON.stringify(error.response.data) });**

###### **}**

###### **});**

###### 

###### **app.listen(port, () => {**

###### **console.log(`Server is running on port ${port}`);**

###### **});**

###### 

###### 

###### 

###### 

###### 

###### 

###### 

###### **---**

