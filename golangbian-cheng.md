
---

* 原生数据类型

```
值类型：
int8、int16、int32、int64                    有符号整数.
uint8、uint16、uint32、uint64                无符号整数.
float32、float64                            浮点数.
complex64、complex128                       复数.
bool                                        布尔类型.
string                                      字符串类型.
array                                       数组类型.
struct                                      结构体类型.

引用类型：
slice                                       切片类型，类似于java的list类型.
map                                         散列表类型.
chan T                                      通道数据类型.
uintptr                                     指针类型，本质为32位无符号整数.
interface                                   接口类型.
```

* 内置（buildin）数据类型和函数

```
内置数据类型：
const                                       声明常用常量的值：true  = 0 == 0，false = 0 != 0，const iota = 0
Variables                                   声明nil的类型为Type（int）：var nil Type（不初始化则默认值为0）
ComplexType                                 声明complex64别名：type ComplexType complex64
FloatType                                   声明float32别名：type FloatType float32
IntegerType                                 声明int别名：type IntegerType int
Type                                        声明int别名：type Type int
Type1                                       声明int别名：type Type1 int
bool                                        声明bool类型别名：type bool bool
byte                                        声明byte别名：type byte = uint8，无=号时候是不同类型，需要一个类型需要类型转换后才能赋值给另一个类型.
complex128                                  声明complex128别名：type complex128 complex128
complex64                                   声明complex64别名：type complex64 complex64
error                                       生成erro接口：type error interface { Error() string }
float32                                     声明float32别名：type float32 float32
float64                                     声明float64别名：type float64 float64
int                                         声明int别名：type int int
int16                                       声明int16别名：type int16 int16
int32                                       声明int32别名：type int32 int32
int64                                       声明int64别名：type int64 int64
int8                                        声明int8别名：type int8 int8
rune                                        声明byte别名：type rune = int32
string                                      声明string别名：type string string
uint                                        声明uint别名：type uint uint
uint16                                      声明uint16别名：type uint16 uint16
uint32                                      声明uint32别名：type uint32 uint32
uint64                                      声明uint64别名：type uint64 uint64
uint8                                       声明uint8别名：type uint8 uint8
uintptr                                     声明uintptr别名：type uintptr uintptr

内置处理函数：
append                                      把数据增加到slice里面,返回修改后的slice.
cap                                         获取切片容量.
close                                       关闭channel.
complex                                     构建复数.
copy                                        复制slice，返回复制的数目.
delete                                      从map中删除key对应的value.
imag                                        返回complex的实部.
real                                        返回complex的虚部.
len                                         返回切片或者数组中的数据长度.
make                                        返回Type本身(只能应用于slice, map, channel).
new                                         返回指向Type的指针.
panic                                       停止常规的goroutine.
print                                       内建函数print以特有的方法格式化参数并将结果写入标准错误，用于自举和调试.
println                                     类似print，但会在参数输出之间添加空格，输出结束后换行.
recover                                     允许程序定义goroutine的panic动作.
```

---

* goroutine和通道（原生）

```

```

* 共享变量和锁（标准库）

```

```

---

* 单元测试（标准库）

```

```

* mock测试（第三方）

```

```

---

* 反射

```

```

* 其他

```

```

---



