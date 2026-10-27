
# Maven installation and commands:

## Installatiosn


---

## commads


### run application from CLI:

```cmd
mvnw spring-boot:run
```


### creating a target folder:

```cmd
mvn clean install
```


### xdebug settigns: 

```cmd
vmadmin@winvm C:\VS Code Java\springbootdebug
#
mvn spring-boot:run -Drun.jvmArguments="-Xdebug -Xrunjdwp:transport=dt_socket,server=y,suspend=n,address=8001"
```
<img width="1061" height="540" alt="image" src="https://github.com/user-attachments/assets/21810c61-da76-421f-b6b9-ace14caab164" />


Add breakpoint and run the application



Note: port should be open at remote host then only debugging will work.


### 
