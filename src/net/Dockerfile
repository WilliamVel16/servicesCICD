FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build

COPY /src/net /dotnetapp

WORKDIR /dotnetapp

EXPOSE 80
RUN dotnet restore

RUN dotnet build "myFirstService.csproj" -c Release -o /app/build

RUN dotnet publish -c release -o /app

FROM mcr.microsoft.com/dotnet/aspnet:6.0
WORKDIR /app
COPY --from=build /app .
ENTRYPOINT ["dotnet", "myFirstService.dll"]
