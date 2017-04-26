步骤：
	------------------------
	安装脚手架：
		1. vue init webpack-simple vue-jq
		2. cd vue-jq
		3. cnpm install
		4. 使用git bash（只是为了方便）
		5. package.json 中修改端口  --port 8088
		6. npm run dev
	-------------------------
		1.删除原来没有用的代码
			ps：chrome中的[WDS]是webpack dev server的 意思 就是服务
				[HMR] hot ... 就是热加载的意思
		2.新建目录，引入外部jq库
		|--assets
		  |--js
			 |--fn.js
			 |--jquery-1.7.2.min.js
		  |--css
			 |--animate.css
			 |--1.css
		3. 在入口文件main.js引入
			import './assets/css/animate.css';
			import './assets/css/1.css';

			import './assets/js/jquery-1.7.2.min.js';
		4.要在页面中使用jq
		   1). npm install jquery --save-dev
		   2). 在webpack.base.conf.js中添加 配置
					 plugins: [
						new webpack.ProvidePlugin({
						  $: 'jquery',
						  jquery: 'jquery',
						  'window.jQuery': 'jquery',
						  jQuery: 'jquery'
						}),
					  ],
		   3). 在App.vue中引入模块
				import $ from 'jquery'
				import fn from './assets/js/fn.js';
		5. 解析animate.css
			1). npm install style-loader --save-dev
			2). 在webpack.base.conf.js中添加 配置
				{
					test: /\.css$/,
					loader: 'style-loader!css-loader' //顺序定死的，必须这么写，知道吗？
				  },
	    6. 编写App.vue文件，使用jq，使用vue提供的方法获取元素
----------------------------------------------------------------------------------------
懒人执行步骤：
	1. cnpm install
	2. npm run dev