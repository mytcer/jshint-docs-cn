JSHint relaxing options
=================

#### * asi

    作用：值为false时，如果代码末尾省略了分号，则JSHint会给出警告；值为true时，则不会.

#### * boss

    作用：值为false时，如果预期为条件表达式的地方使用了赋值表达式，则JSHint会给出警告；值为true时，则不会.
    
    示例：/* jshint boss:false */
             
        // 例1: if条件判断中存在赋值操作
        var a;
        if (a = 1) { // jshint校验结果：Expected a conditional expression and instead saw an assignment.
            alert(1);
        }
        
        // 例2: for循环的条件判断中存在赋值操作
        for (var i = 0, j; j = i; i++) { // jshint校验结果：同上
            alert(j);
        }
        
#### * debug

    作用：值为false时，如果代码中有debugger语句，则JSHint会给出警告；值为true时，则不会.
    
    示例：/* jshint debug:false */

        function show() {
            alert(1);
            debugger; // jshint校验结果：Forgotten 'debugger' statement?
        }
    
#### * eqnull

    作用：值为false时，如果代码中使用"=="来比较变量与null，则JSHint会给出警告；值为true时，则不会.
    
    示例：/* jshint eqnull:false */
    
        var a;
        alert(a == null); // Expected '===' and instead saw '=='.

#### * esnext

    作用：值为true时，JSHint会使用ECMAScript 6的语法来校验你的代码.
    
#### * evil

    作用：值为false时，不允许在代码中使用eval.
    
#### * expr

    作用：值为false时，只允许在函数调用或赋值时使用表达式.
    
    示例：/* jshint expr:false */
    
        // JSHint校验结果：Expected an assignment or function call and instead saw an expression.
        2 > 1 ? (alert(1)) : (alert(2));
        
#### * funcscope

    作用：值为false时，如果在控制语句中定义了变量，却在控制语句之外使用变量，则JSHint会给出警告.
    
    备注：JS中只有两种作用域：全局作用域与函数作用域.
    
    示例：/* jshint funcscope:false */
    
    function test() {
        if (true) {
            var x = 0;
        }
        
        x = x + 1; // JSHint校验结果：'x' used out of scope.
    }

#### * globalstrict

    作用：值为false时，不允许使用全局级别的严格模式.
    
    备注：在全局中使用严格模式，会影响到第三方的JS，因此不建议这么做.
    
    示例：/* jshint globalstrict:false */
    
        "use strict"; // JSHint校验结果：Use the function form of "use strict".
        function show() {
            alert(1);
        }
        
#### * iterator

    作用：???
    
#### * lastsemic

    作用：值为true时，允许单行语句块中最后一条语句不写分号；值为false时，则会给出警告.
    
    示例：值为true和false时，校验结果对比（return语句未写分号）
    
        /* jshint lastsemic:true */
        var a = function() {alert(1);return 'hehe'}(); // JSHint校验结果：pass
    
        /* jshint lastsemic:false */
        var a = function() {alert(1);return 'hehe'}(); // JSHint校验结果：Missing semicolon.
        
#### * laxbreak

    作用：值为true时，允许代码中存在大多数不安全的换行（不包括逗号出现在行首的情况）；值为false时，会给出警告.
    
    示例：暂无（哪些换行是不安全滴???）.
    
#### * laxcomma

    作用：值为true时，允许逗号出现在行首的换行方式；值为false时，会给出警告.
    
    示例：值为true和false时，校验结果对比
    
        /* jshint laxcomma:true */
        var obj = {
            name: 'haha'
            ,age: 24 // JSHint校验结果：pass
        };
        
        /* jshint laxcomma:false */
        var obj = {
            name: 'haha'
            ,age: 24 // JSHint校验结果：Bad line breaking before ','.
        };
        
#### * loopfunc

    作用：值为true时，允许在循环中定义函数；值为false时，会给出警告.
    
    示例：值为false
    
        /* jshint loopfunc:false */
        var nums = [];
        for (var i = 0; i < 10; i++) {
            nums[i] = function (j) { // JSHint校验结果：Don't make functions within a loop.
                return i + j;
            };
        }
        nums[0](2);
    
#### * moz

    作用：该选项告诉JSHint，你的代码中使用了Mozilla JavaScript扩展.
    
#### * multistr

    作用：值为true时，允许多行字符串；值为false时，则会给出警告.

    备注：当值为true时，如果多行之间缺少转义字符，或者转义字符与新行之间有空白，JSHint依然会给出警告.
    
    示例1：值为true
    
        /* jshint multistr:true */
        var text = "hello\
        world"; // JSHint校验结果：pass
        
    示例2：值为true，但缺少转义字符
    
        /* jshint multistr:true */
        var text = "hello
        world"; // JSHint校验结果：Unclosed string.
        
    示例3：值为true，有转义字符，但转义字符与新行之间有空白
    
        /* jshint multistr:true */
        var text = "hello\ 
        world"; // JSHint校验结果：Bad or unnecessary escaping.
        
    示例4：值为false，有转义字符
    
        /* jshint multistr:false */
        var text = "hello\ 
        world"; // JSHint校验结果：Bad escaping of EOL. Use option multistr if needed.   
        
#### * proto

    作用：值为true时，允许在代码中使用__proto__属性；值为false时，则会给出警告.
    
#### * scripturl

    作用：值为true时，允许在代码中使用"javascript:..."这样的url；值为false时，则会给出警告.
    
    示例：值为false时
    
        /* jshint scripturl:false */
        var link = document.createElement('a');
        link.href = 'javascript:void()'; // JSHint校验结果：Script URL.
        
#### * smarttabs

    作用：???
    
#### * shadow

    作用：
    
#### * sub

    作用：值为true时，允许用obj['name']和obj.name两种方式访问对象的属性；值为false时，不允许使用obj['name']方式，
          除非只能使用这种方式访问.
    
    示例：值为false
    
        /* jshint sub:false */
        var obj = {name: 'he'};
        alert(obj['name']);  // JSHint校验结果：['name'] is better written in dot notation.
