
## 开始用issue 写博客2016/10/18

### kit.js [(链接地址)](https://github.com/Kelichao/kit.js/blob/master/kit.js)

### 方法:借鉴底线库的工具框架，包含一些常用方法，在兼容AMD模式的同时，兼顾了CMD，在seaJS中也能够正常包装
<table>

<thead>
<tr>
	<td>XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX方法名称XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX</td>
	<td>使用方法</td>
</tr>
</thead>
<tbody>
<tr>
	<td >kit.method(obj)</td> 
	<td>为对象上挂载的函数体排序生成数组名，除去变量值,返回一个新数组</td>
</tr>
<tr>
	<td>kit.extend</td> 
	<td>通过浅复制，继承当前对象的方法，内部方法，多个对象属性继承用kit.mixin</td>
</tr>
<tr>
	<td>kit.CLIENT_USERID</td> 
	<td>客户端用户id,在浏览器中不存在,这个属性应该是由客户端设置</td>
</tr>
<tr>
	<td>kit.CLIENT_VERSION</td> 
	<td>客户端版本号，在浏览器中不存在,这个属性应该是由客户端设置</td>
</tr>
<tr>
	<td>kit.isArray(totle) </td> <td>判断是否为数组</td>
</tr>
<tr>
	<td>kit.isBoolean(totle)</td> <td>判断是否为布尔值</td>
</tr>
<tr>
	<td>kit.isFunction(totle)</td> <td>判断是否为函数</td>
</tr>
<tr>
	<td>kit.isString(totle)</td> <td>判断是否为字符串</td>
</tr>
<tr>
	<td>kit.isDate(totle)</td> <td>判断是否为日期</td>
</tr>
<tr>
	<td>kit.isNull(totle)</td> <td>判断是否为null(typeof null === "object")</td>
</tr>
<tr>
	<td>kit.isRegExp(totle)</td> <td>判断是否为正则</td>
</tr>
<tr>
	<td>kit.isNumber(totle)</td> <td>判断是否为数字</td>
</tr>
<tr>
	<td>kit.isUndefined(totle)</td> <td>判断是否是undefined</td>
</tr>
<tr>
	<td>kit.isError(totle)</td> <td>判断是否是Error</td>
</tr>
<tr>
	<td>kit.forEach(object/array, fn)/kit.each(object/array, fn)</td>
	 <td>负责用来遍历对象/数组属性,按照ES5标准，与jq参数位置不同</td>
</tr>
<tr>
	<td>kit.trim(string)</td>
	 <td>去除字符串两边的空格，如果有第二个参数，则把所有空格删除</td>
</tr>
<tr>
	<td>kit.locaSearch(key[, string])</td> 
	<td>例子："?getdate=2016-12-08&type=2"。第一个参数为需要取得的键值，
	第二个为需要解析成对象的地址串，
	如果不传为location.search</td>
</tr>
<tr>
	<td>kit.cookie(key[, string])</td> 
	<td>例子："aaa=123;bbb=456;ccc=678"。第一个参数为需要取得的键值
	（如果传入的是"" 或者null，则会打出整个键值对对象），
	第二个为需要解析成对象的地址串，如果不传为document.cookie，已经把末尾的分号“;”去除</td>
</tr>
<tr>
	<td>kit.clone</td> 
	<td>第一个参数为克隆对象，如果第二个参数是true则使用递归深度复制</td>
</tr>
<tr>
	<td>kit.query(selector)</td> 
	<td>封装了document.querySelector</td>
</tr>
<tr>
	<td>kit.querys(selector)</td> 
	<td>封装了docuemnt.querySelectorAll</td>
</tr>
<tr>
	<td>kit.ta(value[, type])</td> 
	<td>埋点快捷方式，
	传入对象{"ibyf130_3242": ".class1","iby2345_fre4": ".class2"} 进行dom绑定，
	如果传入数组，则是载入页面调用。如果有第二个参数,则可以自行设定触发方式</td>
</tr>
<tr>
	<td>kit.clientDown(name, url[, type])</td> 
	<td>快速调用客户端下载弹窗1：下载文件取名，2：文件下载地址(相对路径)，3：文件类型,需要加（.）。	type可选，如果url能够取到地址串，则不会被type覆盖，
	 如果地址串后面的url没有解析出类型，则会被type覆盖。例子： kit.clientDown("abc", "/thsft/Istrategy/abc.pdf", ".xls")</td>
</tr>
<tr>
	<td>kit.splitSpace(string)</td> 
	<td>按照空格分割字符串</td>
</tr>
<tr>
	<td>kit.once(fn)</td> 
	<td>执行一次函数包装器，返回一个新函数体</td>
</tr>
<tr>
	<td>kit.mixin( [deep ], target, object1 [, objectN ] )</td> 
	<td>拷贝属性的方法，第一个参数如果填布尔值则是深度复制，后面跟需要拷贝的对象，
	方法属性都会挂载到第一个对象target上面	</td>
</tr>
<tr>
	<td>kit.sort("asc"/"desc")</td> 
	<td>第一个参数如果是"asc"则是正序从小到大(默认), 如果是"desc",则倒叙，
	如果只传一个数组参数则进行正序排序</td>
</tr>
<tr>
	<td>kit.route(callback)</td> 
	<td>使用方法为传入一个函数参数，路由发生变化时就触发回调
	kit.route(fucntion(hash){console.log(hash)})。
	回调的第一个参数即hash值。注：hash值会改变浏览器历史记录</td>
</tr>
<tr>
	<td>kit.addScript(url[, callback])</td> 
	<td>动态加载脚本，兼顾了IE 6-8浏览器，第一个参数是地址，第二个参数可选，
	为脚本加载完毕后触发的回调</td>
</tr>
<tr>
	<td>kit.underToMustache()</td> 
	<td>启用Mustache.js类型模板语法，使用{{= }} 这样的语法</td>
</tr>
</tbody>
</table>
