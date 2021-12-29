# Description
PoC Keycloak Custom View Themes

## scaffolding project
We are going to create the keycloak theme scaffolded called **poc** from keycloak **base theme**

The folders and files structure must be like this where poc subfolfer it's the custom name for out theme:


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
Now we are going to create the base login template from the base login keycloak theme.
Inside project folder execute this docker command:

```shell
docker cp keycloak-11:/opt/jboss/keycloak/themes/base/login/login.ftl ./themes/poc/login/login.ftl

```

## Coding
Now we must coding the login freemaker template from login.ftl file and add new styles for it and add configure the theme properties to be deployed

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

- Create a new realm called poc.
- Set the new login theme called poc in this new realm.

![PoC Theme Configuration](captures/Realm_Theme_Configure.png "PoC Theme Configuration")

## Access to the new realm login view

```shell
http://localhost:8080/auth/realms/poc/account
```

![PoC Login View](captures/pop_realm.png "PoC Login View")