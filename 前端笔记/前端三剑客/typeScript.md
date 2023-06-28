## 什么是TypeScript

#### 类型是TypeScript的核心。

JavaScript是一门灵活的编程语言：

* 他没有类型约束，一个变量初始化时是字符串，过一会儿又会被赋值为数字。
* 由于隐式类型转化的存在，有的变量的类型很难在程序运行前确认。
* 基于原型的面向对象编程，使得原型上的属性或者方法可以在运行时被修改。
* 函数可以赋值给变量，也可以作为参数或者返回值。

灵活使得JavaScript代码质量参差不齐，维护难度高。

#### TypeScript是静态类型

类型系统按照类型的检查时机分类，分为：静态类型、动态类型。

动态类型在运行时才进行类型检查，JavaScript是一门解释型语言，没有编译阶段，所以是动态类型。

静态类型在编译阶段就进行类型检查，类型错误会导致语法错误。TypeScript运行前先编译为JavaScript，在编译时就执行类型检查，因而是静态类型。

#### TypeScript是弱类型

类型系统按照是否允许隐式类型转换来分类，分为：强类型、弱类型。

```javascript
console.log(1+'1');
```

JAVA、JavaScript、TypeScript都是弱类型。

Python则是强类型。



#### 安装TypeScript

1.安装node.js

可以选择直接安装node.js，或者在github上下载node.js的版本管理工具nvm进行管理。

2.全局安装TypeScript

```shell
npm install -g typescript
```



安装TS之后，可以使用命令编译`.st`文件。（在react中，ts文件后缀为`.tsx`）

```shell
tsc xxx.ts
```



编译TS文件出现错误，仍然会生成.js文件，想要关闭，则可以在txconfig.json中配置noEmitOnerror。





## TypeScript基础

类型声明：

`[ let | var | const ] 变量名 : 变量类型 = 初始值 ;`

### 基础数据类型

#### 布尔值（boolean）

获取一个`boolean`值.

```typescript
let isDone: boolean = false;
let getBoolean: boolean = Boolean(1);
```

使用`Boolean()`得到对象不是布尔值，而是一个布尔对象。

```typescript
let createBoolean: Boolean = new Boolean(1)
```



#### 数值（number）

与JavaScript一样，TypeScript的所有数值都是浮点数，类型为number，支持二、八、十、十六进制。

```typescript
let dec: number = 6;
let hex: number = 0xf00d;
let binary: number = 0b1010;
let octal: number = 0o744;
```



#### 字符串（string）

字符串的数据类型为string，与JavaScript一样，可以使用`'单引号'`或者`"双引号"`来表示字符串.

```typescript
let str: string = "str";
str = '???'
```

使用模板字符串使用 **`** 包裹，以**${expr}**的形式嵌入表达式。

```typescript
let name: string = "gene";
let age: number = 18;
let sentence: string = `Hello, my name is ${name}. 
I'll be ${age + 1} years old next month`;
// 等价于下方的语句
let sentence: string = "Hello, my name is " + name + ". I'll be " + (age + 1 ) + "years old next month.";

```

#### 数组（Array）

定义数组的两种方式

```typescript
let arr:number[] = [1,23,3];
let arr:Array<number> = [1,22,3];
```



#### 元组 （tuple）

```typescript
let x:[string,number] ;
x = ['hello',20]; // true
// x = [20,'hello'] false
```



#### 枚举（enum）

使用枚举类型，为一组数据提供一个友好的名字。

```typescript
enum Color {RED,BULE,GREEN};
let c: Color = Color.RED;
```

枚举默认数值为 0开始递增。设置了一个值，那么从这个值开始递增。也可以设置为字符串。



#### 任意值（any）

当我们不知道值是何种类型的时候，就可以使用any。

```typescript
let notKnow: any[] = [1,'a',flase];
```

#### 空值（void）

当一个方法没有返回值的时候，就可以使用void。

void类型的变量只能赋值为 null 或 undefined.

#### null && undefined

null 和 undefined是所有类型的子类型，因而可以赋值给他们的父类型：number，string，boolean等。

#### never

never只能赋值给never，返回never的函数。



#### 类型断言

开发者比TypeScript更了解某个值的信息。

```typescript
let str: string = "this is a string";
let strLength :number = (<string>str).length;

let strLength: number = (str as string).length;
```



### 变量声明

#### var声明

var声明的变量可以在包含它的函数，模块，命名空间或全局作用域内部任何位置被访问。

* 多次声明同一个变量不会报错，就近原则



#### let声明

let 我熟悉的作用域范围，不允许多次声明。



#### const声明

const声明的变量在赋值之后就不能被修改。



### 解构数组

```typescript
let [first,second,...res] = [1,2,3,4,5,6];
let [,second,,fourth] = [1,2,3,4];
```



#### 解构对象

```typescript
({a,b} = {a:"asd",b:1})
```



#### 属性重命名

```typescript
let o ={a:"a",b:"aa",c:"aaa"};
let {a:n1,b:n2} = o;
```

重命名并且指定类型

```typescript
let o ={a:"a",b:"aa",c:"aaa"};
let {a:n1,b:n2}:{a:string,b:string} = o;
```



#### 设置默认值

```typescript
let o ={a:"a",b:"aa",c:"aaa"};
let {a,b="b"} = o;
```





## 接口







## 类



## 函数

```typescript
function f1 (str:string):string{
    return str;
}
```

