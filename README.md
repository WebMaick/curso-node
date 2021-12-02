[Manual del curso de Node BLUUWEB](https://bluuweb.github.io/node/)

# Nodemon

instalar en modo global con: npm install -g nodemon

# hbs

instalar npm i hbs => nos ayudara a convertir uestros arhivos en dinamicos y usaremos render

### modo de uso

app.set('view engine', 'hbs');

# Express

### Instalacion

npm install express

### Descripcion

```js
const express = require("express");
var hbs = require("hbs");

const app = express();
const port = 4000;

app.set("view engine", "hbs");

app.use(express.static(__dirname + "/public"));
hbs.registerPartials(__dirname + "/views/template", function (err) {});

app.get("/", (req, res) => {
	res.render("index", {
		titulo: "Mi primera prueba con node",
		tituloBody: "Aprendiendo con Node",
	});
});

app.get("/servicios", (req, res) => {
	res.render("servicios", {
		titulo: "Pagina de servicios",
		tituloBody: "Aprendiendo con Node",
	});
});

app.get("/*", (req, res) => {
	res.render("404", {
		titulo: "Error 404 conacte con WebMaick",
		tituloBody: "Aprendiendo con Node",
	});
});

app.listen(port, () => {
	console.log(`Example app listening at http://localhost:${port}`);
});
```
