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
