# js
Javascript base code snippets

### for same dir app create
### `npx create-next-app .`


### tasks.json

```json
{
  "version": "2.0.0",
  "tasks": [
    {
      "type": "npm",
      "script": "dev",
      "group": "build",
      "problemMatcher": [],
      "label": "npm: dev",
      "detail": "next dev"
    }
  ]
}
```

#### vue js
```json
{
"version": "2.0.0",
"tasks": [
	{
	"type": "npm",
	"script": "dev",
	"problemMatcher": [],
	"label": "npm: dev",
	"detail": "vite",
	"group": {
		"kind": "build",
		"isDefault": true
	  },
	}
]
}

```

### TO kill the running port on 3000
#### netstat -ano | findstr :3000
#### taskkill /pid 11704 /F



### jsonconfig.json
```json
{
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "@/components/*": ["components/*"],
      "@/styles/*": ["styles/*"],
      "@/config/*": ["config/*"],
      "@/context/*": ["context/*"],
      "@/helpers/*": ["helpers/*"]
    }
  }
}

```

#### Email validation with jquery
```javascript
jQuery.validator.addMethod("isEmail", function (value, element) {
	let regex = /^([a-zA-Z0-9_\.\-\+])+\@(([a-zA-Z0-9\-])+\.)+([a-zA-Z0-9]{2,4})+$/;
	if (this.optional(element) || regex.test(value)) {
	    return true;
	} else {
	    return false;
	}
}, "Please enter a valid email address.");

$("#firstForm").validate({
rules:
{
    gender: { required: true },
    email: { required: false, email: true,  isEmail: true},
},
messages:
{
    gender:
    {
	required: "Please select gender."
    },
},
});   
	    
```

##### sort by alphabetically
```javascript
data.data?.sort((a, b) => a?.name > b?.name ? 1 : -1)
```

#### update the object

```javascript

let a = {x:1,y:2,z:3}

let b = {...a,x:6,p:9}// first it will take all the object of a , and update if any match otherwise create the new atrributes

console.log(b); // {x:6,y:2,z:3,p:9}
```
