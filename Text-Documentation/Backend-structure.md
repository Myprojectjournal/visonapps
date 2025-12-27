**\*\*BACKEND TOOLS:\*\***



**1. ###### \*\*Rendering files:\*\***



**\* \*\*FOLDER\*\***

**\***

**\*\*import express from "express";\*\***



**\*\*import bodyParser from "body-parser";\*\***



**\*\*import path, { dirname } from "path";\*\***



**\*\*import { fileURLToPath } from "url";\*\***



**const \_\_filename = fileURLToPath(import.meta.url);\*\***



**const =  \\\_\\\_dirname = dirname(fileUrlToPath);**





**\*\*const app = express();\*\***



**\*\*const port = 5000;\*\***





**\*\*app.use (bodyParser.urlencoded({ extended: true }));\*\***





**\*\*app.use(express.static(path.join(\\\_\\\_dirname, 'public')));\*\***





**\*\*app.get ("/", (req, res) => {\*\***



**\*\*res.sendFile(path.join(\\\_\\\_dirname, 'public', 'index.html'));\*\***



**\*\*});\*\***



**\*\*app.listen(port, () =>{\*\***



    **\*\*\\\*\\\*console.log(`Server is running on http://localhost:${port}`);\\\*\\\*\*\***






**\*\*})\*\***









**1. ######  \*\*Middlewares: body-Parser()/Res.send\*\***

**1.**

**\*\*import express from 'express';\*\***



**\*\*import bodyParser from 'body-parser';\*\***



**\*\*import path, { dirname} from 'path';\*\***



**\*\*import { fileURLToPath } from 'url';\*\***



**\*\*const \\\_\\\_dirname =  dirname(fileURLToPath(import.meta.url));\*\***



**\*\*const app = express();\*\***



**\*\*const port = 5000;\*\***



**\*\*app.use(bodyParser.urlencoded({ extended: true }));\*\***



**\*\*app.use(express.static(path.join(\\\_\\\_dirname, 'public')));\*\***



**\*\*app.get('/', (req, res) => {\*\***



    **\*\*\\\*\\\*res.sendFile(path.join(dirname, 'public', 'index.html'));\\\*\\\*\*\***






**\*\*})\*\***





**\*\*app.post('/submit', (req, res) => {\*\***



    **\*\*\\\*\\\*const { username, password } = req.body;\\\*\\\*\*\*



    \*\*\\\*\\\*console.log(req.body);\\\*\\\*\*\*



    \*\*\\\*\\\*res.send(`username: ${username}, password: ${password}`)\\\*\\\*\*\***






**\*\*});\*\***





**\*\*app.listen(port, () => {\*\***



    **\*\*\\\*\\\*console.log(`Server is running on http://localhost:${port}`);\\\*\\\*\*\***






**\*\*})\*\***











1. ###### **API:**
2. ###### **JSON**
3. 
3. 
** {**

    **\*\*"id": "0001",\*\*

    \*\*"type": "taco",\*\*

    \*\*"name": "Chicken Taco",\*\*

    \*\*"price": 2.99,\*\*

    \*\*"ingredients": {\*\*

      \*\*"protein": {\*\*

        \*\*"name": "Chicken",\*\*

        \*\*"preparation": "Grilled"\*\***






**const recipeJSON =**

**'\[{"id": "0001","type": "taco","name": "Chicken Taco","price": 2.99,"ingredients": {"protein": {"name"**



**app.get("/", (req, res) => {**

**res.render("solution.ejs", { recipe: data });**

**});**



**app.post("/recipe", (req, res) => {**

**switch (req.body.choice) {**

    **\*\*case "chicken":\*\*

      \*\*data = JSON.parse(recipeJSON)\\\[0];\*\*

      \*\*break;\*\*

    \*\*case "beef":\*\*

      \*\*data = JSON.parse(recipeJSON)\\\[1];\*\*

      \*\*break;\*\*

    \*\*case "fish":\*\*

      \*\*data = JSON.parse(recipeJSON)\\\[2];\*\*

      \*\*break;\*\*

    \*\*default:\*\*

      \*\*break;\*\***


**}**

**res.redirect("/");**

**});**







###### 

1. ###### **EJS**
2. 
2. 
**app.set(view engine, ejs)**

**app.set("views", "ejs")**

**app.get("/", (req, res) => {**

**res.render("solution.ejs", { recipe: data }**





**<form action="/recipe" method="POST" class="buttons**

**">**

    **\*\*<button type="submit" value="chicken" name="choice">🍗</button>\*\*

    \*\*<button type="submit" value="beef" name="choice">🥩</button>\*\*

    \*\*<button type="submit" value="fish" name="choice">🐟</button>\*\***


**</form>**

**<div id="recipeContainer" class="hidden">**

    **\*\*<%if (locals.recipe) {%>\*\*



      \*\*<h2 id="recipeTitle">\*\*

        \*\*<%= recipe.name %>\*\*

      \*\*</h2>\*\*



      \*\*<h3>Ingredients:</h3>\*\*

      \*\*<ul id="ingredientsList">\*\*

        \*\*<li>\*\*

          \*\*<%= recipe.ingredients.protein.name %>, <%= recipe.ingredients.protein.preparation %>\*\*

        \*\*</li>\*\*

        \*\*<li>\*\*

          \*\*<%= recipe.ingredients.salsa.name %>\*\*



        \*\*</li>\*\*

        \*\*<% recipe.ingredients.toppings.forEach(topping=> { %>\*\*

          \*\*<li>\*\*

            \*\*<%= topping.quantity %> of <%= topping.name %>\*\*

          \*\*</li>\*\*

          \*\*<% }) %>\*\*

      \*\*</ul>\*\*



      \*\*<%} else {%>\*\*

        \*\*<h2>Pick your favourite taco ingredient 👆</h2>\*\*

        \*\*<%}%>\*\***


**</div>**

**</body>**



**</html>**





1. ###### **Axios**



