# HTML学习

- HTML头部
- HTML CSS
- 图像、表格、列表、区块
- 布局
- 表单和输入
- 框架
- 脚本
- 字符实体、URL

---

## HTML头部

- HTML\<head>元素内可以添加的标签有`<title>` `<style>` `<meta>` `<link>` `<script>` `<noscript>` `<base>`。
- `<title>`是文档的标题，是必须的。
- `<base>`定义了页面链接标签的默认链接地址。（href:"URL"基准URL）（target:"\_blank/\_top"规定超链接和表单在何处打开）
- `<link>`定义了文档和外部资源的关系。（href:"URL"定义被链接文档的位置）（rel:""定义当前文档和被链接文档的关系）（type:"text/css"定义被链接的样式文件）
- `<meta>`描述文档的元数据。（charset="UTF-8"定义文档的字符编码）（http-equiv="refresh"刷新页面）（name="application-name / author / description / generator / keywords"把content属性关联到一个名称）（content=""定义前两者相关的元信息）
- `<script>`可以包含脚本语句，也可以通过`src:"URL"`指向外部脚本文件。
- `<style>`定义了文档的样式信息。（type="text/css"规定样式表类型）

---

## HTML CSS

- 通过`<style>` `<link>`调用内部样式表和外部样式表。

- 内部样式表

    > <head>
    >     <style type="text/css">
    >         body{...}
    >         p{...}
    >     </style>
    > </head>

    

- 外部样式表

    > <head>
    >     <link rel="stylesheet" type="text/css" href="<fliename>.css">
    > </head>

---

## 图像、表格、列表、区块

### 图像

- `<img>`定义了图像，`src="URL"`指向图片位置，`alt="text"`定义一串可替换的文本，`width="value"` `height="value"`定义图片的长宽。

    > \<img src="URL" alt="text" width="value" height="value">

### 表格

- 表格由` <table> `标签来定义。每个表格均有若干行（由 `<tr> `标签定义），每行被分割为若干单元格（由 `<td> `标签定义）。数据单元格可以包含文本、图片、列表、段落、表单、水平线、表格等等。表格边框使用`border="1"`定义。 表格的表头使用` <th>` 标签进行定义。  表格的标题使用 `<caption>` 标签进行定义。 

    >  \<table border="1">
    >       \<tr>
    >           \<th>Header 1</th>
    >           \<th>Header 2</th>
    >       \</tr>
    >       \<tr>         
    >           \<td>row 1, cell 1\</td>    
    >           \<td>row 1, cell 2\</td>   
    >       \</tr>
    >       \<tr>
    >           \<td>row 2, cell 1</td>      
    >           \<td>row 2, cell 2</td> 
    >       \</tr> 
    > \</table>  

### 列表

-  HTML 支持有序、无序和定义列表: 

    -  无序列表使用` <ul> `标签 

        > \<ul>
        > \<li>text1\</li>
        > \<li>text2\</li>
        > \</ul> 

        

    -  有序列表始于\ <ol> 标签。每个列表项始于 \<li> 标签。列表项使用数字来标记。

        >  \<ol>
        > \<li>text1\</li>
        > \<li>text2\</li>
        > \</ol> 

    - 自定义列表以 \<dl> 标签开始。每个自定义列表项以\ <dt> 开始。每个自定义列表项的定义以 \<dd> 开始。

        >  \<dl>
        > \<dt>text1\</dt>
        > \<dd>- todo1\</dd>
        > \<dt>text2\</dt>
        > \<dd>- todo2\</dd>
        > \</dl> 

### 区块

- HTML \<div> 元素是块级元素，它可用于组合其他 HTML 元素的容器。

    \<div> 元素没有特定的含义。除此之外，由于它属于块级元素，浏览器会在其前后显示折行。

    如果与 CSS 一同使用，\<div> 元素可用于对大的内容块设置样式属性。

- HTML \<span> 元素是内联元素，可用作文本的容器

    \<span> 元素也没有特定的含义。

    当与 CSS 一同使用时，\<span> 元素可用于为部分文本设置样式属性。

---

## 布局

- 使用\<div>布局

    > \<!DOCTYPE html>
    > \<html> 
    >
    >     <head> 
    >         <meta charset="utf-8">  
    >         <title>title</title>  
    >     </head> 
    > ​    \<body>  
    >     <div id="container" style="width:500px">  
    >      <div id="header" style="background-color:#FFA500;"> 
    >       <h1 style="margin-bottom:0;">主要的网页标题</h1></div> 
    >             <div id="menu" style="background-color:#FFD700; height:200px; width:100px; float:left;"> 
    >                 <b>菜单</b><br> HTML<br> CSS<br> JavaScript</div>
    >             <div id="content" style="background-color:#EEEEEE; height:200px; width:400px;float:left;"> 内容在这里</div> 
    >             <div id="footer" style="background-color:#FFA500;clear:both;text-align:center;"> footer</div>  
    >         </div>  
    > ​    \</body>
    > \</html>  

- 使用\<table>布局

    >  \<!DOCTYPE html>
    > \<html>
    >
    >     <head>  
    >         <meta charset="utf-8"> 
    >         <title>title</title> 
    >     </head>
    > ​    \<body>  
    >         <table width="500" border="0">
    >             <tr> 
    >                 <td colspan="2" style="background-color:#FFA500;"> 
    >                     <h1>主要的网页标题</h1> 
    >                 </td>
    >             </tr> 
    >             <tr> 
    >                 <td style="background-color:#FFD700;width:100px;"> 
    >                     <b>菜单</b><br> HTML<br> CSS<br> JavaScript 
    >                 </td> 
    >                 <td style="background-color:#eeeeee;height:200px;width:400px;"> 内容在这里</td>
    >             </tr>  
    >             <tr> 
    >                 <td colspan="2" style="background-color:#FFA500;text-align:center;"> footer</td> 
    >             </tr> 
    >         </table> 
    > ​    \</body> 
    > \</html>  

---

