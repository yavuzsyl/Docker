FROM mcr.microsoft.com/dotnet/core/sdk:3.1
WORKDIR /app
COPY . .
RUN dotnet restore
RUN dotnet publish DockerMvc.csproj -c Release -o out
WORKDIR out
ENV ASPNETCORE_URLS="http://*:4500"
ENTRYPOINT ["dotnet","DockerMvc.dll"]