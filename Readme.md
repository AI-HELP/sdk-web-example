[Integration Guide In Chinese](https://github.com/AI-HELP/H5-access-stable/blob/master/README_CN.md)

# AIhelp HTML5 Integration Guide
## 1. Import

**Party A is obliged to use Party B's services according to the correct plug-in method and calling method described by Party B's documents. If Party A uses any technical method to influence Party B's billing, Party B will have the right to notify Party A while unilaterally terminating the service immediately and ask Party A to assume responsibility for infulencing the billing of Party B.**<br />

1.1 For Mobile Web Page:
>import below js file to your mobile web page

	https://aihelp.net/elva/elvah5/elvactrl.js
	
1.2 For PC Web Page： 
>import below js file to your PC web page

	https://aihelp.net/static/js/elvactrl.js
	
## 2. Create Initial Parameters.

You need to create inital parameters [boject] in your local js files by:

Passing in below parameters: 
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
    
**introduction:**<br />

appId: The id of different platforms, here you need to use the web appid. Required filed.<br />

appName: Application name. Required filed.<br />

userUid: User id. Optional filed,AIHelp will give priority to the userUid you pass. If the userUid is empty, AIHelp will generate a unique useUid based on the user's device and browser as the user's userUid.<br />

userName: Optional filed,AIHelp will give priority to the userName you passed. AIHelp will name all users who's username was not passed as Unknown_User.<br />

language: Required filed,Otherwise AIHelp will take the current user language as English.<br />

hsTags: Tag. Optional filed,The tag will be displayed in "Conversation-Userdata" in AIHelp back-end<br />

autoEntrance: It decides if the 'manual customer service' entrance is hidden or not. Optional filed. If you want it to be hidden, please write '1', the entrance will be hidden and will only be displayed after the user submits the form or the customer service sends a message to the user. If you don't want it to be hidden, please set it blank and it will always be displayed and players are able to see it and reach to customer service all the time.


**Note:** Please log in AIHelp with your registered account to find appId of Web In the Application page of the Settings Menu. If your company doesn't have an account yet, please egister one on [AIHelp Website](http://aihelp.net/index.html). 

## 3.	use elvah5.init() to pass initialized parameter

>Coding Example:

	if (typeof elvah5 !== undefined) { 
		elvah5.init(elva_conf)     
	} 
  
## 4. use elvah5.show() function

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

Performance on PC：

![Rendering on PC](https://github.com/AIHELP-NET/Pictures/blob/master/AIHelp-H5-on-PC(1).jpg "h5")

Performance on mobile:        **For more access methods on mobile ,**[click me](https://github.com/AI-HELP/H5-access-stable/blob/master/more_reference_EN.md).

![Rendering on mobile](https://github.com/AIHELP-NET/Pictures/blob/master/AIHelp-H5-on-mobile(1).jpg "h5")

Example：

![h5](https://github.com/AIHELP-NET/Pictures/blob/master/AIHelpH5.jpg "h5")
