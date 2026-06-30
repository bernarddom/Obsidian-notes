## To add authentication on the Program.cs file:
```
builder.Services.AddAuthentication(JwtBearerDefaults.AuthenticationScheme)
.AddJwtBearer(options =>
{
		var tokenKey = builder.Configuration["TokenKey"] ?? 
			throw new Exception("Token key not found - Program.cs");

	options.TokenValidationParameters = new TokenValidationParameters
	{
		ValidateIssuerSigningKey = true,
		IssuerSigningKey = new SymmetricSecurityKey(
			Encoding.UTF8.GetBytes(tokenKey)),
		ValidateIssuer = false,
		ValidateAudience = false
	};
});
```

```
app.UseAuthentication();
app.UseAuthorization();
```