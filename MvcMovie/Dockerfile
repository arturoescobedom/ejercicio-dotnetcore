# Stage 1: The development stage:
FROM microsoft/dotnet:sdk AS development

ENV HOME=/app NUGET_PACKAGES=/usr/nuget/packages

WORKDIR /app

COPY ./MvcMovie.csproj /app/

RUN dotnet restore

# Stage 2: The Builder stage:
# This is the stage where the app code gets compiled.
FROM development AS builder

COPY . /app/

RUN dotnet publish --configuration Release

# Stage 3: The deployable stage:
FROM microsoft/dotnet:runtime AS deployable

COPY --from=builder /app/bin/Release/netcoreapp2.0/publish /app

WORKDIR /app

CMD ["dotnet", "MvcMovie.dll"]
