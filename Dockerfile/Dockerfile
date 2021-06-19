#See https://aka.ms/containerfastmode to understand how Visual Studio uses this Dockerfile to build your images for faster debugging.

FROM mcr.microsoft.com/dotnet/sdk:5.0 
ENV ASPNETCORE_ENVIRONMENT=Development
ENV DOTNET_USE_POLLING_FILE_WATCHER=true  
ENV ASPNETCORE_URLS=http://+:8077  
EXPOSE 8077
LABEL version=1.0 \
 name=homework
WORKDIR /app
COPY ["publish/", "."]
ENTRYPOINT ["dotnet", "homework.dll"]

