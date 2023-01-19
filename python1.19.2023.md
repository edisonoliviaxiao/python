Python 1.19
# 1.基本介绍及其应用场所  
Python是易于学习、功能强大的编程语言。它具有高效的高层数据结构和简单而有效的面向对象的编程方法。Python优雅的语法和动态类型，加上它的解释性质，使它成为大多数平台上许多领域的脚本和快速应用开发的理想语言。

Python 解释器和广泛的标准库以源码或二进制形式从 Python 网站 https://www.python.org/ 免费提供给所有主要平台，并且可以免费分发。该网站还包含许多免费的第三方Python模块、程序和工具的发布和指向，以及额外的文档。

Python 解释器很容易用 C 或 C++ (或其他可从 C 调用的语言) 实现的新函数和数据类型进行扩展。Python也适合作为可定制应用程序的扩展语言。

自动化的任务。例如，你可能希望对大量的文本文件进行搜索和替换，或者以一种复杂的方式重命名和重新排列一堆照片文件。也许你想写一个小型的自定义数据库，或一个专门的GUI应用程序，或一个简单的游戏。

如果你是一个专业的软件开发人员，你可能需要使用几个C/C++/Java库，但发现通常的写/编译/测试/再编译的周期太慢。也许你正在为这样的库编写测试套件，并发现编写测试代码是一项乏味的工作。或者你已经写了一个可以使用扩展语言的程序，而你不想为你的应用程序设计和实现一种全新的语言。Python正是适合你的语言。

你可以写一个 Unix shell 脚本或 Windows 批处理文件来完成其中的一些任务，但 shell 脚本最擅长的是移动文件和改变文本数据，不适合 GUI 应用程序或游戏。你可以写一个C/C++/Java程序，但它可能需要大量的开发时间来获得甚至是一个初稿程序。Python使用起来更简单，可在Windows、macOS和Unix操作系统上使用，并能帮助你更快地完成工作。

Python使用起来很简单，但它是一种真正的编程语言，为大型程序提供了比shell脚本或批处理文件所能提供的更多结构和支持。另一方面，Python也比C语言提供了更多的错误检查，而且作为一种非常高级的语言，它有内置的高级数据类型，如灵活的数组和字典。由于其更通用的数据类型，Python适用于比Awk甚至Perl更大的问题域，然而许多事情在Python中至少和这些语言一样简单。

Python允许你把你的程序分成模块，可以在其他Python程序中重复使用。它带有大量的标准模块，你可以把它们作为你的程序的基础--或者作为开始学习 Python 编程的例子。其中一些模块提供了诸如文件输入/输出、系统调用、套接字，甚至是与图形用户界面工具包如Tk的接口。

Python是一种解释型语言，在程序开发过程中可以节省大量时间，因为不需要编译和链接。解释器可以交互使用，这使得实验该语言的特性、编写弃用程序或在自下而上的程序开发过程中测试功能变得容易。它也是一个方便的桌面计算器。

Python 使得程序可以写得很紧凑，很好读。用Python编写的程序通常比同等的C、C++或Java程序要短得多，这有几个原因。
-高级别的数据类型允许你在一条语句中表达复杂的操作。
-语句分组是通过缩进来完成的，而不是通过开头和结尾的括号。
-没有必要进行变量或参数声明。

Python是可扩展的：如果你知道如何用C语言编程，那么很容易在解释器中添加一个新的内置函数或模块，或者以最大的速度执行关键的操作，或者将Python程序与可能只有二进制形式的库相连（如供应商特定的图形库）。一旦你真的迷上了，你可以把 Python 解释器链接到一个用 C 写的应用程序中，并把它作为该应用程序的扩展或命令语言。


# 2.语句  
##1.if 语句
比如说
    x = int(input("Please enter an integer: " ))
    Please enter an integer: 42
    if x < 0:
    x = 0
        print('Negative changed to zero')
    elif x == 0:
        print('Zero')
    elif x == 1:
        print('Single')
    else:
        print('More')
  

可以有零个或多个elif部分，else部分是可选的。关键字'elif'是'else if'的缩写，对于避免过度缩进很有用。一个if ... elif ... elif ... 序列可以替代其他语言中的switch或case语句。

如果你要将同一个值与几个常量进行比较，或者检查特定的类型或属性，你可能也会发现匹配语句很有用。更多细节请参见匹配语句。


## 2. for 语句

