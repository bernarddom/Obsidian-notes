On the `angular.json` file
```
...
"@schematics/angular:guard": {
	"skipTests": true,
	"path": "src/core/guards"	
}
```

### Create a route guard

```
ng g guard <name>
```

### Program
```
export const authGuard: CanActivateFn = () => {
	const accountService = inject(AccountService);
  	const toast = inject(ToastService);
	if (accountService.currentUser()) return true;
	else {
		toast.error("You shall not pass!");
		return false;
	}
};
```

### A dummy route
On the `app.route.ts`:
```
{
	path: '',
	runGuardsAndResolvers: 'always',
	canActivate: [authGuard],
	children: [
		{
			path: 'members',
			component: MemberList,
			canActivate: [authGuard]
		},
		{
		path: 'members/:id',
		component: MemberDetailed
		},
		{
		path: 'lists',
		component: Lists
		},
		{
		path: 'messages',
		component: Messages
		},
	]
},
```