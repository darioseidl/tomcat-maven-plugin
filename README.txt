Fork of tomcat-maven-plugin with fix for https://issues.apache.org/jira/browse/MTOMCAT-264 (uriEncoding parameter not working with https).

Hosted on 

# Usage

Add jitpack as a repository and plugin respository in your maven `pom.xml`.

```
    <repositories>
        <repository>
            <id>jitpack.io</id>
            <url>https://jitpack.io</url>
        </repository>
    </repositories>

    <pluginRepositories>
        <pluginRepository>
            <id>jitpack.io</id>
            <url>http://jitpack.io</url>
        </pluginRepository>
    </pluginRepositories>
```

Use the plugin just like the upstream version, except now the uriEncoding parameter is working even with https. 

```
<build>
        <plugins>
            <plugin>
                <groupId>com.github.darioseidl.tomcat-maven-plugin</groupId>
                <artifactId>tomcat7-maven-plugin</artifactId>
                <version>2.2.2</version>

                <configuration>
                    <path>/</path>
                    <httpsPort>8443</httpsPort>
                    <keystoreFile>${keystore}</keystoreFile>
                    <keystorePass>${password}</keystorePass>
                    <tomcatUsers>${basedir}/src/main/resources/tomcat-users.xml</tomcatUsers>
                    <uriEncoding>UTF-8</uriEncoding>
                </configuration>
            </plugin>
        </plugins>
</build>
```
