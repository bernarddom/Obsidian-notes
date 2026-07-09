```
@Configuration
public class ApplicationConfig {
	@Autowired
	@Bean
	public PaymentService paymentService() {
		var profile = Profile.of('clout');
		var isOkay = this.environment.acceptsProfiles(profile);
		this.environment.getProperty("data.driver");
		...
	}
}
```

