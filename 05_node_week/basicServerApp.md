```
var express = require('express'),
    app     = express(),
    server  = require('http').createServer(app),
    handlebars = require('express-handlebars');

  // tell express where the views are
  app.set('views', path.join(__dirname, 'views'));

  // tellin express were using handlebars
  app.set('view engine', 'hbs');

  app.get('/', function(request, response){
    // request object is from the client,
    // the response is what were sending back
    response.send('Hey I just built a serverrrrr')
  })

  app.get('/blueberries', function(req, res){
    res.send('i like blueberries')
  })


// first argument is the port number
server.listen(3000, function(){
  console.log('server is listening on port 3000')
})

```
