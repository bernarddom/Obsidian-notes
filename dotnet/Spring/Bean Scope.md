It is the availability in the context of the application.

	1.-Singleton
	2.-Prototype
	3.-Request
	4.-Session
	5.-Application
	6.-WebSocket

#### Bean scoping
```
@Configuration
public class MyConfiguration {
	@Bean
	@Scope('prototype')
	public Bean1 bean1() {}
	
	@Bean
	@SessionScope
	public Bean2 bean2() {}
}
```