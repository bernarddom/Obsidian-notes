```
@Service
@Profile("cloud")
public class DefaultPaymentService implements PaymentService {}
```

To set a bean only for a specific profile:
```
@Configuration
public class ApplicationConfig {
	@Bean
	@Profile("cloud")
	public PaymentService paymentService () { ... }
}
```

The `@Profile` annotation can be used also on the class level
### Activation

#### Programatically

```
public static void main() {
	AnnotationConfigApplicationContext annotation;
	annotation = new AnnotationConfigApplicationContext();
	annotation.getEnvironment().getActiveProfile();
	annotation.scan("com.alibou.sample");
	annotation.refresh();
	
	PaymentService paymentSer = applicationContext.getBean(PaymentService.class);
}
```

#### Properties file

`application.yaml`
```
spring:
	profiles:
		active: cloud
```

Setting the active profile on `application.properties`
```
spring.profiles.active=cloud
```

Then creating an `application-cloud.properties` file:
```
my.custom.property=Hello cloud
```

It can also be set on the application:
```
@SpringBootApplication
public class ExampleApplication {
	public static void main(String[] args){
		varr app = new SpringApplication(ExampleApplication.class);
		app.setDefaultProperties(Collections.singletonMap("spring.profiles.active", "dev"));
		var ctx = app.run(args);
	}
}
```