# SpringBoot工程快速创建

## 概述

由于SpringBoot的畅行，Spring官方推出了SpringBoot工程创建插件，方便开发者对项目进行创建以及整合，本文将以idea为例。

## 插件安装

`File` -> `Settings` -> `Plugins`，搜索`Spring Boot`，如果没有该插件请搜索`Spring Assistant`

![idea插件](/document/img/idea-plugin.png)

## 项目创建

`File` -> `New` -> `Project` -> `Spring Initializr`或者`Spring Assistant`

![Spring Boot插件](/document/img/springboot.png)

以上为Spring Boot插件效果

![Spring Assistant插件](/document/img/assistant.png)

以上为Spring Assistant插件效果

在经过项目基础属性的配置之后，我们可以看到如下页面，这个页面对Spring官方提供的各种功能等进行了整合，我们需要依赖的仅仅需要做一个勾选，在项目创建之后会自动将所有依赖进行整合。

![new Project](/document/img/dependencies.png)

在经过一系列得`Next`和`Finish`之后，我们会发现项目自动创建完毕，非常的简单方便，主要重点在插件上，Eclipse安装对应插件请参考官网

### 注意

新的插件更名为Spring Assistant，老版本的Spring Boot依然可用。

### 对比

对比以上我们发现Spring Assistant插件其实就是Spring Boot升级版本，之前的Spring Boot插件已经被该插件所替换，Assistant插件不仅仅提供了Boot插件的功能，还提供了Spring Cloud Data Flow的创建。
