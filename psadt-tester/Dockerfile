# escape=`
FROM microsoft/dotnet-framework:3.5-runtime-windowsservercore-1803

SHELL ["powershell", "-Command"]

RUN Set-ExecutionPolicy Bypass -Scope Process -Force; `
    iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))

RUN choco install dotnet4.7.2 -y
RUN choco install vcredist-all -y
RUN choco install office365proplus -y