FROM mcr.microsoft.com/dotnet/aspnet:6.0 AS runtime
WORKDIR /app
COPY published/ c:\inetpub\wwwroot\Api
ENTRYPOINT ["dotnet", "Api.dll"]
