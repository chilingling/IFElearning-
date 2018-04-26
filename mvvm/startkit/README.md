# 搭建开发环境
#### 基础
- 准备一个文件夹存放你的项目
- npm init -y 初始化你的项目
- 安装webpack  `npm install webpack -g`  `npm install webpack-cli -g`
- 将webpack链接至该项目中 `npm link webpack --save-dev`, `npm link webpack-cli --save-dev`
- 使用默认配置,在src文件夹下面新建index.js作为入口文件
- 写点东西测试一下  
	```Javascript
	import san from 'san'; //引入san
	var MyApp = san.defineComponent({
	template: '<p>Hello {{name}}!</p>',
	initData: function() {
		return {
			name: 'san'
		};
		}
	});
	var myApp = new MyApp();
	myApp.attach(document.body);
	```
- 使用命令行打包： 开发环境 `webpack --mode development`；生产环境`webpack --mode production` 
- 测试成功
- []!(../)

#### 进阶
- 建立配置文件`webpack.config.js` 
- 引入解析html、CSS、JS、图片的loader，首先需要通过npm安装他们

```Javascript
	npm install babel-core babel-loader babel-preset-env css-loader style-loader html-loader file-loader 
```

-  配置babel-loader的代码转换,新建 .babelrc文件
```javascript
	{
		"presets":["env"]
	}
```
- 配置 webpack.config.js 文件
- 在npm scripts中设置dev命令 `webpack --mode development`
- 测试：可以看到打包成功
#### 自动化&调试
- 需要准备的：html-webpack-plugin html(自动生成html文件并引入生成的js文件)、webpack-dev-server (webpack自带的一个server)，将他们全部npm install
- 