# bingo-bean
*对象拷贝，目标是比dozer更快，功能更强大，更完整的支持泛型*
## 1、该项目是复制对象的工具，创建目的是：
    a)、比Dozer、FastJson更快，占用内存更小
    b)、不同类型间的复制，包括对自定义泛型的深层识别，参见com.bingo.bean.domain.ParameterizedFromBean
## 2、使用规则：
    a)、拷贝的对象，必须要有无参构造方法
    b)、拷贝的对象，必须对属性提供public的访问方法
    c)、@Expressions支持不同名称见的映射，通过该注解，可以在自定义的方法中实现类型的转换，比如目标对象有个属性是Date,需要映射原对象中的类型为String，可以在原属性的get方法或者目标属性的set方法中做类型的转换，由此来解决该框架支持不了的映射转换
    d)、最低支持1.8版本
## 3、限制：
    a)、对于类型相同（映射的Type Equals），不做创建，直接给目标付原值
    b)、继承自Collection的自定义类，不支持属性映射，只做了Collection的转换
    c)、对Map还没做支持
## 4、待解决问题：
    a)、嵌套循环引用死锁问题
    b)、多线程下，嵌套引用可能引起死锁（暂时采用再次生成Expression，以后解决）
    c)、嵌套引用，泛型确认阶段会死循环，例子class A<T>{ A<T> a;}
**如有问题，可发邮件到742237305@qq.com。**   

**项目中可能存在未知BUG，因该项目引起的问题，作者概不负责。**  

**欢迎大家对该项目做出评价。(原谅项目代码没注释)**
