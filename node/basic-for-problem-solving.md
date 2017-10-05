### Read input from standard input stream
```javascript
var num = require('fs').readFileSync('/dev/stdin').toString();
```

### Write output
```javascript
console.log(s);
```

### for loops
```javascript
for(var i=1; i<num; i++){

}
```

### Run function in script from CLI
write function and export
```javascript
module.exports.solution = function(){
  //...
}
```

Then call like this. Assuming my 'myscript.js' is in the same directory.
```
node -e 'require("./myscript").solution()'
```
