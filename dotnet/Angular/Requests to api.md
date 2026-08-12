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

Or
```
try {
	return lastValueFrom(this.http.get<User[]>("https://localhost:5001/api/members"))
} catch (error) {
	console.log(error)
	throw error
}
```