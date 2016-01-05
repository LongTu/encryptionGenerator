# encryptionGenerator

This is a helper project to let frontend code connect to backend influxdb databse.
By default, this service is bind to port 18080

follow the instructions here to install go on your environment:
https://golang.org/doc/install



build all go file in encryptionGenerator project
```
go install encryptionGenerator/
```

If you have a username and password to encrypt.

```
go run influxdbUrl/encryptionGenerator.go ${YOUR_USERNAME}
go run influxdbUrl/encryptionGenerator.go ${YOUR_PASSWORD}
go run influxdbUrl/encryptionGenerator.go ${YOUR_URL_TO_DATABASE}
go run influxdbUrl/encryptionGenerator.go ${YOUR_DATABASE_NAME}
```
This will generate a encryted version of your username, password, databseUrl and databaseName

The database url should contain all sub directories. Some sample YOUR_URL_TO_DATABASE
```
http://localhost:8086/query
http://paas.sym.com/db/k8s/series
```

Copy and paste the result generated from the above program to credential.config, in the following format:
```
u=${YOUR_ENCRYPTED_USERNAME}
p=${YOUR_ENCRYPTED_PASSWORD}
l=${YOUR_ENCRYPTED_URL}
d=${YOUR_ENCRYPTED_DATABASE_NAME}
```

After the above config, the last step is to change the file permmision of credential.config to read only
```
chmod 444 credential.config
```