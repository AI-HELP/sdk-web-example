[Integration Guide In Chinese](https://github.com/AI-HELP/H5-access-stable/blob/master/README_CN.md)

# AIhelp HTML5 Integration Guide
## 1. Import

1.1 On Mobile Web Page:
>import below js file

	https://aihelp.net/elva/elvah5/elvactrl.js
	
1.2 On PC Web Page： 
>import below js file

	https://aihelp.net/static/js/elvactrl.js
	
## 2. Create Initial Parameters.

You need to create initial parameters [object] in your local js files. 

Pass in below parameters: 
"gameid,gameuid,gameName,username,language,hsTags,autoEntrance" etc. 

>Coding Example:

	var elva_conf = {
		appId: `${appId}`,
		appName: `${appName}`,
		userUid: `${userUid}`,
		userName: `${userName}`,
		language: `${language}`,
		hsTags: `${hsTags}`,
		autoEntrance: `${autoEntrance}`
	}  
    
**interpretation:**<br />

appId: The id of different platforms, here you need to use the web appid. Required.<br />

appName: Application name. Required.<br />

userUid: User id. Optional,AIHelp will give priority to the userUid you wrote. If the userUid is empty, AIHelp will generate a unique identifier based on the user's device and browser as the user userUid.<br />

userName: Optional,AIHelp will give priority to the userName you passed. AIHelp will name all users who have not passed userName as Unknown_User.<br />

language: Required,Otherwise AIHelp will default the current user language to English.<br />

hsTags: Tag. Optional,The tag will be displayed in the AIHelp customer service back-end complaint.<br />

autoEntrance: Whether to intelligently hide the 'manual customer service' entrance.Optional.If you want to open, please write '1', it will hide the entrance intelligently. It will only be displayed after the user submits the form or the customer service sends the information to the user. Otherwise, please set it blank and it will always display the 'manual customer service' entrance.


**Note:** Please log in [AIHelp Web Console](https://console.aihelp.net/elva) with your registration email account to find __appId__ of Web In the _Application_ page of the _Settings_ Menu. 
If your company doesn't have an account, you need to register an account in [AIHelp Website](http://aihelp.net/index.html). 

## 3.	call method elvah5.init() with "elva_conf"

>Coding Example:

	if (typeof elvah5 !== undefined) { 
		elvah5.init(elva_conf)     
	} 
  
## 4. call method elvah5.show() 

In your page's UI event handler, call elvah5.show to show elva box.

> Coding Example

	btn.onclick = function () { 
		elvah5.show()  
	}

## 5. Customerize the style of your elva box.  
> Coding Example


	.elvaBox {    //chat interface 
		width: 375px;
		height: 500px;
		position: fixed;
		right: 1rem;
		bottom: 4rem;
	}


	.close {   //close button（PC Web Page）
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

Rendering on PC：

![Rendering on PC](https://github.com/AIHELP-NET/Pictures/blob/master/AIHelp-H5-on-PC(1).jpg "h5")

Rendering on mobile:        **For more access methods on mobile side,[click me]**(https://github.com/AI-HELP/H5-access-stable/blob/master/more_reference_EN.md).

![Rendering on mobile](https://github.com/AIHELP-NET/Pictures/blob/master/AIHelp-H5-on-mobile(1).jpg "h5")

Code Example：

![h5](https://github.com/AIHELP-NET/Pictures/blob/master/AIHelpH5.jpg "h5")