Python 中的 for 语句与你在 C 或 Pascal 中可能习惯的有一些不同。Python 的 for 语句不是总是迭代数字的算术级数 (像 Pascal 一样)，也不是给用户定义迭代步骤和停止条件的能力 (像 C 一样)，而是迭代任何序列 (一个列表或一个字符串) 中的项目，按照它们在序列中出现的顺序进行。
    测量一些字符串。
    words = ['cat', 'window', 'defenestrate'] 。
    for w in words:
    print(w, len(w))
    cat 3
    窗口 6
    defenestrate 12

修改一个集合，同时在同一个集合上进行迭代的代码可能很难搞清楚。相反，通常更直接的做法是在一个集合的副本上循环，或者创建一个新的集合。
      Create a sample collection
    users = {'Hans': 'active', 'Éléonore': 'inactive', '景太郎': 'active'}

    Strategy:  Iterate over a copy
    for user, status in users.copy().items():
      if status == 'inactive':
        del users[user]
    
    Strategy:  Create a new collection
      active_users = {}
        for user, status in users.items():
      if status == 'active':
        active_users[user] = status

##3.range()函数  
如果你确实需要对一个数字序列进行迭代，内置函数range()就会派上用场。它可以生成算术级数。

    >>> for i in range(5):
    ...     print(i)
    ...
    0
    1
    2
    3
    4

给出的端点从来不是生成的序列的一部分；range(10)生成10个值，是长度为10的序列项目的合法索引。可以让范围从另一个数字开始，或者指定一个不同的增量（甚至是负数；有时这被称为 "步长"）。
    >>> list(range(5, 10))
    [5, 6, 7, 8, 9]

    >>> list(range(0, 10, 3))
    [0, 3, 6, 9]

    >>> list(range(-10, -100, -30))
    [-10, -40, -70]

为了遍历一个序列的索引，你可以把range()和len()结合起来
    >>> a = ['Mary', 'had', 'a', 'little', 'lamb']
    >>> for i in range(len(a)):
        print(i, a[i])
     0 Mary
     1 had
     2 a
     3 little
     4 lamb

然而，在大多数这种情况下，使用enumerate()函数是很方便的，见循环技术。

如果你只是打印一个range，会发生一件奇怪的事情。
     >>> range(10)
         range(0, 10)

在许多方面，range() 返回的对象表现得好像是一个列表，但事实上它不是。它是一个对象，当你对它进行迭代时，它返回所需序列的连续项，但它并没有真正形成列表，因此节省了空间。

我们说这样的对象是可迭代的，也就是说，它适合作为函数和结构体的目标，这些函数和结构体期望能从中获得连续的项目，直到供应耗尽。我们已经看到 for 语句就是这样一个结构，而函数的一个例子是 sum()，它可以接收一个可迭代对象。
   
     >>> sum(range(4))  # 0 + 1 + 2 + 3       
             6

## 4.break和continue语句，以及循环中的else句子

像C语言一样，break语句会从最里面的for或while循环中断开。

