# Hello World Rest API

### Running the Application

Run ccom.yfsol.app.helloworld.SpringYfsolAppHelloworldApplication as a Java Application or Spring Boot App.

- http://localhost:8080
- http://localhost:8080/hello-world


```txt
Hello World
```

- http://localhost:8080/hello-world-bean

```json
{"message":"Hello World"}
```

- http://localhost:8080/hello-world/path-variable/yfsol

```json
{"message":"Hello World, yfsol"}
```

### Plugin configuration

```
<plugin>
	<groupId>com.microsoft.azure</groupId>
	<artifactId>azure-webapp-maven-plugin</artifactId>
	<version>2.5.0</version>
</plugin>
```
				
### Azure CLI

- https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest

### Final Plugin Configuration
```
<plugin>
    <groupId>com.microsoft.azure</groupId>
    <artifactId>azure-webapp-maven-plugin</artifactId>
    <version>2.5.0</version>
    <configuration>
        <schemaVersion>V2</schemaVersion>
        <resourceGroup>hello-world-rest-api-v2-rg</resourceGroup>
        <appName>yfsol-service-helloworld</appName>
        <pricingTier>B1</pricingTier>
        <region>centralus</region>
        <appSettings>
            <property>
                <name>JAVA_OPTS</name>
                <value>-Dserver.port=80</value>
            </property>
        </appSettings>
        <runtime>
            <os>linux</os>
            <javaVersion>java11</javaVersion>
            <webContainer>java11</webContainer>
        </runtime>
        <deploymentSlot>
            <name>stage</name>
            <configurationSource>parent</configurationSource>                   
        </deploymentSlot>
        <deployment>
            <resources>
                <resource>
                    <directory>${project.basedir}/target</directory>
                    <includes>
                        <include>*.jar</include>
                    </includes>
                </resource>
            </resources>
        </deployment>
    </configuration>
</plugin>

```
### Logging Configuration

```
-Dlogging.level.org.springframework=DEBUG
```

### Installing curl and watch on windows
```
https://curl.haxx.se/windows/
```

### Installing watch on MAC
```
http://osxdaily.com/2010/08/22/install-watch-command-on-os-x/
```
