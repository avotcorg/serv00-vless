免费空间网站：https://www.serv00.com/

1、打开免费提供空间的网站后，注册一个账号，只需要有个真实邮箱能收验证邮件就行，没什么门槛非常方便，注册成功后按收到的邮件里信息登录网站后台面板，面板地址、用户名、密码之类的建议保存一下；
网站首页.png


2、利用这个serv00-vless的github项目指导一步步设置好面板里的各项，分别是:

点WWW Websites，创建一个网站项目，网站类型选择：node.js
点Port reservation，开通一个随机端口
下载此github项目的文件并上传至面板的文件管理自己创建项目的域名文件夹下的public-nodejs目录下
打开app.js文件，修改UUID和端口并保存好
serv00-vless的项目地址：https://github.com/avotcorg/serv00-vless/
添加node.js.png
文件管理.png


3、解析域名a记录，IP为面板的SSL--WWW Websites查看的第1个；

4、SSH登录，用户名密码跟面板一致，连接地址在邮件里可以查看到，端口号默认22
如果使用电脑WINDOWS系统自带的“终端”连接命令：
ssh 用户名@连接地址 -p 22
然后再输密码即成功登录
注意如果使用finalshell软件连接可能会提示密码错误，先点取消会弹出另一个对话框提示再输入密码即可成功登录
切换当前工作目录:
cd /usr/home/自己的用户名/domains/自己的域名/public_nodejs
先安装依赖项及启动Node.js 应用程序:
npm install
npm start
再在screen会话中，运行应用程序:
screen -S mysession
node app.js
最后按下 Ctrl + A，然后按下 D 键将 screen 会话分离，这样关闭终端窗口后，应用程序将继续在后台运行。
终端SSH.png
finalshell.png

5、打开客户端的代理软件，自定义添加一个vless节点，填入域名、端口号、UUID、伪装域名，传输协议选择ws即可测试该节点直连的真连接是否有延迟返回；
v2rayN新增vless节点.png
