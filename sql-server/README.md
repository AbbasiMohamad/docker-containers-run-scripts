## run command

```console
docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=YourPassword' \
        -p 1433:1433  \
        -v <host directory>/data:/var/opt/mssql/data \
        -v <host directory>/log:/var/opt/mssql/log -v \ 
        <host directory>/secrets:/var/opt/mssql/secrets \
        --name sqlserver \
        --restart=always -d \
        mcr.microsoft.com/mssql/server:2022-latest
```

## example

```console
docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=@WSXbgt5*IK<%^&*uytF' \
		-p 1833:1433 \
		-v /containers/sql-server/volumes/data:/var/opt/mssql/data \
		-v /containers/sql-server/volumes/log:/var/opt/mssql/log -v \
		/containers/sql-server/volumes/secrets:/var/opt/mssql/secrets \
		--name sqlserver \
		--restart=always -d \
		mcr.microsoft.com/mssql/server:2022-latest
```
