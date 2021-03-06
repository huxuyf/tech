# 学习EJS

> 目标：看得懂EJS的脚本

## 一、EJS是什么？

`EJS`是一套简单的模板语言，利用`JavaScript`代码生成`HTML`页面。

`E`可以表示`可嵌入（Embedded）`，也可以是`高效（Effective）`、`优雅（Elegant）`，或者是`简单（Easy）`。

## 二、EJS的优势是什么？

- 纯JavaScript
- 快速开发
- 语法简单
- 执行迅速
- 易于调适
- 社区活动

## 三、EJS的重要特性

- 快速编译、输出

- 简洁的标签：`<% %>`

- 引入模板片段

- 同时支持服务器端和浏览器JS环境

  

## 四、EJS的语法

**标签的含义**

- `<%` '脚本' 标签，用于流程控制，无输出。
- `<%_` 删除其前面的空格符
- `<%=` 输出数据到模板（输出是转义 HTML 标签）
- `<%-` 输出非转义的数据到模板
- `<%#` 注释标签，不执行、不输出内容
- `<%%` 输出字符串 '<%'
- `%>` 一般结束标签
- `-%>` 删除紧随其后的换行符
- `_%>` 将结束标签后面的空格符删除



**举例**

```ejs
<% if (is_home() && page.current === 1) { %>
<%- partial('_partial/index-cover') %>
<% } else { %>
    <%- partial('_partial/bg-cover') %>
<% } %>
```

