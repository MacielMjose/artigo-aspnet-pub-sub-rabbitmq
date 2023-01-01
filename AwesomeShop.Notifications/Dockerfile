#See https://aka.ms/containerfastmode to understand how Visual Studio uses this Dockerfile to build your images for faster debugging.

FROM mcr.microsoft.com/dotnet/aspnet:7.0 AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/sdk:7.0 AS build
WORKDIR /src
COPY ["AwesomeShop.Notifications/AwesomeShop.Notifications.csproj", "AwesomeShop.Notifications/"]
RUN dotnet restore "AwesomeShop.Notifications/AwesomeShop.Notifications.csproj"
COPY . .
WORKDIR "/src/AwesomeShop.Notifications"
RUN dotnet build "AwesomeShop.Notifications.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "AwesomeShop.Notifications.csproj" -c Release -o /app/publish /p:UseAppHost=false

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "AwesomeShop.Notifications.dll"]