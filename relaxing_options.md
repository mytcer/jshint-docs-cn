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
        
