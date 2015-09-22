###第二题答案
将下面两问的答案贴到chrome控制台里运行一下即可实现相关功能。为了精简代码css3的transition，transform属性并未添加浏览器兼容性前缀。ie9以下不支持css3属性，因此就忽略事件处理兼容（attachEvent）。
#####第一小问
```JavaScript
(function () {
    var pers = document.querySelector('.logo a');
    var icon = pers.querySelector('img');
    icon.addEventListener('click', function (event) {
        var aniConfig = "transform: rotateY(180deg); transition: transform 1s";
        pers.style.perspective = '500px';
        icon.style.cssText += aniConfig;
        event.preventDefault();
    }); 
})();

```
#####第二小问
```JavaScript
(function () {
    var imgs = document.getElementsByTagName('IMG');
        var icon = document.querySelector('.logo img');
        icon.addEventListener('click', function (event) {
            var aniConfig = "transform: rotate(-180deg); transition: transform 2s ease";
            for (var i = 0,l = imgs.length; i < l; i++) {
                imgs[i].style.cssText += aniConfig;
            }
        event.preventDefault();
    }); 
})();
```
