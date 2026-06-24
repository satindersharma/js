# JS

#### Variables

###### var
it get added to window even if you now use var keyword it will use var

###### let


var is a function scope where let is local scope
actually let create a block scope
by default tehr eis only two scope global and function/local scope
but when we write let it creates a block scope

local scope == parent scope == function scope
```javascript
    function show(){
    if(1){
    var functionScope = "hey";
    let localScope = "'hel"
    }
	console.log(functionScope,localScope )
    }
    
    show()
```


#### Data Types

two types primitives and non primitives

###### primitives
undifined
null
Number
BIgInt
Symbol
String
Boolean

###### non primitives
Object




idff of undifined and null
unfined is a default value and null is a expicit value


