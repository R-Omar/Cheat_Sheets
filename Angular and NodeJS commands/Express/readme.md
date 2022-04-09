## Create an express application
1. Initialize  a node project `npm init`
2. Add Express module to the project `npm instal express --save`
3. Create in the project the file that will fire up the Express application `app.js`

Code example of a basic Express application :
```javascript
const express = require('express');
const app = express();
app.listen(4000,()=>console.log('sever listening on port 4000'));
```