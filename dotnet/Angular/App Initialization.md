
Used to initialize some data before the app starts

```
export class InitService {
	private accountService = inject(AccountService)
	init() {
		const userString = localStorage.getItem("user");
		if (!userString) return of(null);
		const user = JSON.parse(userString);
		this.accountService.currentUser.set(user);
		return of(null);
	}
}
```

On the app `app.config.ts`:
```
provideAppInitializer(async () => {
	const initService = inject(InitService);
	return new Promise<void>((resolve) => {
		setTimeout(async () => {
			try {
				return lastValueFrom(initService.init())
			} finally {
				const splash = document
								.querySelector("#initial-splash"); //loader
				if (splash) {
					splash.remove();
				}
				resolve()
			}
		}, 500)
	})
})
```