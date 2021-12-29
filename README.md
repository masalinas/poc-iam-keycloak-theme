# Description
PoC Keycloak Custom View Themes

## scaffolding project
We are going to create the keycloak theme scaffolding for a theme called **poc**

The folders structure is:


```shell
themes
  |
  poc
    |
      login
        |    
          resources
            |
              css
                styles.css
        theme.properties
```

## Create the custom theme
From keycloak base theme we are going to creta our base login theme

inside project execute thid command to copy the base theme from  keycloak container

```shell
docker cp keycloak-11:/opt/jboss/keycloak/themes/base/login/login.ftl ./themes/poc/login/login.ftl

```

## Coding
Now we must coding the login view throw the freemaker login.ftl file and add new styles for it and add theme properties to deploy this theme in keycloak.

The final

The folders structure is:

```shell
themes
  |
  poc
    |
      login
        |    
          resources
            |
              css
                styles.css
        theme.properties
        login.ftl    

```

## Deploy keycloak container

```shell
docker-compose up
```

## Configure keycloak with the new theme

Access to master realm

```shell
http://localhost:8080
```

- Create a new reaml called poc.
- Set the new login theme called poc in this new realm.

![PoC Theme Configuration](captures/Realm_Theme_Configure.png "PoC Theme Configuration")

## Access to the new real login

```shell
http://localhost:8080/auth/realms/poc/account
```

![PoC Login View](captures/pop_realm.png "PoC Login View")