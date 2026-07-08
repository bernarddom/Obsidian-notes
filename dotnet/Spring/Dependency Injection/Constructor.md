
```
@Service
public class DefaultPaymentService {
	private final AccountRepository;
	
	public DefaultPaymentService(AccountRepository accountRepository) {
		this.accountRepository = accountRepository;
	}
}
```