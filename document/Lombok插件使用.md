# Lombok插件使用

## 概述

在实际的开发过程中，我们经常需要编写大量的重复的代码，例如构造函数，get/set方法等等，这时候我们可以引入lombok插件，可以很大程度的减少一些重复代码的编写，减轻开发量，使代码更加简单整洁。

下面我们来对lombok的时候来进行一下讲解

## 插件安装

在idea中我们需要进行如下操作：`File` -> `Settings` -> `Plugins`，搜索`Lombok Plugin`

![lombok插件](/document/img/lombok.png)

## jar包添加

```xml
<dependency>
    <groupId>org.projectlombok</groupId>
    <artifactId>lombok</artifactId>
    <optional>true</optional>
</dependency>
```

在对应的项目pom.xml文件中添加如上jar包

通过以上的插件安装以及jar包添加之后，我们就可以正常的使用lombok了

### 解释

lombok是一个基于注解的编译时插件，所以我们需要将IDE的自动编译打开，这是我们就能正常的使用了


## 使用

```java

import lombok.Data;

@Data
public class User {

    private String userName;
}
```

```java
public static void main(String[] args) {
    User user = new User();
    user.setUserName("Jim");
}
```

在以上例子中，我们可以明显的观察到，我们并没有定义User类属性userName的set方法，但是我们在对userName进行set赋值时并没有出错，这个就是Lombok的功劳。

Lombok以注解的方式给我们提供了大量的简化操作，大大的减少我们实际开发的代码量，让我们代码阅读性更强。

## 常用注解

1. `Data` 标注在类上，我们可以不需要对每个字段属性生成get、set方法，同时还包含了对Object类的toString()方法的覆写等，通常我们认为它包含了所有参数的Getter、Setter、ToString三个注解，这样就不需要单独标注三个注解了。

2. `NoArgsConstructor` 标注在类上，无参构造生成

3. `AllArgsConstructor` 标注在类上，全参构造生成

4. `Getter` 标注在属性上，生成该属性的get方法

5. `Setter` 标注在属性上，生成该属性的set方法

6. `ToString` 标注在类上，覆写Object类的toString()方法

7. `Builder` 标注在类上，提供了生成器接口，这样我们在对代码的set操作时仅仅需要通过.属性名的方式进行设置

8. `Log4j`、`Log4j2`、`Slf4j` 标注在类上，这三个注解分别对应了log4j、log4j2、logback三种日志工具类的集成，我们在实际的使用过程中，如下操作

示例

```java
import lombok.extern.slf4j.Slf4j;

@Slf4j
public class UserService{

    public String getUser(String userName) {
        log.info("用户名称为：{}", userName);
        return userName;
    }
}
```

在以上示例中，我们可以看出来，对于日志实例log我们并没有进行初始化，在实际的使用过程中我们仅仅添加了一个注解`@Slf4j`，就可以直接通过log来做日志打印。

这个就是该类日志注解的使用方法，示例中我们使用的时logback，实际过程中其他两种也是一样。