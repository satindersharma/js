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


Number.MAX\_SAFE\_INTEGER

cannot add more that this. this is max safe integer

<br />

to create beger then this use BigInt datatype

let num = BigIn()

typeof null is object but this is due to the early emplimentation is in c and c++ . this is a legacy bug. c and c ++ null is treated as object

false values:  if evaluated with if you get false. they are 6

&#x20;0, false, "", undefined, null, NaN

NaN is specail. also typeof NaN is number,. if you look for NaN == NaN is false and NaN === NaN. so use isNaN(NaN now it will give true.\
also same with -0.  -0 == -0 id true 0 == -0 is also true. so use Object.is(0,-0) is false and Object.is(NaN, NaN) is true

<br />

Clousers: A fucntion with some presererved values creates a closure. A closure is created when a function preserves variables outside of its scope.

```JavaScript
let myName = 'js'
let dept = 'web'
function show{
  
}
console.dir(show)  
  // exmpand this and see the [[Scopes]] this will have  scopes Script and Global


```

```JavaScript

function show{
  let myName = 'js'
let dept = 'web'
  function inner(){
    console.log(myName
               )
  }
}
console.dir(show)  
  // exmpand this and see the [[Scopes]] this will have  scopes Closure and Global
// this Closure scope has the variable myName

```

preservees variables are live, like if you change them in outer, inner has the reference of it. 

benfites to have a private varaibles. so no one can modify , off course they can see

 

#### IIFE  imiditialy invoked function expression

(function(){})()  this is an IIFE

as we knwo all the js fine compbines, so if there is same name variabl ediclare in another file won;'t get effected. so we just create a fucntion and keep everythin inside that and immmidetaily invoked that funtion. to keep the varialbes local, so that your variable doesn;'t tuch other file/scripts 

in earliy daes like node files and react files were iife in intself. this might change with the module system. when the webpack rus. the react component or any file, becomes an iife so that it will not effect otheres

<br />

#### curring:

<br />

#### is JS interpreated and Compiled?

how js code executed by browser

when browser see <scrcript> tag. it download the file in streams. using this streams browser create tokens(simply our code parts) then parsing happens and then js create AST abstract syntaxt Tree 

parsing do two things . 1syntax checking and . scope and initialization

this AST goes to the Interpreter . this interpreter gieves us the byte code. now this byte code executed by the browser

after  crome brings its js engine v. now what they did . the byte code is very generic . it build with default setup. it has problem . every machine is different. now the byte code is taken by compiler the google name it trubo fan. the complier look for the repetiable functions and make it fast. that is it is not only iterpreted but also compiled.

<br />

#### Hoisting

by defualt there is no such terms in js. it is given b the developer. most of them says it is moveing athe variable and function to the top. but that is not

js code execute in tow phases.  1,parsing/(memroy allocation phase) and scope intitializing. in this phase the js all variable scope sets the defaults. 



a function returning a function is called curring

<br />

<br />



