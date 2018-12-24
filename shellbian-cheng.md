
---

* 状态码

```
#当shell脚本不写或者退出为exit时候，返回状态码为0
#!/bin/bash

echo hello
echo $?                 #退出状态为0, 因为命令执行成功

lskdf                   #无效命令.
echo $?                 #非零的退出状态, 因为命令执行失败.
echo

exit 113                #返回113退出状态给shell.
```

* 括号含义

```
()            一般用作数组或者分割新开命令组；在和$组合使用时候代表返回命令结果，作用同反引号.
(())          一般用作表达式处理；和$组合使用时候代表返回表达式结果，作用同expr和let.
[]或[  ]      没有空格时候一般用作数组下标，当存在空格时候使用则是bash内部命，等同于test.
[[  ]]        是bash程序语言的关键字，一般用作条件判断，由于是关键字，故在使用时候[[前后都需要空格.
{}            一般用作通配或者代码块；在和$符合组合使用嘿嘿用作变量处理.
```

* 比较方式

```
[  ]或test    使用时候判断数字使用（–eq、–ge、–gt、–le、–lt、–ne）等；字符串使用（–n、-z、＝、!＝）等；连接符使用（–a、–o、!）等；其他情况会把字符串当成文件处理.
[[ ]]         使用时候判断数字使用（–eq、–ge、–gt、–le、–lt、–ne）等；字符串使用（–n、-z、＝、!＝）等；但连接符号使用（&&和||），形式：[[ exp1 ]]&&[[ exp2 ]]；无论数字还是字符一般情况都会被当做字符串处理.
(())          表达式比较时候使用，如for((i=0;i<10;i++)).
```

* 数学运算

```
let                    let后跟表达式，如：let var2=$var1+4.
expr                   expr后跟变量和运算符，将其看作独立个体做运算，故其间需要空格隔开，如：expr $var + 4.
$((exp))               计算exp的结果并返回.   
$[exp]                 和$((exp))含义相同.
```

---

* shell内置变量

```
$BASH                  Bash的二进制程序文件的路径
$BASH_ENV              这个环境变量会指向一个Bash的启动文件, 当一个脚本被调用的时候, 这个启动文件将会被读取.
$BASH_SUBSHELL         这个变量用来提示子shell的层次. 这是一个Bash的新特性, 直到版本3的Bash才被引入近来.
${BASH_VERSINFO[n]}    这是一个含有6个元素的数组, 它包含了所安装的Bash的版本信息等.
$BASH_VERSION          Bash版本号
$DIRSTACK              在目录栈中最顶端的值，这个内建变量与dirs命令相同.
$EDITOR                脚本所调用的默认编辑器, 通常情况下是vi或者是emacs.
$EUID                  "有效"用户ID.
$FUNCNAME              当前函数的名字.
$GLOBIGNORE            一个文件名的模式匹配列表.
$GROUPS                目前用户所属的组
$HOME                  用户的home目录.
$HOSTNAME              系统的hostname.
$HOSTTYPE              主机架构类型.
$IFS                   内部域分隔符，这个变量用来决定Bash在解释字符串时如何识别域, 或者单词边界.
$IGNOREEOF             忽略EOF: 告诉shell在log out之前要忽略多少文件结束符(control-D).
$LC_COLLATE            常在.bashrc或/etc/profile中设置, 这个变量用来控制文件名扩展和模式匹配的展开顺序.
$LC_CTYPE              这个内部变量用来控制通配(globbing)和模式匹配中的字符串解释.
$LINENO                这个变量用来记录自身在脚本中所在的行号. 这个变量只有在脚本使用这个变量的时候才有意义,并且这个变量一般用于调试目的.
$MACHTYPE              机器类型、标识系统的硬件.
$OLDPWD                之前的工作目录.
$OSTYPE                操作系统类型
$PATH                  可执行文件的搜索路径,一般为/usr/bin/,/usr/X11R6/bin/,/usr/local/bin,等等.
$PIPESTATUS            这个数组变量将保存最后一个运行的前台管道的退出状态码.
$PPID                  进程的$PPID就是这个进程的父进程的进程ID(pid).
$PROMPT_COMMAND        这个变量保存了在主提示符$PS1显示之前需要执行的命令.
$PS1                   这是主提示符, 可以在命令行中见到它.
$PS2                   第二提示符, 当你需要额外输入的时候, 你就会看到它. 默认显示">".
$PS3                   第三提示符, 它在一个select循环中显示.
$PS4                   第四提示符, 当你使用-x选项来调用脚本时, 这个提示符会出现在每行输出的开头. 默认显示"+".
$PWD                   工作目录.
$REPLY                 当没有参数变量提供给read命令的时候, 这个变量会作为默认变量提供给read命令.
$SECONDS               这个脚本已经运行的时间(以秒为单位).
$SHELLOPTS             Shell中已经激活的选项的列表, 这是一个只读变量.
$SHLVL                 Shell级别, 就是Bash被嵌套的深度. 如果是在命令行中, 那么$SHLVL为1, 如果在脚本中那么$SHLVL为2.
$TMOUT                 如果$TMOUT环境变量被设置为非零值time的话, 那么经过time秒后, shell提示符将会超时. 这将会导致登出(logout).
$UID                   用户ID号当前用户的用户标识号, 记录在/etc/passwd文件中.
$RANDOM                输出一个随机数.
```

* 位置参数

```
$0, $1, $2...          位置参数, 从命令行传递到脚本, 或者传递给函数, 或者set给变量.
$#                     位置参数的个数.
$*                     所有的位置参数都被看作为一个单词.
$@                     与$*相同, 但是每个参数都是一个独立的引用字符串, 这就意味着, 参数是被完整传递的, 并没有被解释或扩展.
$-                     传递给脚本的标记(使用set命令).
$!                     运行在后台的最后一个作业的PID(进程ID).
$_                     这个变量保存之前执行的命令的最后一个参数的值.
$?                     命令, 函数, 或者是脚本本身的退出状态码.
$$                     脚本自身的进程ID.
$var                   输出变量值.
$(command)             和反引号作用相同，得到命令输出结果.
$((exp))               得到表达式的输出结果.
$[exp]                 作用和$((exp))相同
${var symbol pattern}  通过正则表达式修改变量值${var:-string}、${var:=string}、 ${var:+string}、${var:?string}、${var%pattern}、${var%%pattern}、${var#pattern}、${var##pattern}、${var:num}、${var:num1:num2}、${var/pattern/pattern}、${var//pattern/pattern}.
```

* 内建命令

通过`type command`区分该命令是否是内建命令。

```
IO方面：
echo
printf
read

文件系统：
cd
pwd
pushd、popd、dirs

变量方面：
let
eval
set
unset
export
declare、typeset
readonly
getopts

脚本行为：
source、.
exit
exec
shopt
caller

命令方面：
true
false
type
hash
bind
help

作业控制：
jobs
disdown
fg、bg
wait
suspend
logout
times
kill
killall
command
builtin
enable
autoload
```


