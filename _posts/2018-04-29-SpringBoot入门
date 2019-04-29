## 入门SpringBoot

### 环境：

IDEA 2018

JDK 1.8

SpringBoot 2.1.0.RELEASE

Maven 3.6

### 1.打成jar包 没有将webapp文件夹打包到MATA-INF

需要配置maven

```xml
<build>
     <!--<resources>-->
            <!--&lt;!&ndash; 打包时将jsp文件拷贝到META-INF目录下&ndash;&gt;-->
            <!--<resource>-->
                <!--&lt;!&ndash; 指定resources插件处理哪个目录下的资源文件 &ndash;&gt;-->
                <!--<directory>src/main/webapp</directory>-->
                <!--&lt;!&ndash;注意此次必须要放在此目录下才能被访问到&ndash;&gt;-->
                <!--<targetPath>META-INF/resources</targetPath>-->
                <!--<includes>-->
                    <!--<include>**/**</include>-->
                <!--</includes>-->

            <!--</resource>-->
            <!--<resource>-->
                <!--<directory>src/main/resources</directory>-->
                <!--<includes>-->
                    <!--<include>**/**</include>-->
                <!--</includes>-->
                <!--<filtering>false</filtering>-->
            <!--</resource>-->
        <!--</resources>-->
</build>   
```



### 2.打包时多了一个BOOT-INF

```xml
<plugins>
  <plugin>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-maven-plugin</artifactId>
    <configuration>
      <skip>true</skip>
    </configuration>
  </plugin>
</plugins>
```



### 3.解决1.2.的问题直接达成war包，也可以用java -jar 启动项目 /丢到tomcat下也可以

上面1、2的问题，如果按照解决方法处理，得到jar包，也会缺少主程序，Main-Class，可以手动配置。

或者说直接达成war包，是最简便的处理方法。无需在pom文件上做修改。

### 4.IDEA 设置properties文件编码 ，设置成utf-8，后边的√上

properties的编码有单独的编码选项，需要在setting中搜索file encoding，把properties编码设置成uft-8，后边的√也要打上。如果还是乱码，可以删除掉做此设置之前的properties文件，再创建一遍。

### 5.@ConfigurationPropertieshe 和@Value的对比

|            | ConfigurationProperties(prefix = "person") | @Value               |
| ---------- | ---------------------------------------- | -------------------- |
|            | 批量注入配置文件中的属性值                            | 一个个在属性值上加入@Value进行注入 |
|            | 支持松散语法lastName相当于last-name相当于LAST-NAME或者last_name | 不支持松散语法              |
| SPEL       | 不支持                                      | 支持@Value("#{2*12}")  |
| JSR303数据校验 | 支持 属性头上加@Email等校验规则进行校验                  | 不支持                  |
| 复杂类型封装     | 支持，例如Map<String,Object>类型                | 不支持                  |

**.yml和.properties都适用**

### 6.配置文件占位符

#### 6.1随机数：

${random.int}

${random.uuid}

#### 6.2引用属性值

person.name=陈亮

person.dog.name=${person.name}的狗狗

### 6.3提供默认值

如果被引用的属性不存在，提供默认值，则获取默认值

如果不提供默认值，则把占位符原样赋给属性

写法：person.dog.name=${person.name:"伟酱"}的狗狗 (person.name不在配置文件中)

结果：person.dog.name=伟酱的狗狗

写法：person.dog.name=${person.name}的狗狗 (没提供默认值)

结果：person.dog.name=${person.name}的狗狗(原样赋值给person.dog.name)

```yml
#person.last-name=陈亮,id为：${random.uuid}
person.age=${random.int}
person.boss=false
person.dog.name=${person.last-name:陈亮的狗狗}
person.dog.age=2
```

### 7.Profile

#### 7.1 多个properties配置文件

​	默认使用application.properties,如果要使用其他配置文件，在application.properties中激活，

激活方式：spring.profiles.active=dev

其余配置文件

application-dev.properties

application-prod.properties

### 7.2yml 多文档块模式

用---来分割文档块

```yml
server:
  port: 8080

spring:
  profiles:
    active: dev #激活配置文档块，如果不设置激活值 则默认使用该文档块的配置
---
server:
  port: 8081
spring:
  profiles: dev
---
server:
  port: 8082
spring:
  profiles: prod
```

### 8.SpringBoot跳到jsp的配置

<https://blog.csdn.net/shawearn1027/article/details/54881680>









