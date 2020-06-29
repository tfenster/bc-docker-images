# escape=`
ARG BASE
ARG NCHVERSION
FROM tobiasfenster/navcontainerhelper:$NCHVERSION-$BASE

ARG TYPE
ARG COUNTRY
ARG VERSION
SHELL ["powershell", "-Command", "$ErrorActionPreference = 'Stop';"]

RUN Import-Module navcontainerhelper; `
    Download-Artifacts -artifactUrl (Get-BCArtifactUrl -type $env:TYPE -country $env:COUNTRY -version $env:VERSION) -includePlatform;
RUN Copy-Item "C:\bcartifacts.cache\$env:TYPE\$env:VERSION\platform\ModernDev\program` files\Microsoft` Dynamics` NAV\*\AL` Development` Environment\ALLanguage.vsix" "C:\bcartifacts.cache\$env:TYPE\$env:VERSION\ALLanguage.zip"; `
    Copy-Item "C:\bcartifacts.cache\$env:TYPE\$env:VERSION\platform\ModernDev\program` files\Microsoft` Dynamics` NAV\*\AL` Development` Environment\System.app" "C:\bcartifacts.cache\$env:TYPE\$env:VERSION\$env:COUNTRY\Applications.$env:COUNTRY"; `
    Expand-Archive "C:\bcartifacts.cache\$env:TYPE\$env:VERSION\ALLanguage.zip" "C:\bcartifacts.cache\$env:TYPE\$env:VERSION\ALLanguage"; 