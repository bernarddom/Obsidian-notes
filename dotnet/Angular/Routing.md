On `app.route.ts`:
```
{
	path: '',
	component: Home
},
{
	path: 'members',
	component: MemberList
},
```

#### Route programmatically
```
private router = inject(Router);
...
this.router.navigateByUrl("/members");
```