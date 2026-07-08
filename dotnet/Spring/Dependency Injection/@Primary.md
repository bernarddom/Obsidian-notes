```
@Configuration
public class ApplicationConfig {
	@Bean
	@Primary
	public AccountRepository primary() {
		return new JdbcAccountRepository();
	}
	@Bean
	public AccountRepository secondary() {
		return new JdbcAccountRepository();
	}
}
```

```
@Service
public class DefaultPaymentService {
	@Autowired
	public DefaultPaymentService (
		AccountRepository accountRepository
	) {
		this.accountRepository = accountRepository;
	}
}
```