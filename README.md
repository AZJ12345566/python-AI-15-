# python-AI-15-
Python+AI笔记(15)
# 一阶-七章-函数的多返回值
#函数体内只有一个return能起作用，若有2个return，则返回到一个return
#若需返回多个值，则在一个return中返回两个值
def test_return():
    return 1,2
x,y=test_return()
print(x)  #输出1
print(y)  #输出2

#除此之外，返回的类型是不受限的，可以是数字，字符串，bool，但是接收的时候要注意对位

# 一阶-七章-函数的多种参数使用方式
#1.位置参数   2.关键字参数(通过键🟰值的形式传递参数)    3.缺省参数(为参数提供默认值，调用函数时可不传该默认参数的值)    4.不定长参数(用于不确定调用的时候会传递多少个参数的场景)

#关键字参数可以无视传参顺序
#注:函数调用时，如果有位置参数和关键字参数混用时，位置参数必须在关键字参数前面，但关键字参数之间不存在先后顺序
def user_info(name,age,gender):
    print(name,age,gender)
user_info('小明',20,'男')  #位置参数顺序不能乱

#关键字参数
user_info(name='小王',age=11,gender='女')
user_info(age=10,gender='女',name='鲜花')  #关键字参数传参可以不按定义传参
user_info('天天',gender='女',age=9)  #顺序传参已经放到最前面了

#缺省参数
user_info(name,age,gender='男')
    print(name,age,gender)
user_info('小天'，13)  #输出小天,13,男  但是默认参数可以被覆盖
#注:默认参数是必须写到最后面的

#不定长参数
#1. 位置传递  2.关键字传递

#位置不定长 - *号
#不定长定义的形式参数会作为元组存在，接收不定长数量的参数传入
def user_info(*args):  #*后面接啥字母都可以,但是规范要求一般都是args
    print(type(args),args)  
user_info(1,2,3'小明','男孩')  #传入元素个数是不受限的

#关键字不定长 - **号
def user_info(**kwargs):
    print(type(kwargs),kwargs)
user_info(name='小王',age=11,gender='男孩')  #传入的类型必须是以键值对的形式传递的

# 一阶-七章-函数作为参数传递
def test_func(compute):
    result=compute(1,2)  #确定compute是函数
    print(type(compute))
    print(result)
def compute(x,y):
    return x+y
test_func(compute)  #这里传参直接传了一个函数，因此在函数中传参是可以传入计算逻辑的

# 一阶-七章-lambda匿名函数
#lambda关键字，可以定义匿名函数(无名称)
#有名称的函数，可以基于名称反复调用
#lambda的匿名函数，只可以临时调用一次
#语法:  lambda 传入参数:函数体(一行代码)
test_func(lambda x,y:x+y)  #结果为3

# 一阶-八章-文件编码概念
#编码和解码需要用相同的格式，常用的是GBK，UTF-8，Big5等
#UTF-8是最长用的格式
