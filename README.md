#Decoupled MEAN Todo App

cd into api and ```npm install```

Run Mongod in one terminal, then inside api folder run ```nodemon```

cd into frontend and run ```budo```


Note, inside your $resources, this route should be a full route to your api folder,
serving up your backend.

```app.service('Todo', function($resource) {
  return $resource('http://localhost:3000/api/todos/:id', {
    update: {
      method: 'PATCH' // this method issues a PUT request
    }
  });
});```

Inside server.js, note ```var cors = require('cors');``` and ```app.use(cors())``` to prevent you from getting errors. 
