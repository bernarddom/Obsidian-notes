#### @NotBlank
Does not let the value be null or be white spaces
```
@NotBlank
String fieldName;

List<@NotBlank(message = "Tag cannot be blank") String> tags;
```
####  @Size
Set the min and max size for strings and arrays
```
@Size(min = 1, max = 5)
Set<Seats> seats;

@Size(min = 20, max = 120)
String name;
```

#### @Email
Validate the value is an email
```
@Email
String email;
```

#### @Past and @Future
For dates
```
@Future(message = "Availability date must be in the future", groups = {OnCreate.class, OnUpdate.class})
    LocalDate availabilityDate;
```

#### @Positive and @Negative
