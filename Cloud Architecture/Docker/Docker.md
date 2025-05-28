docker run -e "ACCEPT_EULA=Y" -e "MSSQL_SA_PASSWORD=123456" \
-p 1433:1433 --name sqlserver_container -d [mcr.microsoft.com/mssql/server:latest](http://mcr.microsoft.com/mssql/server:latest)

- **帳號**：`sa`
- **密碼**：123456

docker run -e "ACCEPT_EULA=Y" -e "MSSQL_SA_PASSWORD=SecureP@ssw0rd123" \
-p 1433:1433 --name sqlserver_container5 -d [mcr.microsoft.com/mssql/server:latest](http://mcr.microsoft.com/mssql/server:2019-latest)