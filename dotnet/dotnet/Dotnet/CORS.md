### Configure
#### On Program.cs
```
builder.Services.AddCors();

app.UseCors(options => options.AllowAnyHeader().AllowAnyMethod().WithOrigins("http://localhost:4200", "https://localhost:4200"));
```

## Services
Add a service an its interface on Program.cs:
```
builder.Services.AddScoped<ITokenService, TokenService>();
```
