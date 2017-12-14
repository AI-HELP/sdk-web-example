[Integration Guide In Chinese](https://github.com/AI-HELP/H5-access-stable/blob/master/README_CN.md)

# AIhelp HTML5 Integration Guide
## 1. Import

1.1 On Mobile Web Page: import below js file

	https://aihelp.net/elva/elvah5/elvactrl.js
	
1.2 On PC Web Page： import below js file

	https://aihelp.net/elvactrl.js
	
## 2. Create Initial Parameters.

You need to create initial parameters [object] in your local js files. 

Pass in below parameters: 
"gameid,gameuid,gameName,username,language,sdkVersion,hsTags" etc. 

>Coding Example:

	var elva_conf = {
		appId: 'TryElva_platform_14970be5-d3bf-4f91-8c70-c2065cc65e9a',
		appName: '${appName}',
		userUid: '${userUid}',
		userName: '${userName}',
		language: '${language}',
		sdkVersion: '${sdkVersion}',
		hsTags: '${hsTags}'
	}  
    

Note: Please log in [AIHelp Web Console](https://aihelp.net/elva) with your registration email account to find __appId__ of Web In the _Application_ page of the _Settings_ Menu. 
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

	.show_AIhelp {   //button style 
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

Example：

![h5](https://github.com/AI-HELP/Docs-Screenshots/blob/master/h5.png "h5")
