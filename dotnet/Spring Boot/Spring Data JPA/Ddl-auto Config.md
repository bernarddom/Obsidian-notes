```
spring.jpa.hibernate.ddl-auto=none
spring.jpa.hibernate.ddl-auto=validate
spring.jpa.hibernate.ddl-auto=update
spring.jpa.hibernate.ddl-auto=create
spring.jpa.hibernate.ddl-auto=create-drop
```

### create
Erase all the data and recreate it every time the application starts.
### validate
Checks if the database schema matches your entity classes. Fails if there is a mismatch. 
### update
Updates the database schema to match your entity classes.
### none
Disables all automatic schema generation
### create-drop
Create the schema on startup and drops it completely when the application shuts down