循环语句可以有一个else子句；当循环因迭代器耗尽而终止时（for），或当条件变为false时（while），它就会被执行，但当循环被break语句终止时，就不会被执行。下面这个搜索素数的循环就是一个例子。

     for n in range(2, 10):
     for x in range(2, n):
        if n % x == 0:
            print(n, 'equals', x, '*', n//x)
            break
        else:
            loop fell through without finding a factor
     print(n, 'is a prime number')
...
    2 is a prime number
    3 is a prime number
    4 equals 2 * 2
    5 is a prime number
    6 equals 2 * 3
    7 is a prime number
    8 equals 2 * 4
    9 equals 3 * 3

这就是正确的代码。仔细看：else子句属于for循环，而不是if语句）。

当与循环一起使用时，else子句与try语句的else子句有更多的共同点，而不是if语句的else子句：try语句的else子句在没有异常发生时运行，而循环的else子句在没有中断发生时运行。关于try语句和异常的更多信息，请参见处理异常。

continue语句也是从C语言借来的，它继续进行循环的下一次迭代

    for num in range(2, 10):
        if num % 2 == 0:
           print("Found an even number", num)
            continue
        print("Found an odd number", num)
...
    Found an even number 2
    Found an odd number 3
    Found an even number 4
    Found an odd number 5
    Found an even number 6
    Found an odd number 7
    Found an even number 8
    Found an odd number 9

##5.pass语句

pass语句不做任何事情。当语法上需要一个语句，但程序不需要任何操作时，可以使用它。
    while True:
       pass  # Busy-wait for keyboard interrupt (Ctrl+C)

这通常用于创建最小的类。
    class MyEmptyClass:
       pass

##6.match语句

match语句接收一个表达式，并将其值与作为一个或多个案例块给出的连续模式进行比较。这在表面上类似于C、Java或JavaScript（以及许多其他语言）中的switch语句，但它也可以从值中提取成分（序列元素或对象属性）进入变量。

最简单的形式是将一个主题值与一个或多个字面符号进行比较。
    def http_error(status):
      match status:
          case 400:
              return "Bad request"
          case 404:
              return "Not found"
          case 418:
              return "I'm a teapot"
          case _:
              return "Something's wrong with the internet"

注意最后一个区块："变量名"_作为通配符，永远不会失败。如果没有匹配的情况，则不执行任何分支。

你可以用|（"或"）在一个模式中组合几个字词。

    case 401 | 403 | 404:
       return "Not allowed"

Patterns can look like unpacking assignments, and can be used to bind variables:

    point is an (x, y) tuple
      match point:
      case (0, 0):
          print("Origin")
      case (0, y):
          print(f"Y={y}")
      case (x, 0):
          print(f"X={x}")
      case (x, y):
          print(f"X={x}, Y={y}")
      case _:
          raise ValueError("Not a point")

第一个模式有两个字面，可以认为是上面所示字面模式的延伸。但是接下来的两个模式结合了一个字面意义和一个变量，变量绑定了一个来自主体（点）的值。第四种模式捕获了两个值，这使得它在概念上类似于解包赋值（x, y）= point。

如果你使用类来结构你的数据，你可以使用类的名称，后面跟一个类似于构造函数的参数列表，但有能力将属性捕捉到变量中。

class Point:
    x: int
    y: int

def where_is(point):
    match point:
        case Point(x=0, y=0):
            print("Origin")
        case Point(x=0, y=y):
            print(f"Y={y}")
        case Point(x=x, y=0):
            print(f"X={x}")
        case Point():
            print("Somewhere else")
        case _:
            print("Not a point")

你可以在一些为其属性提供排序的内置类中使用位置参数（例如，数据类）。你也可以通过在你的类中设置__match_args__特殊属性来为模式中的属性定义一个特定位置。如果它被设置为 ("x", "y")，下面的模式都是等价的 (并且都将y属性绑定到var变量上)。

Point(1, var)
Point(1, y=var)
Point(x=1, y=var)
Point(y=var, x=1)


推荐的阅读模式的方法是把它们看成是你放在赋值左边的扩展形式，以了解哪些变量会被设置成什么。只有独立的名字（如上面的var）是由匹配语句赋值的。带点的名字（比如foo.bar）、属性名（上面的x=和y=）或类名（通过旁边的"（...）"识别，比如上面的Point）永远不会被赋值。

模式可以任意嵌套。例如，如果我们有一个简短的点的列表，我们可以这样来匹配它
match points:
    case []:
        print("No points")
    case [Point(0, 0)]:
        print("The origin")
    case [Point(x, y)]:
        print(f"Single point {x}, {y}")
    case [Point(0, y1), Point(0, y2)]:
        print(f"Two on the Y axis at {y1}, {y2}")
    case _:
        print("Something else")

我们可以在模式中添加一个if子句，即所谓的 "guard"。如果保护句是假的，匹配就会继续尝试下一个案例块。请注意，value capture发生在guard被评估之前。

match point:
    case Point(x, y) if x == y:
        print(f"Y=X at {x}")
    case Point(x, y):
        print(f"Not on the diagonal")

这个语句的其他几个关键特征。

-与解包赋值一样，元组和列表模式具有完全相同的含义，实际上可以匹配任意的序列。一个重要的例外是，它们不匹配迭代器或字符串。

-序列模式支持扩展的解包：[x, y, *rest]和(x, y, *rest)的工作类似于解包赋值。*后面的名字也可以是_，所以(x, y, *_)匹配至少两个项目的序列而不绑定其余项目。

-映射模式。{"bandwidth": b, "latency": l}从一个字典中捕获 "bandwidth "和 "latency "的值。与序列模式不同，额外的键会被忽略。也支持像**rest那样的解包。(但是 **_ 是多余的，所以它不允许)。

-子模式可以使用 as 关键字来捕获。

case (Point(x1, y1), Point(x2, y2) as p2): ...
将捕获输入的第二个元素为p2（只要输入是两点的序列）。

-大多数字词是通过等价比较的，但是单数True、False和None是通过身份比较的。

-模式可以使用命名的常数。这些名称必须是带点的，以防止它们被解释为捕获变量。
from enum import Enum
class Color(Enum):
    RED = 0
    GREEN = 1
    BLUE = 2

match color:
    case Color.RED:
        print("I see red!")
    case Color.GREEN:
        print("Grass is green")
    case Color.BLUE:
        print("I'm feeling the blues :(")
