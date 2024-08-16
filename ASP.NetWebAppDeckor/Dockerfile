#See https://aka.ms/customizecontainer to learn how to customize your debug container and how Visual Studio uses this Dockerfile to build your images for faster debugging.

#FROM mcr.microsoft.com/dotnet/aspnet:6.0
#WORKDIR /app
#COPY /bin/Release/net6.0/publish /app
#ENTRYPOINT ["dotnet","ASP.NetWebAppDeckor.dll"]



FROM mcr.microsoft.com/dotnet/sdk:6.0 as build
WORKDIR /app 
COPY *.csproj .
RUN dotnet restore
COPY . .
RUN dotnet restore
RUN dotnet publish ASP.NetWebAppDeckor.csproj -c Release -o out
FROM mcr.microsoft.com/dotnet/aspnet:6.0
WORKDIR /app
COPY --from=build /app/out .
ENV ASPNETCORE_URLS="http://*:4500"
ENTRYPOINT ["dotnet","ASP.NetWebAppDeckor.dll"]








