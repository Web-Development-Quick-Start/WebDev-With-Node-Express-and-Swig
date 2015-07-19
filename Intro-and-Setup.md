## Templating

Before we were creating static pages, and you can do that with node and express,
but the real power starts to show once you leverage templates and create
dynamic content for your user (i.e. custom welcome page, their favorite links, etc)

We'll talk about the pieces of a simple node-express app, make some static pages, then add dynamic swag wit swig :wink:

### Installing stuff


`npm install swig`
`npm install express`

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
