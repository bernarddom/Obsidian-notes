## Properties
Entities has properties and they are defined like this:
```
public required string DisplayName { get; set; }
```

Which would make them required. It could be optional but it would need to be checked if it's null:
```
public string? DisplayName { get; set; }
```

