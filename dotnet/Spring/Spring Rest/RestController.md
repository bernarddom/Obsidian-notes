```
@RestController
public class PaymentRestController {
	@PostMapping(value="/payments")
	public ResponseEntity<PaymentInformation> initiatePayment(
		@RequestBody PaymentRequest PaymentRequest
	) {
		URI resultLocation = UriComponentBuilder
								.fromPath("/payments/{id}")
								.buildAndExpand(confirmation.getId())
								.toUri();
		return ResponseEntity.created(resultLocation).body(confirmation);
		
	}
}
```

1. @PostMapping
2. @GetMapping 
### @ResponseStatus

```
@GetMapping("/hello")
@ResponseStatus(HttpStatus.ACCEPTED)
public String sayHello() {
	return "Hello"
}
```

### Parameters
#### @RequestBody
When sending a value on a json file
```
@PostMapping("/post")
public String post(
	@RequestBody String message
) {
	return "message: " + message;
}
```

### Validation

1. @NotNull

#### Response