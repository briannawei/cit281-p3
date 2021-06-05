## Project 3


### p3-module.js
```

/*
Name: Brianna Wei
Professor Phil Colbert
Project 3
p3-module.js
*/

function validDenomination(coin) {
    let denomArray = [1, 5, 10, 25, 50, 100];
    if (denomArray.indexOf(coin) !== -1) {
        return true;
    }
    else {
        return false;
    }
}

function valueFromCoinObject(obj) {
    const {denom = 0, count = 0} = objDecon;
    return denom * count;
}


function valueFromArray(arr) {
    const resultReduced = (result, currentObj) => result + currentObj + valueFromCoinObject(currentObj);
    return arr.reduce(resultReduced);
}


function coinCount(...coinage) {
    return valueFromArray(coinage);
}

// console.log statements given
console.log("{}", coinCount({denom: 5, count: 3})); 
console.log("{}s", coinCount({denom: 5, count: 3},{denom: 10, count: 2})); 
const coins = [{denom: 25, count: 2},{denom: 1, count: 7}]; 
console.log("...[{}]", coinCount(...coins)); 
console.log("[{}]", coinCount(coins));


```



### p3-server.js

```
/*
Name: Brianna Wei
Professor Phil Colbert
Project 3
p3-server.js
*/

// part 7
const { fstat } = require("fs");
const { coinCount } = require("./p3-module.js");
const fastify = require("fastify")();

// part 8
const server = http.createServer((request,reply) => {
      fs.readFile(`${__dirname}/index.html`, (request, reply) => {
          reply
            .code(200);
            header("Content-Type", "text/html; charset=utf-8");
          fastify.listen(port, IPAdress, (err, address) => {
              if (err) {
                  address.code(500);
                  console.log(err);
                  process.exit(1);
                };

            });
        });
});

server.listen(port, hostname,() => {
    console.log(`Server running at http://${hostname}:${port}/`);
});
 

const http = require('http')
const fs = require('fs');
const hostname = '127.0.0.1'
const IPAdress = "localhost";
const port = 8080;

fastify.get("/coin", (denom, count) => {
    const {denom, count} = request.query;
    coinCount()
    reply
      .code(200)
      .header("Content-Type", "text/html; charset=utf-8")
      .send(`<h2>Value of ${count} of ${denom} is ${coinValue}</h2><br /><a href="/">Home</a>`);
  });

// part 10
fastify.get("/coins", (option) => {
    const {option} = request.query;
    coinValue()
    coinCount({ denom: 5, count: 3 }, { denom: 10, count: 2 }); //option 1
    coinCount(...coins); // option 2
    coinCount(coins); // option 3
    reply
      .code(200)
      .header("Content-Type", "text/html; charset=utf-8")
      .send(`<h2>Option ${option} value is ${coinValue}</h2><br /><a href="/">Home</a>`);
  });
  
  
```

