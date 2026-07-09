Is used for injecting values on a class

```
@Configuration
@PropertySource("classpath:database.properties")
public class ApplicationConfig{
	@Value("${jdbc.url}")
	private String url;
	
	@Value("${jdbc.username}")
	private String username;
	
	@Value("${jdbc.password}")
	private String password;
	
	private String defaultLocale;
	
	@Value("#{systemProperties['user.region']}")
	public void setDefaultLocale(String defaultLocale) {
		this.defaultLocale = defaultLocale;
	}
	
	@Bean
	public DataSource dataSource() {}
}
```