FROM microsoft/dotnet-framework:3.5-runtime-windowsservercore-1803
SHELL ["powershell", "-Command"]
ARG Office=""
USER "NT AUTHORITY\\SYSTEM"

RUN Set-ExecutionPolicy Bypass -Scope Process -Force; \
    iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))

RUN choco install dotnet4.7 -fy
RUN choco install vcredist-all -fy
RUN switch($env:Office) { \
    "32-bit" {choco install office365proplus -fy --forcex86} \
    "64-bit" {choco install office365proplus -fy} \
    default  {Write-Host "No Office"} \
}\