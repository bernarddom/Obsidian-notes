[[Project Structure]]
[[LIFT]]
[[HTTPS]]
[[Local Storage]]
[[Signals]]
[[Components]]
[[Routing]]
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

# Signals

