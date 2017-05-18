# Intro to MVC

> An introduction to the Model View Controller pattern

## Templates

Most MVC tutorials go in order of Modes, Views, then Controllers or explain routing and controllers first. This time we're going to think of it differently. Let's first focus on the final product: the template. 

Templates are basic HTML views that are populated with data from deeper within the application. The data comes from the Models and Controllers. A View in the MVC model for a Node.js program running a blog could look like this:

*Note: There are multiple templating languages we can use in Node (or any laguage). Here we are using a templating language called Handlebars. Whenever you see `{{curlyBraces}}` that's some data being output by Handlebars. Handlebars also has functions for looping over data structures like arrays and objects to extract data from them. You'll see some that in these examples*

```html
<!DOCTYPE html>
<html>
<head>
  <title>{{pageTitle}}</title>
</head>
<body>
  <main class="contrainer">
    <div class="row">
      <div class="row-4 sidebar">
        <h2>Sidebar</h2>
        <ul>
          {{#each links}}
            <li><a href="{{this.url}}">{{this.label}}</a></li>
          {{/each}}
        </ul>
      </div>

      <div class="col-8 main-content">
        {{#each post}}
          <h1>{{this.title}}</h1>
          <h2>{{this.author}}</h2>

          {{this.postBody}}
      </div>
    </div>
  </main>
</body>
</html>
```

Templates and views are interchangeable words most of the time.

### How do Templates fit into MVC

Simple. Templates are the compiled views. What does that mean? You'll have to understand controllers and models before you can understand how a view is "compiled".

## Routing

In the MVC model everything stars with routing. 
