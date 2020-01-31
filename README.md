# storage
""" 知识点一  ： 类的类属性介绍，是咧属性介绍 ：
1： 共有类属性的修改
2： 添加新的共有类"""


class person(object):
    tall = 180
    hobbies = []

    def __init__(self, name, age,weight):
        self.name = name
        self.age = age
        self.weight = weight

    def infoma(self):
        print('%s is %s weights %s'%(self.name,self.age,self.weight))


#  1：添加类属性
person.hobbies.extend([1,2,3])
print(person.hobbies)

# 2: 修改类属性,这里的原理其实覆盖之前那个类
person.hobbies = [4,4,4]
print(person.hobbies)

# 3：新增类属性
person.hobbies2 = '我是新增的类属性'
print(person.hobbies2)
print(dir(person))   # 通过dir可以查看类属性
print(person.__dict__)  # 通过__dict__可以查看字典类型的类属性用法（类名.__dict__）就可以了

""" 二：实列属性
1： 只能通过实列访问，操作如下 """
Bruce = person('madison',20,80)  # 1 先实例化一个对象
print(Bruce.age)  # 2:然后通过实例去调用实例属性

"""
2: 添加实例属性，操作如下 """
Bruce.height = '180CM'  # 1：添加实例属性
print(Bruce.height)
Bruce.height = '000'  # 2：对新添加的实例属性进行修改
print(Bruce.height)
print(dir(Bruce))  # 3:实例属性只能通过实例查看
print(Bruce.__dict__)  # 4:查看字典类型的实例属性
