FROM mcr.microsoft.com/dotnet/sdk:5.0 as build
WORKDIR /build
COPY  . .
RUN dotnet restore
RUN dotnet build -c Release -o output

FROM mcr.microsoft.com/dotnet/sdk:5.0 
WORKDIR /app
COPY --from=build /build/output .
ENTRYPOINT ["dotnet","DeploymentGuide.dll"]