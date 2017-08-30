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
