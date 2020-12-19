# repos-setup
Frequently used tools for setting up React, Node repos


### Prettier linting
Dry run
```
prettier **/*.{js,json}
```
Commit
```
prettier **/*.{js,json} --write
```

### ESlint
```
"lint": "eslint . --ignore-path ./.gitignore --ext .js",
```


### Jest
```
jest --runInBand --coverage
jest --config jest.config.unit.json
jest --watch
```
Prevent reading dir like `postgres-data` by editing `jest.config.json`.
```
{
	"testRegex": "((\\.|/*.)(spec))\\.js?$",
	"clearMocks": true,
	"testEnvironment": "node",
	"testPathIgnorePatterns": [
		"/node_modules/",
		"postgres-data",
		"db.sql"
	],
	"watchPathIgnorePatterns": [
		"/node_modules/",
		"postgres-data",
		"db.sql"
	]
}
```

### Husky
```
"husky": {
  "hooks": {
    "pre-commit": "lint-staged"
  }
}
```
