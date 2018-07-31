##
#流程敲定：
# 1. 用户输入一句话
# 2. 检查里面没有没有敏感词汇
#     2.1  将敏感词汇读取出来。使用readline()，或者直接使用文件管理器。
#     2.2  检测用户输入是否含有敏感词  in
# 3.判断是否有后进行反应
##

user_input=input('Please say something:')
print(user_input)
for filter_word in open('filtered_words.txt'):
     #这里碰到一个东西就是，使用open()文件迭代器的方法，会自动在读取的对象后面增加一个跨行符号\n ，
     #所以这里需要一个rstrip()去掉右边的跨行符。
    if filter_word.rstrip() in user_input:    
        print('Freedom!')
        break
else:
    print('Human Rights!')


#如果不使用跨行符，那么结果就是 filter_word in user_input 永远是false， Freedom不会被打印。

#下面示范没有rstrip()的形式。
print('这是分割线，哦啦啦啦啦')
user_input=input('Please say something:')
print(user_input)
for filter_word in open('filtered_words.txt'):
    if filter_word in user_input:    
        print('Freedom!')
        break
else:
    print('Human Rights!')