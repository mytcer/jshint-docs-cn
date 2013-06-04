JSHint文档汉化版
=================

## 一. JSHint options

JSHint有两种类型的options：强制型和宽松型，前者使JSHint更加严格，后者用来抑制一些警告.


#### 1. 强制型
  
    * bitwise
    
    作用：值为true时，禁止使用位操作符，如"^，|，&"等.
    
    * camelcase
  
    作用：值为true时，变量名必须使用驼峰风格（如"loginStatus"）或UPPER_CASE风格（如"LOGIN_STATUS"）.
    
    * curly
    
    作用：值为true时，不能省略循环和条件语句后的大括号.
    
    备注：如"if (con) ..."，需要写成"if (con) { ... }".
    
    * eqeqeq
    
    作用：值为true时，禁止使用"=="和"!="，而应该使用"==="和"!==".
    
    * es3
    
    作用：值为true时，表示你的代码需要遵守ECMAScript 3规范.
    
    * forin
    
    作用：值为true时，在所有"for in"循环中，必须使用hasOwnPropery过滤掉对象继承来的成员.
    
    * immed
    
    作用：???.
    
    * indent
    
    作用：该选项要求你的代码必须使用指定的tab缩进宽度，如"indent:4".
    
    * latedef
    
    作用：值为true时，禁止在变量定义之前使用它.
    
    * newcap
    
    作用：值为true时，构造函数名需要大写. 
    
    备注：经测试，该选项是否激活，JSHint都不会检查构造函数名.
    
    * noarg
    
    作用：值为true时，禁止使用arguments.caller与arguments.callee.
    
    * noempty
    
    作用：值为true时，不允许代码中出现空的语句块（"{}"）.
    
    * nonew
    
    作用：值为true时，禁止使用产生副作用的构造器调用方式，如"new MyConstructor();".
    
    备注：上面的调用所产生的对象，没有赋值给任何变量，和直接调用函数没什么区别.
    

#### 2. 宽松型

