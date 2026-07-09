```
@Service
@Profile("cloud")
public class DefaultPaymentService implements PaymentService {}
```

```
@Configuration
public class ApplicationConfig {
	@Bean
	@Profile("cloud")
	public PaymentService paymentService () { ... }
}
```

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

`application.properties`
```
spring.profiles.active=cloud
```

