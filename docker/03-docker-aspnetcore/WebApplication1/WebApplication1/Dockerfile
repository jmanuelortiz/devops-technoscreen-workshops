FROM microsoft/dotnet:2.1-aspnetcore-runtime-nanoserver-1709 AS base
WORKDIR /app
EXPOSE 59548
EXPOSE 44327

FROM microsoft/dotnet:2.1-sdk-nanoserver-1709 AS build
WORKDIR /src
COPY WebApplication1/WebApplication1.csproj WebApplication1/
RUN dotnet restore WebApplication1/WebApplication1.csproj
COPY . .
WORKDIR /src/WebApplication1
RUN dotnet build WebApplication1.csproj -c Release -o /app

FROM build AS publish
RUN dotnet publish WebApplication1.csproj -c Release -o /app

FROM base AS final
WORKDIR /app
COPY --from=publish /app .
ENTRYPOINT ["dotnet", "WebApplication1.dll"]
