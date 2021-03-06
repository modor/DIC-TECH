### 单元测试

---

* 要求

```
一致性(Conformance)            值是否符合预期格式。 
有序性（Ordering)              一组值应该是有序的还是无序的。 
区间性（Range)                 参数的取值范围是否在某个合理的区间范围内。 
引用/耦合性（Rerference)       代码是否引用了一些 不受代码本身直接控制的外部因素。 
存在性(Existence)              参数是否真的存在，引用为null,string为空，数值为0或者物理介质不存在时，程序是否能正常运行。 
基数性(Cardinality)            是否恰好有足够的值。 
时间性(Time)                   所有事情是否都是按顺序反生的？是否在正确的时间，是否及时。
```

* 测试任务

```
1.接口功能测试：用来保证接口功能的正确性.
2.局部数据结构测试（不常用）：用来保证接口中的数据结构是正确的.
    1)比如变量有无初始值
    2)变量是否溢出
3.边界条件测试
    1)变量没有赋值（即为NULL）
    2)变量是数值（或字符)
        主要边界：最小值，最大值，无穷大（对于DOUBLE等）;
        溢出边界（期望异常或拒绝服务）：最小值-1，最大值+1;
        临近边界：最小值+1，最大值-1;
    3)变量是字符串
        引用“字符变量”的边界;
        空字符串;
        对字符串长度应用“数值变量”的边界;
    4)变量是集合
        空集合;
        对集合的大小应用“数值变量”的边界;
        调整次序：升序、降序;
    5)变量有规律,比如对于Math.sqrt，给出n^2-1，和n^2+1的边界.
4.所有独立执行通路测试：保证每一条代码，每个分支都经过测试.
    1)代码覆盖率
        语句覆盖：保证每一个语句都执行到了
        判定覆盖（分支覆盖）：保证每一个分支都执行到
        条件覆盖：保证每一个条件都覆盖到true和false（即if、while中的条件语句）
        路径覆盖：保证每一个路径都覆盖到
    2)相关软件
        Cobertura：语句覆盖
        Emma: Eclipse插件Eclemma
5.各条错误处理通路测试：保证每一个异常都经过测试
```

---

### 设计模式

---

* 按封装变化分类

```
1.组件协作
    Template Method
    Strategy
    Observer/Event
2.单一职责
    Decorator
    Bridge
3.对象创建
    Factory Method
    Abstract Factory
    Prototype
    Builder
4.对象性能
    Singleton
    Flyweight
5.接口隔离
    Facade
    Proxy
    Mediator
    Adapter
6.状态变化
    Memento
    State
7.数据结构
    Composite
    Iterator
    Chain of Resposibility
8.行为变化
    Command
    Visitor
9.领域问题
    Interpreter
```

* 按作用分类

```
1.创建型模式
    Factory Method
    Abstract Factory
    Singleton
    Builder
    Prototype
2.结构型模式
    Adapter
    Decorator
    Proxy
    Facade
    Bridge
    Composite
    Flyweight
3.行为模式
    Strategy
    Template Method
    Observer/Event
    Iterator
    Chain of Resposibility
    Command
    Memento
    State
    Mediator
    Interpreter
    Visitor
4.其他
    并发型模型
    线程池模型
```

---



