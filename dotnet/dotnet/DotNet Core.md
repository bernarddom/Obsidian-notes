### Database config ([[Sql Server]])
#### On the `appsettings.json`:

```
"ConnectionStrings": {
	"DefaultConnection": "Server=localhost,1433;Database=MyApiDb;UserId=sa;Password=Bernardo1->;TrustServerCertificate=True;"
}
```

### On the `Program.cs`:

```
builder.Services.AddDbContext<AppDbContext>(options =>
options.UseSqlServer(builder.Configuration.GetConnectionString("DefaultConnection")));
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

##### To list global tools
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

#### Certs Https

##### Clean
```
dotnet  dev-certs https --clean
```

##### Trust
```
dotnet  dev-certs https --trust
```
