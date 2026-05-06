[[Project Structure]]
[[LIFT]]
[[Signals]]
[[Components]]
### Install angular-cli
```
npm install -g @angular/cli@next 
```

### Create angular app
```
ng new <app-name>
```

### Start angular server (development)
```
ng serve
```


### Making a call to an api
#### On 'app.config.ts':
```
provideHttpClient()
```

#### On the service file:
```
this.http.get("https://localhost:5001/api/members").subscribe({
	next: response => this.members = response,
	error: error => console.log(error),
	complete: () => console.log("Completed the http request")
})
```

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

# Signals

