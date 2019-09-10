# Spring Boot在idea中使用devtools热部署失败

> 在开发过程中，每一次对类的修改都需要重启服务，浪费时间，影响效率。介绍一种SpringBoot热部署的方法

+ #### 在Maven的pom.xml 文件中添加依赖和插件的配置

  ```xml
   <!--Spring Boot 热部署-->
          <dependency>
              <groupId>org.springframework.boot</groupId>
              <artifactId>spring-boot-devtools</artifactId>
              <optional>true</optional>
          </dependency>
  ```

  ```xml
  			<plugin>
                  <groupId>org.springframework.boot</groupId>
                  <artifactId>spring-boot-maven-plugin</artifactId>
                  <configuration>
                      <fork>true</fork>
                  </configuration>
              </plugin>
  ```

  添加完依赖和配置之后发现，热部署功能实现了，每一次修改，console窗口都会有Spring Boot的重新启动，但是浏览器刷新 结果不变

  #### 原因在于IDEA默认不会自动编译，解决方法有两种：

  1、 手动构建项目，重新编译文件，重启服务

  2、自动：**File**-> **Setting**->**Compiler**->勾选**Build Project automatically**

  **按快捷键Ctrl+Shift+Alt+/，选择1.Registry**

  **勾选 compiler.automake.allow.when.app.running 即可**

  **至此SpringBoot 在IDEA 上的热部署 就完成了**

  

  

  