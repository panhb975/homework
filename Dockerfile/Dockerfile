#See https://aka.ms/containerfastmode to understand how Visual Studio uses this Dockerfile to build your images for faster debugging.

FROM mcr.microsoft.com/dotnet/aspnet:5.0 AS base
WORKDIR /app
EXPOSE 8090

FROM mcr.microsoft.com/dotnet/sdk:5.0 AS build
WORKDIR /src
COPY ["homework.csproj", "."]
RUN dotnet restore "./homework.csproj"
COPY . .
WORKDIR "/src/."
RUN dotnet build "homework.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "homework.csproj" -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "homework.dll"]