# jQuery$命名冲突

#### 解决：使用 `noConflict()` 方法：

```
var jq = $.noConflict(); 
jq(document).ready(function(){ 
    jq("button").click(function(){ 
        jq("p").text("jQuery 仍在运行！"); 
    }); 
}); 
```
或者：
```
JQuery.noConflict(); 
JQuery(document).ready(function($){ 
    $('#msg').hide();  //此时在整个ready事件的方法中使用的$都是jquery.js中定义的$. 
});
```
或者：
```
(function($){ 
    ..... 
    $('#msg').hide();  //此时在这个语句块中使用的都是jquery.js中定义的$. 
})(JQuery);
```
