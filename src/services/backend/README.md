# .NET Core Api Project Example

## Commands used to create the environment:

### Create the solution:

```sh
# /src/services/backend
dotnet new sln
```

### Create the project:

```sh
# /src/services/backend
dotnet new webapi --output ./ApiTest
```

### Add the project in solution:

```sh
# /src/services/backend
dotnet sln add ./ApiTest
```

## Commands to Launch the application

### Launch using the IIS Express profile:

```sh
  dotnet run --launch-profile "IIS Express"
```

After launch, we can open the API using the URL: `https://localhost:5001/WeatherForecast`.
