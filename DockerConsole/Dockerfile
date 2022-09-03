#FROM mcr.microsoft.com/dotnet/runtime:6.0 AS base
#WORKDIR /app
#
#FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
#WORKDIR /src
#COPY ["DockerConsole/DockerConsole.csproj", "DockerConsole/"]
#RUN dotnet restore "DockerConsole/DockerConsole.csproj"
#COPY . .
#WORKDIR "/src/DockerConsole"
#RUN dotnet build "DockerConsole.csproj" -c Release -o /app/build
#
#FROM build AS publish
#RUN dotnet publish "DockerConsole.csproj" -c Release -o /app/publish /p:UseAppHost=false
#
#FROM base AS final
#WORKDIR /app
#COPY --from=publish /app/publish .
#ENTRYPOINT ["dotnet", "DockerConsole.dll"]

FROM mcr.microsoft.com/dotnet/runtime:6.0 AS base
WORKDIR /app
COPY bin/Release/net6.0/publish /app/
ENTRYPOINT ["dotnet", "DockerConsole.dll"]