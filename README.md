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

<br />

#### Execution Context:

a place where code run. area in a program/memory where js code executes. wherever we write js it createa golbal context. then inside this many small small context created

<br />

```JavaScript
fuction grandParent(){
  function parent(){
    let x = 9
    function chile(){
      
    }
    function sibling(){
      console.log(x)
    }
    child()
    sibling()
  }
  parent()
}
```

global context➔ grand parent ex context ➔ parent ex context ➔ child ex context + sibling ex context

every ex context has special variable this. the exe context remail in memry till the function execution end

claouser possble because of ex context as every has its own ex context and the clouser has the refernces becouse of this

exe context created only on the calling of function. no function call no ex context

`this` value defiend by how we call the function.

<br />

###### arrrow fucntion has only one rule, normal function has 4 rules. 

1. is Function invoked with new keyword. ( if so then the `this` = newly created object
2. call bind apply method ( `this` = the object used to call the function\\
3. if function invoked over an object like Obj.show ( `this` = Obj itself)
4. directly called function then ( `this` = Window object or undefined)

   <br />

<br />

<br />

```JavaScript
// 1 is functio invoke with new keyword(constructor call)
function x(){
  console.log(this) // this will be an empty object i.e {}
}
new x()


// 2. using call
function show(){
  console.log(this.name) // this will the object used to call the function
}
show()
const obj = {name:'Loin'}
const pers = {name:'Silver'}
const hero = {name:'sufer'}
//  there will be like some ways to log
function showName(ob){
  console.log(ob.name)
}
// or
function showName(name){
  console.log(name)
}
// the more intutuive way is using this

//  the call allows to control how we are goint to execute the fucntion. 
// overe here the obj is passed so the this pointto the obj
show.call(obj)
show.call(pers)
show.call(hero)

// diferent in call and apply and bind
// call and apply and bind to used to set the value of this
// bind take comman sepreated appply take as array
show.call(obj,1,2,3,4)
show.apply([obj,1,2,3,4])

// bind used to perrmanent set the `this` value insde a function and return that funtion
const newFn = show.bind(hero)
// above means create a new function and the `this` value should be the hero
// to call this we need to do
newFn()

// 3.
const obj = {fName:1, fn: function(){
  console.log(this.fName)
}}
obj.fn() // so this will log fName as 1
// 4. 
const x = obj.fn
x() // this will log undefuned. this is because of 4th rule. this will look in window object

```

