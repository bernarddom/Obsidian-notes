```
@Configuration
public class ApplicationConfig {
	@Bean
	@Qualifier('primary')
	public AccountRepository primary{
		return new JdbcAccountRepository();
	}
	
	@Bean
	@Qualifier('secondary')
	public AccountRepository secondary(){
		return new JdbcAccountRepository();
	}
}
```

```
@Service
public class DefaultPaymentService {
	@Autowired
	public DefaultPaymentService(
		@Qualifier('primary') AccountRepository
	) {
		this.accountRepository = accountRepository;
	}
}
```