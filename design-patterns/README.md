# design-patterns
Design patterns are the best formalized practices a programmer can use to solve common problems when designing an application or system.

Design patterns can speed up the development process by providing tested, proven development paradigms.

Reusing design patterns help prevent subtle issues which cause major problems, and it also improves code readability for coders and architects who are familiar with the patterns.
https://github.com/iluwatar/java-design-patterns



| layout  | title             | folder            | categories | tags          |
| ------- | ----------------- | ----------------- | ---------- | ------------- |
| pattern | Abstract Document | abstract_document | Structural | Extensibility |
| pattern | Abstract Factory  | abstract_factory  | Creational | Gang of Four  |
|         |                   |                   |            |               |



## abstract_document

The Abstract Document pattern enables handling additional, non-static  properties. This pattern uses concept of traits to enable type safety and  separate properties of different classes into set of interfaces.  In Abstract Document pattern, fully implements  interface. Traits are then defined to enable access to properties in usual, static way. 

- 主要是处理额外的非静态的属性,将他们放入Map<String,Object> 来进行存储
- 用到了Java8的新特性,Stream和Optional来保证数据读取时类型的一致性和稳定性(类似于泛型,和非空检查)
- Kotlin很好的解决了后者的检查问题,但是编写起来还是需要理解哪里可以为null哪里不行

此模式的目的是提供强类型语言中实现组件之间的高度灵活性，使新的属性可以在对象树上快速添加，而不会失去类型安全的支持。