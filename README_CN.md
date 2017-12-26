# AIhelp H5 接入文档 
## 1. 引入 

1.1 移动端： 在页面引入js文件

	https://aihelp.net/elva/elvah5/elvactrl.js
	
1.2 PC端网页： 在页面引入js文件

	https://aihelp.net/static/js/elvactrl.js
	
## 2. 创建初始化参数
在本地js文件中创建初始参数[object] 需要传入gameid,gameuid,gameName,username,language,sdkVersion,hsTags等参数。

>示例:

	var elva_conf = {
		appId: 'TryElva_platform_14970be5-d3bf-4f91-8c70-c2065cc65e9a',
		appName: '${appName}',
		userUid: '${userUid}',
		userName: '${userName}',
		language: '${language}',
		sdkVersion: '${sdkVersion}',
		hsTags: '${hsTags}'
	}  
    
注：appid: 请使用注册邮箱登录 [AIhelp 后台](https://console.aihelp.net/elva)。在Settings菜单Applications页面查看。初次使用，请先登录[AIhelp 官网](http://aihelp.net/index.html)自助注册。<br />

## 3.	调用elvah5.init()传入初始化参数
>示例:

	if (typeof elvah5 !== undefined) { 
		elvah5.init(elva_conf)     
	} 
  
## 4.	调用elvah5.show() 函数
在页面UI事件响应函数中，调用elvah5.show()弹出elva盒子
> 示例:

	btn.onclick = function () { 
		elvah5.show()  
	}

## 5.	自定义弹出elva盒子的样式
> 示例:

	.show_AIhelp {   //按钮样式
		position: fixed;
		bottom: 1rem;
		right: 1rem;
		border-radius: 4px;
		border: none;
		padding: 10px 30px;
		background: #f9c633;
		color: #444;
		outline: none;
	}

	.elvaBox {    //聊天界面
		width: 375px;
		height: 500px;
		position: fixed;
		right: 1rem;
		bottom: 4rem;
	}


	.close {   //关闭按钮（PC端网页）
		position: absolute;
		right: -10px;
		top: -16px;
		width: 30px;
		height: 30px;
		background: #f9c633;
		border-radius: 25px;
		cursor: pointer;
	}
	
	.close:hover {
		background: #bbb;
		transition: all .3s ease;
	}

	.close:before {
		position: absolute;
		content: '';
		width: 20px;
		height: 2px;
		background: #444;
		transform: rotate(45deg);
		top: 14px;
		left: 6px;
	}

	.close:after {
		content: '';
		position: absolute;
		width: 20px;
		height: 2px;
		background: #444;
		transform: rotate(-45deg);
		top: 14px;
		left: 6px;
	}

图示：

![h5](https://github.com/AI-HELP/Docs-Screenshots/blob/master/h5.png "h5")
