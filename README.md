JSHint文档汉化版
=================

## JSHint options

JSHint有两种类型的options：强制型和宽松型，前者使JSHint更加严格，后者用来抑制一些警告.


#### 一. 强制型
  
##### * bitwise
    
    作用：值为true时，禁止使用位操作符，如"^，|，&"等.
    
##### * camelcase
  
    作用：值为true时，变量名必须使用驼峰风格（如"loginStatus"）或UPPER_CASE风格（如"LOGIN_STATUS"）.
    
##### * curly
    
    作用：值为true时，不能省略循环和条件语句后的大括号.
    
    备注：如"if (con) ..."，需要写成"if (con) { ... }".
    
##### * eqeqeq
    
    作用：值为true时，禁止使用"=="和"!="，而应该使用"==="和"!==".
    
##### * es3
    
    作用：值为true时，表示你的代码需要遵守ECMAScript 3规范.
    
##### * forin
    
    作用：值为true时，在所有"for in"循环中，必须使用hasOwnPropery过滤掉对象继承来的成员.
    
##### * immed
    
    作用：???.
    
##### * indent
    
    作用：该选项要求你的代码必须使用指定的tab缩进宽度，如"indent:4".
    
##### * latedef
    
    作用：值为true时，禁止在变量定义之前使用它.
    
##### * newcap
    
    作用：值为true时，构造函数名需要大写. 
    
    备注：经测试，该选项是否激活，JSHint都不会检查构造函数名.
    
##### * noarg
    
    作用：值为true时，禁止使用arguments.caller与arguments.callee.
    
##### * noempty
    
    作用：值为true时，不允许代码中出现空的语句块（"{}"）.
    
##### * nonew
    
    作用：值为true时，禁止使用产生副作用的构造器调用方式，如"new MyConstructor();".
    
##### * plusplus
    
    作用：值为true时，禁止使用一元递增（"++"）和递减（"--"）运算符.
    
##### * quotmark
    
    作用：该选项用于统一代码中的引号风格，可选的值有三个：
          (1) single -- 只能使用单引号；
          (2) double -- 只能使用双引号；
          (3) true -- 两者任选其一，但不能同时出现.
    
##### * undef
    
    作用：值为true时，禁止使用未定义的变量.
    
##### * unused
    
    作用：该选项激活后，对于"已定义却未使用的变量"会给出警告，可选的值有三个：
          (1) vars -- 只检查变量，不检查函数形参；
          (2) strict -- 检查变量和函数形参；
          (3) true -- 检查变量和函数形参，但允许这种情况：一个未使用的形参后紧随一个被使用的形参.
          
    示例：strict与true的区别
          (1) strict
              function show(x,y) {alert(y);}  // jshint校验结果：'x' is defined but never used
              show(1);
          
          (2) true
              function show(x,y) {alert(y);} // jshint校验结果：pass
              show(1); 
        
##### * strict
    
    作用：值为true时，该选项会要求所有函数在ECMAScript 5的严格模式中运行.
    
    备注：该选项激活后，仅在函数作用域中启用严格模式（如果在全局作用域中启用，可能会影响页面中的第三方JS）.

##### * trailing

    作用：值为true时，禁止在代码的末尾出现空白.
    
##### * maxparams

    作用：该选项用于设置每个函数形参数量的上限，如"maxparams:3".
    
##### * maxdepth

    作用：该选项用于设置每个函数中代码块嵌套层级的上限，如"maxdepth:1".
    
    示例：/* jshint maxdepth:1 */
          function show() {
            if (1) {
              if (2) { // jshint校验结果：Blocks are nested too deeply. (2)
                alert('the second nested');
              }
            }
          }
    
##### * maxstatements

    作用：该选项用于设置每个函数中语句数量的上限，如"maxstatements:4".
    
    备注：函数声明被看作一个语句.
    
    示例：/* jshint maxstatements:4 */
          function main() { // jshint校验结果：This function has too many statements. (5)
            var i = 0;
            var j = 0;

            // 函数声明被看作一个语句
            function inner() {
              var i2 = 1;
              var j2 = 1;
              return i2 + j2;
            }

            j = i + j;
            return j;
          }

##### * maxcomplexity

    作用：???
    
##### * maxlen

    作用：该选项用于设定每行的最大字符长度.

#### 二. 宽松型

