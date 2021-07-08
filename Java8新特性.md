# 基础知识

## 一、java8新特性

### 1.1  Lambda表达式*

### 1.2 函数式接口

值包含一个抽象方法的接口为函数式接口，lambda表达式在此接口中可作为参数传递。其中，@FunctionalInterface 注解检查是否为函数式接口

四大核心函数式接口

函数式接口         类型    返回类型        用途

Consumer<T>      消费型    void     对类型为T的对象进行操作，包含方法：void accept(T t)

Supplier<T>      供给型     T        返回类型为T的对象， 包含方法：T get()

Function<T, R>   函数型     R        对类型为T的对象进行操作，并返回结果R，包含方法 R apply(T t)

Predicate<T>      断言型   boolean   确定类型为T的对象是否满足某约束，并返回boolean值

### 1.3 方法引用与构造器引用

#### 1.3.1 方法引用

即"::"符号

分三种用法:1、对象 :: 实例方法；2、类 :: 静态方法；3、类 :: 实例方法。

#### 1.3.2 构造器引用

格式：ClassName :: new

与函数式接口相结合，自动与函数式接口中方法兼容。可以把构造器引用赋值给定义的方法，与构造器参数列表要与接口中的抽象方法的参数列表一致

### 1.4 Stream API*

定义：用于操作数据源（集合、数组）所产生的元素序列

Java8中处理集合的关键抽象概念，可以指定希望对集合进行的操作，可以执行非常复杂的查找、过滤映射数据等操作。使用Stream API对集合数据进行操作，就类似于使用SQL执行的数据库查询。也可以使用Stream API来并行执行操作。

特点：

1.Stream 自己不会存储元素。
2.Stream 不会改变源对象。相反，他们会返回一个持有结果的新的Stream。

3.Stream 操作时延迟执行的。这意味着他们会等到需要的结果的时候才会执行。

步骤：创建Stream -> 中间操作 -> 终止操作


![XIAN CHENG](https://github.com/wls860707495/Java/blob/master/img/940099032.jpeg) 

各步骤操作函数自行查看

### 1.5 新时间日期API

问题：原时间API存在线程安全问题，多线程下需手动加锁

#### 1.5.1 LocalDate、LocalTime和LocalDateTime

               LocalDate    LocalTime    LocalDateTime

类型              年月日         时间         年月日时间

获取指定日期     LocalDate.of()、LocalTime.of()、LocalDateTime.of()

日期时间加减     eg: LocalDateTime.plusYears() / LocalDateTime.minusDays()

LocalDateTime ->: LocalDateTime.ofInstant(date.toInstant(), ZoneId.systemDefault());

Date -> LocalDatetime: Date.from(localDataTime.atZone(ZoneId.systemDefault()).toInstant());

#### 1.5.2 Instant：时间戳（默认UTC）

获取当前时间戳：Instant.now() ，精确到毫秒数，获取中国时间需加偏移量Instant.atOffset(ZoneOffset.ofHours(8))

#### 1.5.3 时间日期差计算

Duration (LocalDateTime、Instant)

使用：Duration.between()

Period (LocalDate)

使用：Period.between()

#### 1.5.4 时间校正器

帮助快速获取常用时间（如下周、当月第一天等）

TemporalAdjusters类中有各种实现。eg：TemporalAdjusters.firstDayOfMonth()  获取当月第一天

#### 1.5.5 时间格式化工具 DateTimeFormatter

两种格式化：

DateTimeFormatter.format(datetime)

LocalDateTime.format(formatter)

也可自定义

### 1.6 接口默认方法与静态方法

相比以前，允许静态方法。除此之外若一个接口中定义了一个默认方法，而另外一个父类或接口中又定义了一个同名的方法时：

1.选择父类中的方法。如果一个父类提供了具体的实现，那么接口中具有相同名称和参数的默认方法会被忽略。

2.接口冲突。如果一个父接口提供一个默认方法，而另一个接口也提供了一个具有相同名称和参数列表的方法（不管方法是否是默认方法），那么必须覆盖该方法解决冲突。

仅供内部使用，未经授权，切勿外传
评论(0)
浏览 23 次 共 2 人浏览

写点你要说的
