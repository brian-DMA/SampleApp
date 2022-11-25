FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build-env
WORKDIR /WebApi

COPY . .
RUN dotnet restore
RUN dotnet publish -c Release -o out

FROM mcr.microsoft.com/dotnet/aspnet:6.0
WORKDIR /WebApi
COPY --from=build-env /WebApi/out .
ENV ASPNETCORE_URLS=http://+:5005
ENTRYPOINT ["dotnet", "WebApi.dll"]