# AIHelp H5 接入文档 
## 1. 引入 

**页面初始化（必须在页面初始化阶段调用）**<br />
**甲方有义务按照乙方接入文档说明的正常接入方式和调用方式使用乙方服务，如甲方通过技术手段影响乙方计费，乙方有权在通知甲方的同时立即单方面终止服务，并要求甲方承担责任。**<br />

1.1 移动端网页：
>在页面引入js文件

	https://aihelp.net/elva/elvah5/elvactrl.js
	
1.2 PC端网页： 
>在页面引入js文件

	https://aihelp.net/static/js/elvactrl.js
	
## 2. 创建初始化参数
在本地js文件中创建初始参数[object] 需要传入gameid,gameuid,gameName,username,language,hsTags,custom,autoEntrance等参数。

>示例:

	var elva_conf = {
		appId: `${appId}`,
		appName: `${appName}`,
		userUid: `${userUid}`,
		userName: `${userName}`,
		language: `${language}`,
		hsTags: `${hsTags}`,
    custom: `${custom}`,
		autoEntrance: `${autoEntrance}`
	}  

**说明:**<br />

appId: 不同平台的id,此处需使用web的appid. 必传项.<br />
appName: 应用名. 必传项.<br />
userUid: 用户id. 选传项,AIHelp会优先使用您所传的uid,若是uid为空,AIHelp会根据用户的设备与浏览器生成唯一id作为用户uid.<br />
userName: 用户名. 选传项,AIHelp会优先使用您所传的userName,AIHelp会将所有未传userName的用户命名为Unknown_User.<br />
language: 语言. 必传项,否则AIHelp会将当前用户语言默认为英语.<br />
hsTags: 标签. 选传项,会将所传标签在AIHelp客服后台客诉中显示.<br />
custom: 体验定制化. 选传项,可传值为1,2,3,4,5.分别对应以下5种体验：<br />

> **custom:"1"**:  默认进入FAQ列表页面，点击“联系客服”直接进入人工客服页面<br />
> **custom:"2"**:  默认进入人工客服页面<br />
> **custom:"3"**:  默认进入机器人客服页面<br />
> **custom:"4"**:  默认进入机器人客服页面，并且不显示页面右上角的“联系客服”入口<br />
> **custom:"5"**:  默认进入FAQ列表页面，并且不显示“联系客服”入口<br />
> **如果不传，则默认进入FAQ列表页面，点击“联系客服”进入机器人客服页面**
<br />

autoEntrance: 是否智能隐藏'人工客服'入口.选传项.是请传'1',将会智能隐藏入口,只有在用户提交表单或客服发送信息到用户后等一些情景下才会显示;否请传空,将常显'人工客服'入口.

    
**注： appId** 请使用注册邮箱登录 [AIHelp 后台](https://console.aihelp.net/elva)。在Settings菜单Applications页面查看。初次使用，请先登录[AIHelp 官网](http://aihelp.net/index.html)自助注册。<br />

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

PC端效果:

![PC效果图](https://github.com/AIHELP-NET/Pictures/blob/master/AIHelp-H5-on-PC(1).jpg "h5")

移动端效果:       **更多移动端接入方式,**[请戳这里](https://github.com/AI-HELP/H5-access-stable/blob/master/more_reference_CN.md)

![移动端效果图](https://github.com/AIHELP-NET/Pictures/blob/master/AIHelp-H5-on-mobile(1).jpg "h5")

代码示例：

![h5](https://github.com/AI-HELP/H5-access-stable/blob/master/AIHelp-H5-on-mobile(2).png "h5")
