# 1. 自动配置



### 1. 观察自动配置的判断结果

​	在proeject param    —debug

那么在启动项目时， ConditionEvaluationReportLoggingListener  会对自动配置的匹配情况进行输出 ，

- Positive matches

- Negative matches

- Exclusions

- Unconditional classes

  

### 2.自动配置的原理

​	基于JavaConfig  

条件注解  

- ​	@Conditional 

​     类条件 

- ​		@ConditionalOnClass
- ​		@ConditionalOnMissingClass

​     属性条件

- ​		 @ConditionalOnProperty

​     Bean条件

- ​                @ConditionalOnBean
- ​		@ConditionalOnMissingBean
- ​		@ConditionalOnSingleCadidate  在上下文中只存在一个候选的Bean

   资源条件

- ​		@ConditionalOnResouce

  Web应用条件

- ​		@ConditionalOnWebApplication	
- ​		@ConditionaOnNotlWebApplication

 其他条件

- ​		@ConditionalOnExpression
- ​		@ConditionalOnJava
- ​		@ConditionalOnJndi

# 2.起步依赖

​	SpringBoot 使用了starter 起步依赖， 对各个模块进行的统一的依赖管理。

​	基于maven的依赖管理

- 面向功能  比如spring-boot-starter-web    spring-boot-starter-jdbc
- 一站式获取依赖    starter 内部使用dependencyManagement 进行管理

# 3.配置加载



##### 外化配置加载顺序

- 开启dev-tools， ~/.spring-boot-devtools.properties 
- 测试类上的@TestPropertySource注解
- @SpringBootTest#propterties属性
- 命令行参数（--server.port=9000）
- SPRING_APPLICATION_JSON中的属性
- ServletConfig初始化参数
- ServletContext初始化参数
- Java:comp/env 中的JNDI属性
- System.getProperties
- 操作系统环境变量
- Random.*涉及到的RandomValuePropertySource
- jar包外部的application-{profile}.properties    或 yml
- jar包内部的application-{profile}.properties    或 yml
- jar包外部的application.properties    或 yml
- jar包内部的application.properties    或 yml
- @Configuration类上的@PropertySource
- SpringApplication.setDefaultProperties()设置的默认属性





##### application.properties

默认位置

- ./config
- ./
- CLASSPATH中的/config
- CLASSPATH中的/
- 

##### 也可以修改配置文件的名字或路径

- spring.config.name
- spring.config.location
- spring.config.additional-location



# 4. PropertySource抽象

- 可以将属性绑定到结构化对象上
- 支持relaxed binding
- 支持安全的类型转换
- @EnableConfigurationProperties

# 5.Actuator

监控并管理应用程序

访问方式

- HTTP
- JMX



​      