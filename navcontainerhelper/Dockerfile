# escape=`
ARG BASE
FROM mcr.microsoft.com/windows/servercore:$BASE
ARG NCHVERSION
SHELL ["powershell", "-Command", "$ErrorActionPreference = 'Stop';"]

RUN Install-PackageProvider -Name NuGet -MinimumVersion 2.8.5.201 -Force; `
    Install-Module navcontainerhelper -MinimumVersion $env:NCHVERSION -MaximumVersion $env:NCHVERSION -Force;