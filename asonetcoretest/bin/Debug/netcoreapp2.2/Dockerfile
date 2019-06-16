FROM mcr.microsoft.com/dotnet/core/aspnet:2.2-stretch-slim AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/core/sdk:2.2-stretch AS build
WORKDIR /src
COPY ["asonetcoretest/asonetcoretest.csproj", "asonetcoretest/"]
RUN dotnet restore "asonetcoretest/asonetcoretest.csproj"
COPY . .
WORKDIR "/src/asonetcoretest"
RUN dotnet build "asonetcoretest.csproj" -c Release -o /app

FROM build AS publish
RUN dotnet publish "asonetcoretest.csproj" -c Release -o /app

FROM base AS final
WORKDIR /app
COPY --from=publish /app .
ENTRYPOINT ["dotnet", "asonetcoretest.dll"]
