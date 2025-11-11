### [[Docker]]

#### Create docker container
``` 
sudo docker run -e "ACCEPT_EULA=Y" -e "SA_PASSWORD=Bernardo1->" \
   -p 1433:1433 --name sqlserver \
   -d mcr.microsoft.com/mssql/server
```


##### How to start mssql from docker
```
/opt/mssql-tools18/bin/sqlcmd -S localhost -U SA -P 'Bernardo1->' -C
```


## Install Swagger
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

#### List databases:
```
SELECT name from sys.databases;
```

#### List tables from database:
```
SELECT TABLE_NAME FROM INFORMATION_SCHEMA.TABLES WHERE TABLE_TYPE = 'MyApiDb';
```
