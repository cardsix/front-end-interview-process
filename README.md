# front-end-interview-process

我觉得每一个前端开发工程师上辈子都是断翼的天使。最近一直在找前端开发工程师的岗位，也是很艰辛，希望能够通过这个纪录自己在前端面试过程中遇到的困难或者自己在学习上遇到的问题。

# HTML 篇

#### 1.块级元素有哪些，行内元素有哪些？

块级元素：div p h1-h6 form ul ol

行内元素：a b br i span input select

#### 2.position有哪些属性，分别有什么含义


# CSS 篇

#### 1.通过css实现一个三列布局，左右宽度固定，中中间的内容宽度自适应，并且两边元素的高度随着中间元素的高度变化而变化

#### 2.import和link有什么区别

1)link是XHTML标签，除了加载CSS外，还可以定义RSS等其它事务；@import属于CSS范畴，只能加载CSS。

2）link引用CSS时，页面载入时同时加载；@imprt需要页面完全载入之后才会加载。

3）link是XHTML标签，没有兼容问题，@import是CSS2.1提出的，低版本浏览器不支持。

4）link支持使用 javascript控制DOM去改变样式，而@import不支持。



# javascript篇

#### 1.通过js实现一个函数找到字符串中出现次数最多的字符

#### 2.如何实现深度克隆

#### 3.如何解析一个url，http://baidu.com?name=123&age=123#secion解析query的内容

#### 4.有如下一份伪json文件：

```javascript
{
     "name": "qiniu",
     "location": "shanghai", // in shanghai
     "tags": ["#golang", "//tech", "/\\\"//enthusiasm\"/"], // //manytags
     // a comment line
     "property": {
       // these are properties
       "products":["/storage//", "cdn", "/data/processing/", "////live///"] //4 products
     }
}
```

现在要实现一个解析器，将上述文件转化为合法的json文件，即去掉注释，上述文件转化为：

```javascript
{
     "name": "qiniu",
     "location": "shanghai",
     "tags": ["#golang", "//tech", "/\\\"//enthusiasm\"/"], 
     "property": {
       "products":["/storage//", "cdn", "/data/processing/", "////live///"] 
     }
}
```

#### 5.document.write和innerHtml有什么区别

document.write是直接写入到页面的内容流，如果在写之前没有调用documen.open，浏览器自动调用open。每次写完关闭之后重新调用该函数，会导致页面被重写。

innerHTML则是页面元素的一个属性，代表该元素的html内容。你可以精确到一个具体的元素来进行修改。

innerHTML很多情况优于document.write，其原因在于其允许更精确的控制要刷新页面的一个部分。

#### 6.实现一个flatten函数

```javascript
function flatten(arr) {
	var result = [];
	var len = arr.length;
	for (var i = 0; i < len;i ++) {
		var ele = arr[i];
		if (ele.length === 1 || !Array.isArray(ele)) {
			result.push(ele);
		} else {
			var temp = flatten(ele);
			result = result.concat(temp);
		}
	}
	return result;
}
```

#### 7.如何判断数组

1)instanceof 但是在IE上不一定成功

2）isArray方法

3）使用数组的内部属性

```javascript
fuction isArray(arr) {
  return toString.apply(arr) === '[object Array]';
}
```



# 性能篇

1. 为什么要对js文件进行打包



# 框架

1. jquey是如何实现选择器的
2. undescore里面的template方法



# 其它问题

1. 有没有阅读过什么框架的源码