[[DotNet Core]]
## To define a controller:
```
[Route("api/[controller]")]
[ApiController]
public class ExampleController(AppDbContext context) : ControllerBase
```

The "\[controller\]" part makes the endpoint as:

```
api/Example
```

## Asynchronous endpoint
To create one:
```
public async Task<ActionResult<IReadOnlyList<AppUser>>> GetMembers()
```

And to call a method:
```
var members = await context.Users.ToListAsync();
```


