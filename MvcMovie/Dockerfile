FROM microsoft/dotnet:sdk

ENV HOME=/app NUGET_PACKAGES=/usr/nuget/packages

WORKDIR /app

COPY ./MvcMovie.csproj /app/

RUN dotnet restore
