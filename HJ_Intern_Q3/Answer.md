###第三题
设置动画调用元素只需执行下面这句话：`animation.initAnimation('img');` 如果需要新增或者删减，直接修改参数即可。如：
`animation.initAnimation('img', 'div', 'a');` 和 `animation.initAnimation(['img', 'a']);`两种形式的参数传入都可以。

```JavaScript
var animation = (function () {
    var elems = [];
    var set = function (list) {
        elems.length = 0;
        for (var i = 0,l = list.length; i < l; i++) {
            elems.push(document.getElementsByTagName(list[i]));
        }
    };
    var init = function () {
        if (arguments.length > 0) {
            var params = arguments[0] instanceof Array ? arguments[0]
                        : Array.prototype.slice.call(arguments);
            set(params);
        }
        var icon = document.querySelector('.logo img');
        icon.addEventListener('click', function (event) {
            var aniConfig = "transform: rotate(-180deg); transition: transform 2s ease";
            for (var i = 0,l = elems.length; i < l; i++) {
                for (var j = 0,len = elems[i].length; j < len; j++) {
                    elems[i][j].style.cssText += aniConfig;
                } 
            }
            event.preventDefault();
        });
    };
    return {
        'initAnimation': init
    }
})();
animation.initAnimation('img');
```
