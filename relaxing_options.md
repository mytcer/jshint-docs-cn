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

    作用：值为false时，不允许使用__iterator__属性?
    
#### * lastsemic

    作用：
