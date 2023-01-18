## prerequisite to HTTPS

1.  `.pfx` file (certification file)

Generate a certificate and configure the local machine:

### Windows using Linux containers

```plaintext
dotnet dev-certs https -ep %USERPROFILE%\\.aspnet\\https\\aspnetapp.pfx -p \<CREDENTIAL\_PLACEHOLDER>  
dotnet dev-certs https --trust
```

### macOS or Linux

```plaintext
dotnet dev-certs https -ep ${HOME}/.aspnet/https/aspnetapp.pfx -p \<CREDENTIAL\_PLACEHOLDER>  
dotnet dev-certs https --trust
```

## run command

```plaintext
docker run \
        -p 8000:80 -p 8001:443 \
        -e ASPNETCORE_URLS="https://+;http://+" \
        -e ASPNETCORE_HTTPS_PORT=8001 \
        -e ASPNETCORE_Kestrel__Certificates__Default__Password="<CREDENTIAL_PLACEHOLDER>" \
        -e ASPNETCORE_Kestrel__Certificates__Default__Path=/https/aspnetapp.pfx \
        -v ${HOME}/.aspnet/https:/https/ \
        --restart=always -d \
        mcr.microsoft.com/dotnet/samples:aspnetapp
```