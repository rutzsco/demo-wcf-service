FROM mcr.microsoft.com/dotnet/framework/sdk:4.8-windowsservercore-ltsc2022 AS build
WORKDIR /app
COPY WcfServiceWebApp/. .
RUN msbuild /p:Configuration=Release

FROM mcr.microsoft.com/dotnet/framework/wcf:4.8-windowsservercore-ltsc2022 AS runtime
WORKDIR /inetpub/wwwroot
COPY --from=build /app/ .
