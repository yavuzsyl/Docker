FROM mcr.microsoft.com/dotnet/core/sdk:3.1 as build
WORKDIR /app
COPY *.csproj .
RUN dotnet restore
COPY . .
RUN dotnet publish DockerMvc.csproj -c Release -o out
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
WORKDIR /app
COPY --from=build /app/out .
ENV ASPNETCORE_URLS="http://*:4500"
ENV MySQL =  "Server=localhost;userid=root;password=9585200;database=Development;"
ENV ASPNETCORE_ENVIRONMENT="DEVELOPMENT"
ENTRYPOINT ["dotnet","DockerMvc.dll"]