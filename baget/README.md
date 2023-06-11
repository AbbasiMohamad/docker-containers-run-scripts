# RUN Command
```
docker run --rm -d --name nuget-server -p 5555:80 --env-file baget.env -v "$(pwd)/baget-data:/var/baget" loicsharma/baget:latest
```

# Sample Configuration with Proxy
```
ApiKey=NUGET-SERVER-API-KEY

Storage__Type=FileSystem
Storage__Path=/var/baget/packages
Database__Type=Sqlite
Database__ConnectionString=Data Source=/var/baget/baget.db
Search__Type=Database
Mirror__Enabled=true
Mirror__PackageSource=https://api.nuget.org/v3/index.json
AllowPackageOverwrites=true
```
