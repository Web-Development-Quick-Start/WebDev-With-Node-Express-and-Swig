## Templating

Before we were creating static pages, and you can do that with node and express,
but the real power starts to show once you leverage templates and create
dynamic content for your user (i.e. custom welcome page, their favorite links, etc)

We'll talk about the pieces of a simple node-express app, make some static pages, then add dynamic swag with swig :wink:

### Installing stuff

assuming you have node installed, you can make a folder for your project

`mkdir first-app`

Then cd into it and start installing all the things:

`cd first-app/`

`npm install swig`
`npm install express`

## create the app

copy the following text:

```
var app = require('express')();
var swig = require('swig');

//this will allow swig to render stuff
app.engine('html', swig.renderFile);

app.set('view engine', 'html');

//we will be keeping our html files in the views directory
app.set('views', __dirname + '/views');

//while prototyping, use express's caching
//my preference is to set both to true once app is rdy for production
app.set('view cache', false);
swig.setDefaults({ cache: false });

//routing here
app.get('/', function (req, res) {
        res.render('index', { /* you can add dynamic stuff here */ });
});
app.get('/second.html', function (req, res) {
        res.render('second.html', { /* add dynamic stuff here */ });
});

app.listen(9001);
console.log('your application is running on port 9001');
console.log('if running on your own compy, open with http://localhost:9001');

```


`vim app.js`

`<esc>:set paste` press esc key, and type `:` then `set paste` and press enter
press `i` to go into typey-mode

press `cntl-shift-v` to paste, and it should come to this (if not use the cursor to move around and make corrections as needed).



### 

`mkdir views`
`vim index.html`

```html
<html>
<body>
hello world
</body>
</html>
```


`vim second.html`
