# follow-Bootstrap-grid仿照bootstrap做的栅格布局
---
布局采用 12 等分法，将 1 行平均分为 12 列
#### 关键点
**网格行的处理**
> 网格由于采用 ``` float:left ``` 脱离了文档流，导致 ``` row ``` 没有高度，采用以下方法即可恢复正常
```
.row:after{clear:both;display:block;content:''}
```
或者用下边的方法，在row加样式
```
overflow: hidden;
```
### HTML代码
```
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>仿bootstrap栅格</title>
<style type="text/css">
*{padding:0;margin:0}body{background:#000}
.container{margin:0 auto;background:#c1e2b3}
@media (min-width:768px){.container{width:750px}}
@media (min-width:992px){.container{width:970px}}
@media (min-width:1200px){.container{width:1170px}}
.container-fluid{width:100%;margin:0 auto}
.row:after{clear:both;display:block;content:''}
.row{background:#e4b9b9;box-sizing:border-box;margin:1px 0}
.col-1,.col-2,.col-3,.col-4,.col-5,.col-6,.col-7,.col-8,.col-9,.col-10,.col-11,.col-12{box-sizing:border-box;color:#fff;position:relative;float:left}
.col-1{width:8.3333333333%}
.col-2{width:16.6666666667%}
.col-3{width:24.9999999999%}
.col-4{width:33.3333333333%}
.col-5{width:41.6666666667%}
.col-6{width:49.9999999999%}
.col-7{width:58.3333333333%}
.col-8{width:66.6666666667%}
.col-9{width:74.9999999999%}
.col-10{width:83.3333333333%}
.col-11{width:91.6666666667%}
.col-12{width:99.9999999999%}
.colora{background:#337ab7}
.colorb{background:#f7ecb5}
</style>
</head>
<body>
<div class="container">
<div class="row"><div class="col-12 colora">12</div> </div>    
<div class="row">            <div class="col-6 colorb">6</div>            <div class="col-6 colora">6</div>        </div>        <div class="row">            <div class="col-4 colorb">4</div>            <div class="col-4 colora">4</div>            <div class="col-4 colorb">4</div>        </div>        <div class="row">            <div class="col-3 colora">3</div>            <div class="col-3 colorb">3</div>            <div class="col-3 colora">3</div>            <div class="col-3 colorb">3</div>        </div>        <div class="row">            <div class="col-1 colora">1</div>            <div class="col-1 colorb">1</div>            <div class="col-1 colora">1</div>            <div class="col-1 colorb">1</div>            <div class="col-8 colora">                <div class="row">                    <div class="col-3 colorb">3</div>                    <div class="col-3 colora">3</div>                    <div class="col-3 colorb">3</div>                    <div class="col-3 colora">3</div>                </div>            </div>        </div>        <div class="row">            <div class="col-1 colorb">1</div>            <div class="col-5 colora">5</div>            <div class="col-3 colorb">3</div>            <div class="col-1 colora">1</div>            <div class="col-2 colorb">2</div>        </div>        <div class="row">            <div class="col-2 colora">2</div>            <div class="col-2 colorb">2</div>            <div class="col-2 colora">2</div>            <div class="col-2 colorb">2</div>            <div class="col-2 colora">2</div>            <div class="col-2 colorb">2</div>        </div>        <div class="row">            <div class="col-7 colora">7</div>            <div class="col-2 colorb">2</div>            <div class="col-3 colora">3</div>        </div>        <div class="row">            <div class="col-5 colora">5</div>        </div>        <br>        <br>        <hr>    </div></body>
</html>

```
