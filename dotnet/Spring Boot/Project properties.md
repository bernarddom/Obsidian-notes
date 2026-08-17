`application.properties`
```
spring.application.name=workie  
spring.profiles.active=${ACTIVE_PROFILE:dev}  
spring.datasource.url=jdbc:postgresql://${POSTGRES_HOST}:${POSTGRES_PORT}/${POSTGRES_DATABASE}  
spring.datasource.username=${POSTGRES_USERNAME}  
spring.datasource.password=${POSTGRES_PASSWORD}  
spring.datasource.driver-class-name=org.postgresql.Driver  
  
  
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.PostgreSQLDialect  
  
spring.jpa.hibernate.ddl-auto=create-drop  
#spring.jpa.hibernate.ddl-auto=create  
#spring.jpa.hibernate.ddl-auto=create-drop  
#spring.jpa.hibernate.ddl-auto=validate  
spring.datasource.initialization-mode=always
```

Now we do a file for every environment:
`application-dev.yaml`:
```
ACTIVE_PROFILE: dev  
  
PRIVATE_KEY: 'private.key'  
PUBLIC_KEY: 'public.key'  
  
POSTGRES_USERNAME: 'deceptiveb'  
POSTGRES_DATABASE: 'ticket_system'  
POSTGRES_HOST: 'localhost'  
POSTGRES_PORT: 5432  
POSTGRES_PASSWORD: 'deceptiveb'  
  
SERVER_PORT: 8080  
UI_APP_URL: http://localhost:5173
```