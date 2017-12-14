# AIhelp H5 access document <br />
## 1. Import <br />
1.1 Mobile client: Import the js file on the page
<pre>https://aihelp.net/elva/elvah5/elvactrl.js </pre>
1.2 PC client: Import the js file on the page
<pre>https://aihelp.net/elvactrl.js</pre>
## 2. Create
Create initial parameters[object] in the local js file, incoming "gameid,gameuid,gameName,username,language,sdkVersion,hsTags" parameters.<br />
> Example: <br />
   <pre>
var elva_conf = {    <br />
    appId: 'TryElva_platform_14970be5-d3bf-4f91-8c70-c2065cc65e9a',<br />
    appName: `${appName}`,<br />
    userUid: `${userUid}`,<br />
    userName: `${userName}`,<br />
    language: `${language}`,<br />
    sdkVersion: `${sdkVersion}`,<br/>
    hsTags: `${hsTags}`<br />
  		}  <br />
    
Note: how to find the appid: Please log in [AIhelp backend](https://aihelp.net/elva) using your registered email, you can see the appid in the Settings->Applications page. If you have not yet registered an account, please visit [AIhelp official website](http://aihelp.net/index.html) to register account fisrt.<br />

## 3.	Put elva_conf in elvah5.init() Funtion
> Example <br />
   <pre>
if (typeof elvah5 !== undefined) {   <br />
    elvah5.init(elva_conf)   <br />
  }   <br />
## 4.	Call elvah5.show() Function
> Example：   <br />
   <pre>
btn.onclick = function () {   <br />
    elvah5.show()   <br />
  }   <br />
## 5.	Custom pop-up box style   <br />
> Example   <br />
   <pre>
      .show_AIhelp {   //Button style
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

        .elvaBox {    //Chat interface
            width: 375px;
            height: 500px;
            position: fixed;
            right: 1rem;
            bottom: 4rem;
        }


        .close {       //Close button (PC client)
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
</pre>
Example：

![h5](https://github.com/AI-HELP/Docs-Screenshots/blob/master/h5.png "h5")
