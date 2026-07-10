
```
@Autowired
public void injectDependencies(
	@Qualifier("secondBean") MyFirstClass myFirstClass
) {
	this.myFirstClass = myFirstClass;
}
```