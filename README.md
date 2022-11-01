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
