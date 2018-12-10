# SpringAOPTree
面向切面编程技术研究


传统：

![](https://i.imgur.com/w8Jjp8u.png)
       
修改版：

![](https://i.imgur.com/A5MqHaG.png)


<pre>
Aop原理:

       AspectJ是一个基于Java语言的AOP框架，提供了强大的AOP功能，其他很多AOP框架都借鉴或
   采纳了其中的一些思想。

       与AspectJ相同的是，Spring AOP 同样需要对目标类进行增强，也就是生成新的AOP代理类；
   与AspectJ不同的是，Spring AOP无需使用特和特殊命令对Java源代码进行编译，它采用的是运
   行时动态的，在内存中零时生成“代理类”的方式来生成AOP代理。

       Spring允许使用AspectJ Annotation用于应以方面Aspect, 切入点Pointcut， 增强处理
   Advice，Spring框架可以识别并根据这些注解来生成AOP代理。

   当使用@Aspect来修饰一个Java类之后，Spring将不会把该Bean当做组件Bean处理，因此负责自动
   增强的后处理Bean将会被略过，不会对该Bean进行任何增强处理。   

   增强处理：
           AfterReturning,
           Around,
           Before,
           After,
           AfterThrowing 
</pre>


![](https://i.imgur.com/9lTu85C.png)

<pre>
Aop代理的方法和目标方法


      Spring的AOP代理由Spring的IOC容器负责生成，管理，其依赖关系也由IOC容器负责管理，因
    此，AOP代理类可以直接使用容器中的其他Bean实例作为目标。


    代理对象的方法  =  增强处理   + 被代理对象的方法

    Spring AOP的实现原理其实很简单：
           AOP框架负责动态的生成AOP代理类，这个代理类的方法则由 Advice和回调目标对象的方法组成。


    AOP广泛应用于处理一些具有横切性质的系统级服务，AOP的出现是对OOP的良好补充，它是的开发
    者能用更优雅的方式处理具有切面性质的服务。不管是哪种AOP实现，不论是AspectJ，还是
    Spring AOP,他们都需要生成一个AOP代理类，区别只是生成AOP代理类的机制不同：
        AspectJ采用编译时生成AOP代理类，因此具有更好的性能，但需要使用特定的编译器处理。
        Spring Aop则采用运行时生成AOP代理类，因此无需使用特定编译器进行处理，由于Spring
    Aop需要在每次运行时生成AOP代理，因此性能略差一些。
</pre>