# jQuery$命名冲突

#### 解决：使用 `noConflict()` 方法：

1.把 jQuery 赋值给自定义的变量名：
```
var jq = $.noConflict(); 
jq(document).ready(function(){ 
    jq("button").click(function(){ 
        jq('#msg').hide();
    }); 
}); 
```

2.在代码块中使用 $：
```
JQuery.noConflict(); 
JQuery(document).ready(function($){ 
    $('#msg').hide();  //此时在整个ready事件的方法中使用的$都是jquery.js中定义的$. 
});
```

3.使用立即执行函数：
```
(function($){ 
    ..... 
    $('#msg').hide();  //此时在这个语句块中使用的都是jquery.js中定义的$. 
})(JQuery);
```
