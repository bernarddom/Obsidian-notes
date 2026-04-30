
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
