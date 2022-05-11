FROM mcr.microsoft.com/dotnet/framework/sdk:4.8-windowsservercore-ltsc2019 AS build
WORKDIR /app
COPY WcfServiceWebApp/. .
RUN msbuild /p:Configuration=Release

FROM mcr.microsoft.com/dotnet/framework/wcf:4.8-windowsservercore-ltsc2019 AS runtime
WORKDIR /inetpub/wwwroot
COPY --from=build /app/ .
