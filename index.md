##Lint是检查代码格式工具的一个统称，具体的有Eslint ,Jslint等
## ESLint是一个用来识别ECMAScript并且按照规则给出报告的代码检测工具,
使用它可以避免低级错误和统一代码风格，ESLint被设计为完全可配置的，主要有两种方式来配置：

##使用js注释直接把配置嵌入到JS文件中
##配置文件：使用下面任一的文件来为全部的目录和它的子目录指定配置信息
1.js :使用.eslintrc.js文件并导出一个包含配置的对象
2.yaml:.eslintcr.yaml /eslintcr.yam
3.json:.eslintrc.json  并且此文件允许使用js形式的注释
4.package.json:在文件中创建eslintConfig属性
##如上的优先级：顺序即可

###可以被配置的信息可以分为三类：
1.Environments:js code运行环境

```js
module.exports= {
	env:{
		browser:true,
		node:true
	},
	globals:{
		var1:true,
		var2:true
	},
	rules:{
		curly:'error'
	}
}
```
2.globals：代码执行的时候，访问的格外的局部变量
```js
/*global var1:false,var2:false*/
```
3.Rules:开启某些规则
规则的等级有三种：
1).off 或者0:关闭规则
2).warn /1:打开规则，并且作为一个警告
3).error /2:打开规则，并且作为一个错误

##ESLint使用方法
1）通过命令行来使用
2)编辑器 配合相应的插件，在vscode中直接显示错误和警告



在package.json中使用脚本：
"scripts":{
	"lint":"eslint src"//在scr这个文件夹下进行
}
