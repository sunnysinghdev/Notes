# Node JS Interview Material
![image](https://www.tutorialspoint.com/nodejs/images/nodejs_concepts.jpg)
###### It is not advisable to use Node.js for CPU intensive applications
--------------

* Building high-volume transactional customer-facing systems desirable
* ES6 or ECMA 2015.
* Express (Router set-up), `StrongLoop`, etc
* `EventLoop` architecture, `Child Process` and `Streams`.
* `Promises`.
* `Axios`, proficiency in REST-ful APIs.
* Node Debugging.
* Node Global variables and In-built libraries.
* Asynchronous programming and its quirks and workarounds
* Server-side templating languages [such as `Jade`, `EJS`, etc ]
* CSS preprocessors [such as `Stylus`, `SASS`, etc]
* HTML5, and CSS3
* [RDBMS, No SQL DB]

---
## Express Server

```javascript

var fs           = require("fs");
var express      = require('express');
var cookieParser = require('cookie-parser');
var bodyParser   = require('body-parser');

var app = express();

app.use(cookieParser());
app.use(bodyParser.json());

app.get('/listUsers', function (req, res) {
   fs.readFile( __dirname + "/" + "users.json", 'utf8', function (err, data) {
      console.log( data );
      res.end( data );
   });
})

var server = app.listen(8081, function () {
   var host = server.address().address
   var port = server.address().port
   console.log("Example app listening at http://%s:%s", host, port)
});
```
## Child Process

![image](https://cdn-media-1.freecodecamp.org/images/1*I56pPhzO1VQw8SIsv8wYNA.png)

### spawn()

`child_process.spawn(command[, args][, options])`

* Spawn method launches a new process with a given command.
* The spawn() method returns streams (stdout &stderr) and it should be used when the process returns a volume amount of data. 

```javascript
const { spawn } = require('child_process');

const child = spawn('pwd');

child.on('exit', function (code, signal) {
  console.log('child process exited with ' +
              `code ${code} and signal ${signal}`);
});
```

### fork()
`child_process.fork(modulePath[, args][, options])`.

* special case of the spawn() to create child processes.
* The fork method returns an object with a built-in communication channel in addition to having all the methods in a normal ChildProcess instance.
### exec()
* child_process.exec method runs a command in a shell/console and buffers the output