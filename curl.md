# Curl Commands

```bash
curl --form "file=@/Users/pujan/filename.txt" -F file=@2.jpg  http://host/api/

curl -X GET http://localhost/api

curl -X POST -F files=@/Users/pujan/1.png -F files=@/Users/pujan/2.png http://host/api/upload -v

curl -X POST -d 'job={"imageurl":["http://localhost/2.tiff"], "jobtype":"new"}' http://localhost/a/api/job/insert

curl -X POST -H "Accept:application/json" -H "Content-Type: application/json" -d '{"method":"ping", "client": {"version":"1.0", "platform":"fibble/1.0"}, "id":"id-01"}' "http://54.191.112.207:8080/ial/remote/jsonrpc"

curl -H "Content-Type: application/json" -X PUT -d '{"name":"Pujan S.","gender":"M"}' http://host/api/

curl --head --compressed quora.com
```

## Basic Authentication

```shell script
curl -H "Authorization: OAuth 2c4419d1aabeec" http://host/api/
```
