# [[Sql Server]]

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

### DbContext
#### Example
```
public class AppDbContext(DbContextOptions options) : DbContext(options)
{
	public DbSet<AppUser> Users { get; set; }
}
```

