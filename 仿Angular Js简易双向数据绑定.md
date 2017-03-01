# 仿Angular Js简易双向数据绑定

---

代码实例：

```html
<html>
<head>
    <meta charset="UTF-8">
    <title>two-way binding</title>
</head>
<body>
<button ng-click="incre">increase</button>
<span style="color: red" ng-bind="counter"></span>
</body>
<script>
    //数据模型
    var counter = 0
    function incre() {
        counter += 1
    }
    //数据绑定
    var list = document.querySelectorAll("[ng-click]")
    list[0].onclick = (function (index) {
        return function () {
            window[list[index].getAttribute("ng-click")]()
            apply()
        }
    })(0)
    //应用到数据
    function apply() {
        var list = document.querySelectorAll("[ng-bind]")
        list[0].innerHTML = counter
    }
</script>
</html>
```

