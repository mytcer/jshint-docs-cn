# JSHint environments options

    说明：这些选项用于预定义来自流行JS库（如JQuery）和运行时环境（如Node）中的全局变量.
    
#### * browser

    作用：该选项定义了现代浏览器暴露出来的全局变量（不包括alert和console），true -- 启用，false -- 关闭.
    
    示例：未启用    
        /* jshint browser:false */
        var elem = document.getElementById('#aa'); // JSHint校验结果：'document' is not defined.
    
#### * couch

    作用：该选项定义了CouchDB暴露出来的全局变量，true -- 启用，false -- 关闭.
    
#### * devel

    作用：该选项定义了用于调试的全局变量（如alert，console），true -- 启用，false -- 关闭.
    
    示例：未启用   
        /* jshint devel:false */
        alert('log...'); // JSHint校验结果：'alert' is not defined.
        
#### * dojo

    作用：该选项定义了dojo暴露出来的全局变量，true -- 启用，false -- 关闭.
    
#### * jquery

    作用：该选项定义了jquery暴露出来的全局变量，true -- 启用，false -- 关闭.
    
    示例1：未启用    
        /* jshint jquery:false */
        var a = jQuery('#a'); // JSHint校验结果：'jQuery' is not defined.
        
    示例2：启用    
        /* jshint jquery:true */
        var a = jQuery('#a'); // JSHint校验结果：ok        
    
#### * mootools

    作用: 该选项定义了mootools暴露出来的全局变量，true -- 启用，false -- 关闭.
