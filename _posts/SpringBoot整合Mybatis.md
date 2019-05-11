# SpringBoot整合Mybatis

## 参考博客链接：<https://blog.csdn.net/Winter_chen001/article/details/77249029>



#  步骤流程：

### 1.使用IDEA 构建SpringBoot项目

### 2.使用Mybatis-Generation生成mapper接口，实体类，xml配置文件。

### 3.补充：Test测试

需要在接口加入@Mapper

```java

@Mapper
public interface AppTestMapper 

```



### 4.遇到的问题：

### 4.1 运行项目，报关于github的错，直接删除分页依赖...反正暂时没用

```java
<!-- 分页插件 -->
        <!--<dependency>
            <groupId>com.github.pagehelper</groupId>
            <artifactId>pagehelper-spring-boot-starter</artifactId>
            <version>1.1.2</version>
        </dependency>-->
```

#### 4.2 druid版本过低

报错内容：java.lang.ClassNotFoundException: org.springframework.boot.bind.RelaxedDataBinder 

解决：升级版本

```xml
<!-- alibaba的druid数据库连接池 -->
<dependency>
            <groupId>com.alibaba</groupId>
            <artifactId>druid-spring-boot-starter</artifactId>
            <version>1.1.13</version>
        </dependency>
```







