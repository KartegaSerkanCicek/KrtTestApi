FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
WORKDIR c:\inetpub\wwwroot

# copy csproj and restore as distinct layers
COPY *.sln .
COPY Api/*.csproj ./aspnetapp/
RUN dotnet restore

# copy everything else and build app
COPY aspnetapp/. ./aspnetapp/
WORKDIR c:\inetpub\wwwroot\aspnetapp
RUN dotnet publish -c release -o /app --no-restore

# final stage/image
FROM mcr.microsoft.com/dotnet/aspnet:6.0
WORKDIR c:\inetpub\wwwroot\aspnetapp
COPY --from=build /app ./
ENTRYPOINT ["dotnet", "api.dll"]
=======
FROM mcr.microsoft.com/dotnet/aspnet:6.0 AS runtime
WORKDIR /app
COPY published/ c:\inetpub\wwwroot\Api
ENTRYPOINT ["dotnet", "Api.dll"]
