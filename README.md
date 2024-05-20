## How the project works

1. This project takes the latest docker image of IIS server `FROM mcr.microsoft.com/windows/servercore/iis`.
2. Then we spinn up the docker container and download/instal .NET 8 hosting bunddle (includes .NET and ASP.NET runtimes).
3. Then we're copying the binaries of the Blazor App to the IIS `WORKDIR`.
4. In the end we're capturing the image.

## How to build the project
```pwsh
cd BlazorApp;
dotnet publish;
docker build -t iis-site .;
docker run -d -p 8000:80 --name my-running-site iis-site;
```
