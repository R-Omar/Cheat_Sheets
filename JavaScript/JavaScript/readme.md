## Classes and objects
Declare a class and instantiate an object
```javascript
class className {
    constructor(prop1, prop2) {
        this.prop1 = prop1;
        this.prop2 = prop2;
    }
    
    functionName(){
        //do something
    }
}

let obj = new className(val1,val2);
```

## Arrays
```javascript
let arr = [];
arr.push(value);        // add element at the end of the array
arr.unshift(value);     // add element at the beginning of the array
arr.pop()               // delete the last element
arr[index]              // access the element in index position
```

## for… of et for… in
```javascript
for (let i in passengers) {
   console.log(passengers[i]);
}

for (let passenger of passengers) {
   console.log(passenger);
}
```
