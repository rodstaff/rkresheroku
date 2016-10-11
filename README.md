# redux-react-heroku

"Redux-React-Heroku" is coded in ReactJS + React-Router and using the Redux framework.  It is a playful presentation of some famous people and the Mutant Ninja Turtles!  The app's simplicity betrays the complexity behind it.  It uses multiple sources and it serves as a personal template for bigger and more complex apps.  There were four challenges I faced creating this app:  

(1) It is on the "bleeding edge" of technology and can be overwhelming;<br/>
(2) Online authors do not necessarily make sure your dev environment is working or assume it is already working;<br/>
(3) Different authors have different coding styles and preferences and explain only snippets of their total code.  Their code repositories may also be outdated.<br/>
(4) Deployment to Heroku is a pain!!!<br/>

Regarding to (4) above:  As of this writing, there is not a clear documentation on how to deploy React-Redux apps to Heroku and most of them look quite complex and difficult to follow.  I used a very simple option and that is to use the bundle.js file and deploy that to Heroku using Node.js/Express as the background server.  

The server.js file is below

```
var express = require('express');
var app = express();
var port = process.env.PORT || 8080

app.use(express.static(__dirname + '/'));

app.listen(port);
console.log("server running on port " + port);
```

The index.html file looks like this

```
<!DOCTYPE html>
<html>
<head>
  <title>React2Heroku</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <div id="root"></div>
  <link href="style.css" rel="stylesheet">
  <script type="text/javascript" src="bundle.js"></script>
</body>
</html>
```
The bundle.js file was bundled by webpack from [redux-react-routes](https://github.com/rodstaff/redux-react-routes).

To run this app locally using your terminal
```
$node server.js
```


