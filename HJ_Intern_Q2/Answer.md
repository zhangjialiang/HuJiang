###第二题答案
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
