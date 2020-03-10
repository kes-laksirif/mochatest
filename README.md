# mochatest
## Testing Node Applications with Mocha and Chai

##### Node Project Instructions

###### Project init and dependancy installation
```
npm init
npm install mocha chai --save-dev
```

###### package.json
Set test runner
```
"test": "mocha || true"
```

Complete code
```
{
  "name": "mochatest",
  "version": "1.0.0",
  "description": "A simple app to see unit testing implemented",
  "main": "app.js",
  "scripts": {
    "test": "mocha || true"
  },
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "chai": "^4.2.0",
    "mocha": "^7.1.0"
  }
}
```

###### app.js
```
module.exports = {

    sayHello: function() {
        return 'hello';
    },

    addNumbers: function(value1, value2) {
        return value1 + value2;
    }
}
```

###### test\appTest.js
```
const assert = require('chai').assert;      
const app = require('../app');

//Results
sayHelloResult = app.sayHello();
addNumbersResult = app.addNumbers(5,5);

describe('App', function() {
    describe('sayHello()', function() {
        it('sayHello should return hello', function() {
            assert.equal(sayHelloResult, 'hello');
        });
    
        it('sayHello should return type string', function(){
            assert.typeOf(sayHelloResult, 'string');
        });
    });
    
    describe('addNumbers()', function() {
        it('addNumbers should return grater than 5', function() {
            assert.isAbove(addNumbersResult, 5);
        });
    
        it('addNumbers should return type number', function(){
            assert.typeOf(addNumbersResult, 'number');
        });
    });
});
```

###### Run test
```
npm test
```

##### Git Instructions
```
echo "# mochatest" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/kes-laksirif/mochatest.git
git push -u origin master
```
