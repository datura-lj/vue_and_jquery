���裺
	------------------------
	��װ���ּܣ�
		1. vue init webpack-simple vue-jq
		2. cd vue-jq
		3. cnpm install
		4. ʹ��git bash��ֻ��Ϊ�˷��㣩
		5. package.json ���޸Ķ˿�  --port 8088
		6. npm run dev
	-------------------------
		1.ɾ��ԭ��û���õĴ���
			ps��chrome�е�[WDS]��webpack dev server�� ��˼ ���Ƿ���
				[HMR] hot ... �����ȼ��ص���˼
		2.�½�Ŀ¼�������ⲿjq��
		|--assets
		  |--js
			 |--fn.js
			 |--jquery-1.7.2.min.js
		  |--css
			 |--animate.css
			 |--1.css
		3. ������ļ�main.js����
			import './assets/css/animate.css';
			import './assets/css/1.css';

			import './assets/js/jquery-1.7.2.min.js';
		4.Ҫ��ҳ����ʹ��jq
		   1). npm install jquery --save-dev
		   2). ��webpack.base.conf.js����� ����
					 plugins: [
						new webpack.ProvidePlugin({
						  $: 'jquery',
						  jquery: 'jquery',
						  'window.jQuery': 'jquery',
						  jQuery: 'jquery'
						}),
					  ],
		   3). ��App.vue������ģ��
				import $ from 'jquery'
				import fn from './assets/js/fn.js';
		5. ����animate.css
			1). npm install style-loader --save-dev
			2). ��webpack.base.conf.js����� ����
				{
					test: /\.css$/,
					loader: 'style-loader!css-loader' //˳�����ģ�������ôд��֪����
				  },
	    6. ��дApp.vue�ļ���ʹ��jq��ʹ��vue�ṩ�ķ�����ȡԪ��
----------------------------------------------------------------------------------------
����ִ�в��裺
	1. cnpm install
	2. npm run dev