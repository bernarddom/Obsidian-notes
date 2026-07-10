```
@Autowired
public void setMyFirstClass(
	@Qualifier("secondBean") MyFirstClass myFirstClass
) {
	this.myFirstClass = myFirstClass;
}
```