# Maven-Release仓库

release仓库是用来托管UBSI的核心JAR包以及可部署的基础微服务/工具JAR包，这些JAR包可以通过maven进行引用，各个包的详情请查看：https://github.com/orgs/open-ubsi/packages

在maven的settings.xml中增加本仓库的引用：
```
<servers>
  ......

  <server>
    <id>github</id>
      <username>{your-github-account}</username>
      <password>{your-github-Personal_access_tokens}</password>
      <!-- Personal access tokens需要具备的权限：public_repo | read:packages -->
      <!-- 可以在github.com的个人Settings -> Developer settings -> Personal access tokens页面中创建PAT -->
  </server>
</servers>

<profiles>
  ......

  <profile>
    <id>dev</id>
    <repositories>
      ......
      
      <repository>
        <id>github</id>
        <url>https://maven.pkg.github.com/open-ubsi/release</url>
      </repository>
    </repositories>
  </profile>
</profiles>

<activeProfiles>
  <activeProfile>dev</activeProfile>
</activeProfiles>
```
