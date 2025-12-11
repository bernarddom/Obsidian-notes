[[Controllers]]
[[Entities]]
## Gitignore file:
```
dotnet new gitignore
```

## New project (api with controllers):
```
dotnet new webapi -controllers -n API 
```

## Database config ([[Sql Server]])

#### On the `appsettings.json`:

```
"ConnectionStrings": {
	"DefaultConnection": "Server=localhost,1433;Database=MyApiDb;UserId=sa;Password=Bernardo1->;TrustServerCertificate=True;"
}
```

#### On the `Program.cs`:

```
builder.Services.AddDbContext<AppDbContext>(options =>
options.UseSqlServer(builder.Configuration.GetConnectionString("DefaultConnection")));
```

## Swagger
#### Install
```
dotnet add package NSwag.AspNetCore
```

#### In Program.cs
```
if (app.Environment.IsDevelopment())
{
	app.MapOpenApi();
	app.UseSwaggerUi(options =>
	{
		options.DocumentPath = "/openapi/v1.json";
	});
}
```

## Solutions
##### To create a solution file:
```
dotnet new sln
```

##### To add a solution to an already created project:
```
dotnet sln add <project-dir>
```

## Tools
#### To list global tools
```
dotnet tool list -g
```

### Entity Framework
##### To install:
```
<PackageReference Include="Microsoft.EntityFrameworkCore.Design" Version="9.0.10" />
```

##### Install dotnet-ef
```
dotnet tool install -g dotnet-ef
```

##### Create migration and add output to file:
```
dotnet ef migrations add InitialCreate -o Data/Migrations
```

##### Update database:
```
dotnet ef database update
```

### Certs Https

##### Clean
```
dotnet  dev-certs https --clean
```

##### Trust
```
dotnet  dev-certs https --trust
```

## Encoding
### SHA512
```
var hmac = new HMACSHA512();

var password = hmac.ComputeHash(Encoding.UTF8.GetBytes(password));
```

## DbContext
### Example
```
public class AppDbContext(DbContextOptions options) : DbContext(options)
{
	public DbSet<AppUser> Users { get; set; }
}
```
