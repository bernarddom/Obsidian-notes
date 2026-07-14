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

### Set environment
```
private Environment environment;

@Autowired
public void setEnvironment(Environment) {
	this.environment = environment;
}

public String getOsName() {
	return environment.getProperty("os.name")
}

public String readProp() {
	return environment.getProperty("my.custom.property");
}
```

#### Property source
`@PropertySouce` annotation lets call properties from another .properties file
```
@PropertySource("classpath:custom.properties")
public class MyFirstService {}
```

#### @Value annotation
To read values from `application.properties`
```
@Value("${my.custom.property}")
private String myProperty;

public String getCustomProperty() {
	return customProperty;
}
```