## Prepare

```bash
mkdir -p ssl public_html
openssl genrsa -out ssl/server.key 2048
openssl req -new -key ssl/server.key -out ssl/server.csr
openssl x509 -req -days 365 -in ssl/server.csr -signkey ssl/server.key -out ssl/server.crt
cat ssl/server.crt ssl/server.key > ssl/server.pem
```

## Usage

```bash
docker-compose up -d
docker-compose exec php bash
```
