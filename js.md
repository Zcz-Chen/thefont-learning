# JavaScrips

### 变量

##### 为什么需要变量？

因为我们一些数据需要保存，所以需要变量

##### 变量是什么？

变量就是一个容器，用来存放数据的。方便我们以后使用里面的数据

##### 变量的本质是什么？

变量是内存里的一块空间，用储存数据。

##### 变量怎么使用的？

1. 我们使用变量的时候，一定要声明变量，然后赋值
2. 声明变量本质是去内存申请空间。

##### 什么是变量的初始化？

声明变量并赋值我们称之为变量的初始化

##### 变量命名规范有哪些？

变量命名尽量要规范，见名知意--驼峰命名法

##### 变换2个变量值的思路？

1. 区分那些变量名不合法
2. 学会交换2个变量

##### 变量的声明提前

1. 使用var关键字声明的变量，会在所有的代码执行之前声明(但是不会赋值)
2. 但是如果声明变量时不适用var关键字，则变量不会被提前声明

### this 关键字

1. this指向的是一个对象，这个对象我们成为函数的上下文对象，根据函数的调用方式不同，this 会指向不同的对象
2.  以函数方式调用时，this永远都是window    以方法形式调用时，this就是调用那个方法的那个对象

### 原型 prototype

```javascript
    //添加一个构造函数
        function Person(name, age, gender) {
            this.name = name;
            this.age = age;
            this.gender = gender;
            // 向对象里添加一个方法
            // this.sayName = fun;
        };


        // function fun() {
        //         alert(this.name);
        //     }

            //向原型中添加方法
        Person.prototype.sayName = function(){
            alert(this.name);
        };

        // 实例
        var per = new Person("swk", 18, "nan");
        per.sayName();

        function MyClass(){

        }
        MyClass.prototype.name = "我是原型里的名字"
        var mc = new MyClass();
        // 使用 in 检查对象中是否含有某个属性时，如果对象里没有但是原型里有，就会返回 true
        console.log("name" in mc);

        // 可以使用对象的 hasOwnProperty() 来检查对象自身是否含有该属性
        // 使用该方法只有当对象自身中含有属性时，才会返回 true
        console.log(mc.hasOwnProperty("name")); // 这个返回为 false
```

