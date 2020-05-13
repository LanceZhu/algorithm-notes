## 牛客网

## 输入输出

Node.js

```javascript
var readline = require('readline')
const rl = readline.createInterface({
  input: process.stdin,
  output: process.stdout
})
var inputs = []
rl.on('line', function(line){
    inputs.push(line.trim());
    console.log(inputs.length)
})
rl.on('EOF', () => {
  // code
})
```