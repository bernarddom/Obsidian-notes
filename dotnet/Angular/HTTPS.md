# Running angular with https
### Create ssl directory inside the project:
```
mkdir ssl
```

### Create certificate inside ssl folder:
```
mkcert localhost
```

### Add these lines in the "serve" object inside the 'angular.json' file:
```
"options": {
	"ssl": true,
	"sslCert": "./ssl/localhost.pem",
	"sslKey": "./ssl/localhost-key.pem"
},
```
