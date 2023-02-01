FROM mcr.microsoft.com/windows/servercore:1607 AS Build-env
WORKDIR c:\App\

COPY *.csproj .

RUN dotnet restore

COPY . ./
RUN dotnet publish --no-restore -c Release -o out


WORKDIR c:\inetpub\wwwroot\Api\"dotnet", "Api.dll"
ENTRYPOINT ["dotnet", "Api.dll"]
