# HTML+CSS+JS案例展示(tab栏切换效果）
> 参考来源：
>
> [JavaScript基础语法-dom-bom-js-es6新语法-jQuery-数据可视化echarts黑马pink老师前端入门基础视频教程(500多集)持续_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1Sy4y1C7ha?p=225&spm_id_from=pageDriver)

### 网页GitHub地址如下：（若加载较慢建议刷新后耐心等待一会~）

https://zhiyuanda.github.io/js_tab/

### 网页代码如下：

HTML+CSS+JS：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>tab栏切换</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }
        body {
            color: #666;
        }
        li {
            list-style: none;
        }
        .tab {
            margin: 50px auto;
            width: 990px;
        }
        .tab_list {
            margin-top: 50px;
            padding: 0;
            height: 37px;
            width: 988px;
            border: 1px solid #eee;
            border-bottom: 1px solid red;
            background-color: rgb(247,247,247);

        }
        .tab_list li {
            display: inline-block;
            padding: 10px 25px;
            height: 17px;
            line-height: 17px;
            cursor: pointer;
            font-size: 14px;
        }
        .item {
            display: none;
        }
        .red {
            background-color: #e4393c;
            color: #fff;
        }
    </style>
</head>
<body>
    <div class="tab">
        <div class="tab_list">
            <ul>
                <li class="red">商品介绍</li>
                <li>规格与包装</li>
                <li>售后保障</li>
                <li>商品评价</li>
                <li>本店好评商品</li>
            </ul>
        </div>
        <div class="tab_con">
                <div class="item" style="display: block;">商品介绍</div>
                <div class="item">规格与包装</div>
                <div class="item">售后保障</div>
                <div class="item">商品评价</div>
                <div class="item">本店好评商品</div>
        </div>
    </div>
    <script>
        var tab_list = document.querySelector('.tab_list');
        var lis = tab_list.querySelectorAll('li');
        var items = document.querySelectorAll('.item');
        for (var i = 0;i < lis.length;i++) {
            lis[i].setAttribute('index',i);
            lis[i].onclick = function() {
                for (var i = 0;i < lis.length;i++) {
                    lis[i].className = '';
                }
                this.className = 'red';
                var index = this.getAttribute('index');
                for (var i = 0;i < items.length;i++) {
                    items[i].style.display = 'none';
                }
                items[index].style.display = 'block';
            }
        }
    </script>
</body>
</html>
```

