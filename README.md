# JavaScript-window.print-
JavaScript中window.print()打印
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>printDemo</title>
</head>
<body>
  <input type="button" value="打印此页面" onclick="printpage()" />
  <div>内容</div>
  <script>
    function printpage() {
      window.print()
    }
  </script>
</body>
</html>

【1】使用打印样式表
<link href="/path/print.css" media="print" rel="stylesheet" />
配置一份打印样式表print.css，引入到HTML文档，在 <link> 上加上一个 media="print" 来标识这是打印机才会应用的样式表，这样打印的时候，就会默认将该样式表应用到文档中

方式1：在当前页面打印
1、var newStr = document.getElementById(printDiv).innerHTML;//获取打印的部分
2、var bodyStr = document.body.innerHtml;//获取当前页所有内容
3、 document.body.innerHTML = newStr; //打印部分写到当前页
4、  window.print(); //执行打印功能
5、 document.body.innerHTML = bodyStr; // 打印执行完之后把之前页面内容写到页面

方式2：新建浏览器对话框打印
1、var newStr = document.getElementById("printDiv").innerHTML;//获取打印部分
2、var win = window.open("","新建打印窗口","height=300,width=700,top=100");//新建窗口
3、win.document.body.innerHTML = newStr;//打印内容写到新建窗口中
4、 win.print();//执行打印

方式3：新建浏览器对话框中通过url获取内容
var url = "http://....";
1、var wind = window.open(url,"新建打印窗口","height=300,width=700");
2、 wind.print();
```
