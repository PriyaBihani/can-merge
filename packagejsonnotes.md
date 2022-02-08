```
{
	"name": "can-merge",
	"version": "0.0.0",
	"description": "",
	"main": "./bin/can-merge",
	"bin": {
		"can-merge": "./bin/can-merge"
	},
	"scripts": {
		"prepublishOnly": "safe-publish-latest",
		"prepublish": "not-in-publish || npm run prepublishOnly",
		"lint": "eslint --ext=js,mjs bin/** .",
		"pretest": "npm run lint",
		"tests-only": "nyc tape 'test/**/*.js'| tap-spec",
		"test": "npm run tests-only",
		"posttest": "aud --production"
	},
	"repository": {
		"type": "git",
		"url": "git+https://github.com/ljharb/can-merge.git"
	},
	"keywords": [],
	"author": "",
	"license": "MIT",
	"bugs": {
		"url": "https://github.com/ljharb/can-merge/issues"
	},
	"homepage": "https://github.com/ljharb/can-merge#readme",
	"devDependencies": {
		"@ljharb/eslint-config": "^20.1.0",
        // Use  npx aud instead of npm audit whether you have a lockfile or not. Good idea to run npm audit in CLI, it ensures that you don't unknowingly have vulnerabilities in your dep graph.
		"aud": "^1.1.5",
        // A tool for identifying and reporting on patterns found in ECMAScript/JavaScript code. (JS Parsing)
		"eslint": "^8.6.0",
        // NPM dependency that allows you to have pre-published life cycle scrips that don't run when you run `npm install`.
		"in-publish": "^2.0.1",
        // Istanbul's state of the art command line interface.
		"nyc": "^15.1.0",
        // ES spec-proposal-compliant Object.fromEntries shim. Invokes its "shim" method to shim Object.fromEntries if it's unavailable or noncompliant. A shim is a library that intercepts API calls and changes the arguments passed, handles the operation itself, or redirects the operation elsewhere.
		"object.fromentries": "^2.0.5",
        // Ensure that when you npm publish, the latest tag is only set for the truly latest version.
		"safe-publish-latest": "^2.0.0",
        // Formatted TAP output like Mocha's spec reporter (Testing)
		"tap-spec": "^5.0.0",
        // A Test Anything Protocol Framework for Node.js (Testing)
		"tape": "^5.4.0"
	},
	"dependencies": {
        // GitHub GraphQL API client from browsers and Node.
		"@octokit/graphql": "^4.8.0",
        // Terminal String styling.
		"chalk": "^4.1.2",
        // Loads environment variables from the .env file.
		"dotenv": "^10.0.0",
        // Retrieves github repo info without relying upon the git command
		"git-repo-info": "^2.1.1",
        // Parse .git/confit into a JavaScript object sync or asyn.
		"parse-git-config": "^3.0.0",
        // helps you build interactive command line tools, by parsing arguments and generating an elegant user interface.
		"yargs": "^17.3.1"
	},
	"engines": {
		"node": "^14 || >= 16"
	}
}
```
