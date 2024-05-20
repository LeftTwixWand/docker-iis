FROM mcr.microsoft.com/windows/servercore/iis

# Download and install the .NET Core Hosting Bundle
ADD https://download.visualstudio.microsoft.com/download/pr/70f96ebd-54ce-4bb2-a90f-2fbfc8fd90c0/aa542f2f158cc6c9e63b4287e4618f0a/dotnet-hosting-8.0.5-win.exe C:/dotnet-hosting/
RUN C:/dotnet-hosting/dotnet-hosting-8.0.5-win.exe /install /quiet /norestart
RUN rmdir /s /q C:\dotnet-hosting

RUN powershell -NoProfile -Command Remove-Item -Recurse C:\inetpub\wwwroot\*

WORKDIR /inetpub/wwwroot

COPY bin/Release/net8.0/publish/ .