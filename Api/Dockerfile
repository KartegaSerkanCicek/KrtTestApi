FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS Build-env
WORKDIR c:\App\

COPY *.csproj .

RUN dotnet restore

COPY . ./
RUN dotnet publish --no-restore -c Release -o out

FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
WORKDIR c:\inetpub\wwwroot\Api\"dotnet", "Api.dll"
ENTRYPOINT ["dotnet", "Api.dll"]