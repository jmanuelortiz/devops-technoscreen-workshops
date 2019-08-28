FROM microsoft/iis:10.0.14393.206​

SHELL ["powershell"]​​

RUN Install-WindowsFeature NET-Framework-45-ASPNET; \
    Install-WindowsFeature Web-Asp-Net45​

COPY GuidGenerator GuidGenerator​

RUN Remove-WebSite -Name 'Default Web Site'

EXPOSE 80​

CMD ["ping", "-t", "localhost"]​