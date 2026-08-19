Mysql example `docker-compose.yaml`:
```
services:
  mysql-db:
    image: mysql:latest
    container_name: mysql_server
    restart: always
    environment:
      MYSQL_ROOT_PASSWORD: deceptiveb
      MYSQL_DATABASE: todoapp
      MYSQL_USER: root
      MYSQL_PASSWORD: deceptiveb
    ports:
      - "3306:3306"
    volumes:
      - mysql_data:/var/lib/mysql

volumes:
  mysql_data:
```

Then run:
```
docker-compose up -d
```

with another name:
```
docker-compose -f my-custom-compose.yml up -d
```
