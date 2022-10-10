
## Verdaccio
### Pros:
  * Npm version fully support
  * Free private
### Cons:
  * Maintain a server

Installation
```
$ docker pull verdaccio/verdaccio
$ docker run -d --name verdaccio -p 4873:4873 verdaccio/verdaccio
``` 

Check the server
```
http://localhost:4873
```

Add user
```
$ npm adduser --registry http://localhost:4873
```

Login
```
$ npm login --registry http://localhost:4873
```

Publish (or un-publish with --force)
```
$ npm publish --registry http://localhost:4873
```

Client usage
```
$ npm install --registry http://localhost:4873 <package-name>
```

## GitHub
### Pros:
  * Serverless
### Cons:
  * Bad version updating
### Example:
* https://github.com/jeremy-test-org/hello-npm

Publish
```
$ git push origin master
```

Optional: Update with tags
```
$ git tag v<x.y.z>
$ git push origin --tags
```

Client usage (ex: $ npm i -S git@github.com:jeremy-test-org/hello-npm.git#v1.0.2)
```
$ npm i -S git@github.com:<git path>
$ npm i -S git@github.com:<git path>:#<tag>
```

## Npm Orgs
### Pros:
  * SaaS
### Cons:
  * Public free / private non-free
### Example:
* https://www.npmjs.com/package/@jeremy-test-org/hello-npm

Register an user and an organization in npm orgs.

Must have a scope ex: @scope/project-name in package.json

Login (ref: https://docs.npmjs.com/creating-a-new-npm-user-account)
```
$ npm login
$ npm whoami
```

Publish
```
$ npm publish --access public
```

Client usage
```
$ npm install <package-name>
```