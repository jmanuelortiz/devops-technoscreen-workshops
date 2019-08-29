FROM microsoft/iis

SHELL ["powershell"]​​

RUN Install-WindowsFeature NET-Framework-45-ASPNET; \
    Install-WindowsFeature Web-Asp-Net45​

COPY GuidGenerator GuidGenerator​

RUN Remove-WebSite -Name 'Default Web Site'

EXPOSE 80​

CMD ["ping", "-t", "localhost"]​