# Hello GitHub Actions CI + Package Registry + Maven

[![Banner](https://repository-images.githubusercontent.com/215815435/d9c17a72-530a-4566-9b91-9ec9f4b6dd59)](https://github.com/quynhnhu748/HelloMaven.git)

This project is a sample how to deploy a Java Maven artifact with the brand new [GitHub Actions](https://github.com/features/actions) CI to the  [GitHub Package Registry](https://github.com/features/package-registry).  
For now this feature is in beta. To use it, you have to [sign up for the beta](https://github.com/features/package-registry/signup).

> 📦 The package is released [here](https://github.com/quynhnhu748/HelloMaven/packages).

> 📚 You can find more info for Package Registry in the official GitHub doc:  
> [Configuring Apache Maven for use with GitHub Package Registry](https://help.github.com/en/articles/configuring-apache-maven-for-use-with-github-package-registry)

> 🔖 There is also an [Example Project](https://github.com/quynhnhu748/github-plugin-registry-example) which shows how to add this dependency in maven project. 

## 🛠 Add dependency
To include this sample dependency in you project you have to do two things:

 1. Add it as dependency in your `pom.mxl`.

```xml
<dependency>
    <groupId>github.quynhnhu748</groupId>
    <artifactId>hello-maven</artifactId>
    <version>1.2.1</version>
</dependency>
```
```xml
<repositories>
    <repository>
        <id>github</id>
        <name>GitHub TobseF Apache Maven Packages</name>
        <url>https://maven.pkg.github.com/quynhnhu748/HelloMaven</url>
        <releases><enabled>true</enabled></releases>
        <snapshots><enabled>true</enabled></snapshots>
    </repository>
</repositories>
```

 2. Add the authentication to the Package Registry to your global `settings.xml`:  
`USER_HOME\.m2\settings.xml`

``` xml
<servers>
    <server>
        <id>github</id>
        <username>quynhnhu748</username>
        <password>YOUR_AUTH_TOKEN</password>
    </server>
</servers>
```
Replace the `YOUR_AUTH_TOKEN` with a generated GitHub personal access token:  
_GitHub_ > _Settings_ > _Developer Settings_ > _Personal access tokens_ > _Generate new token_:   
The token needs at least the `read:packages` scope.

### Setup your own
If you want to use the Package Registry in your own project, make sure its activated.
Therefore check your project package site:  
https://github.com/YOUR_NAME/YOUR_PROJECT/packages
