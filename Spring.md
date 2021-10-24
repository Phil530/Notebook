# IOC容器

## 什么是IOC
1. 控制反转，把对象创建和对象之间的调用过程，交给Spring进行管理
2. 使用IOC的目的：为了耦合度降低
3. 做入门案例就是IOC实现

## IOC底层原理
- xml解析、工厂模式、反射

## IOC底层原理
**IOC工程**
第一步：

``` <!--xml配置文件，配置创建的对象-->
<!--id属性是标识单个 bean 定义的字符串。
class属性定义 bean 的类型并使用完全限定的类名。-->
<bean id="user" class="com.phil.spring.User"></bean>
```
第二步：有service类和dao类，创建工厂类

``` class UserFactory{
    public static UserDao getDao(){
        String classValue = class属性值;//1、xml解析
        
        Class clazz = Class.forName(classValue);//2、通过反射建对象
        return (UserDao)clazz.newInstance();
    }
}
```
**IOC（ BeanFactory 接口）**  
- IOC思想基于IOC容器完成，IOC容器底层就是对象工厂
	- BeanFactory ：IOC容器基本实现，是Spring内部的使用接口，不提供开发人员使用
		**加载配置文件时不会创建对象，在获取对象（使用）才去创建对象**
	- ApplicationContext： BeanFactory 接口的子接口，提供更多更强大的功能，一般由开发人员进行使用
	  **加载配置文件时就会把在配置文件对象进行创建**
	- ApplicationContext接口有实现类

