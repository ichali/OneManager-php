[中文](readme_cn.md)  

# NOTICE: the release is used as archive. 

Please read the descriptions of settings before raising an issue.  

---

# Deploy to Heroku  

### Official

​	https://heroku.com  

### Demo

​	https://herooneindex.herokuapp.com/  

### How to Install

> ~~Click the button [![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy) to Deploy a new app~~(`"We couldn't deploy your app because the source code violates the Salesforce Acceptable Use and External-Facing Services Policy."`)  
>
> Star this project, then Fork, create a heroku app, then turn to the Deploy tab, "Deployment method" via "Connect GitHub", select your github fork.   

---

# Deploy to Glitch  

### Official

​	https://glitch.com/  

### Demo

​	https://onemanager.glitch.me/  

### How to Install

​	New Project -> Import form Github -> paste "https://github.com/qkqpttgf/OneManager-php", after done, Show -> In a New Window.  

---

# Deploy to Vercel  

### Official

​	https://vercel.com/  

### Demo

​	null

### Notice

> 1. you must wait 30-50s to make sure deploy READY after change config;  
>
> 2. Vercel limit 100 deploy every day.  

### How to Install

​	https://scfonedrive.github.io/Vercel/Deploy.html .  

---

# Deploy to Tencent Serverless Cloud Function (SCF 腾讯无服务器云函数)  

### Official

​	https://cloud.tencent.com/product/scf  

### DEMO

​	暂无  

### 注意事项

​	SCF新增限制，环境变量整体最大4KB，所以最多添加4个盘。  

### How to Install

1. 进入函数服务，上方选择地区，然后点击新建。

2. 输入函数名称，选择模板函数，在模糊搜索中输入onedrive，大小写随意，选择那个【获取onedrive信息.....】，点下一步，在代码界面不用动，直接点完成。

3. 点击触发管理，创建触发器，触发方式改成API网关触发，底下勾选启用集成响应，提交。

4. 在触发管理中可以看到一个 访问路径，访问它，开始安装。 

    （重点：**勾选集成响应**）  

> **添加网盘时，SCF可能会反应不过来，不跳转到微软，导致添加失败，请不要删除这个盘，再添加一次相同标签的盘就可以了。**

----


# Deploy to Huawei cloud Function Graph (FG 华为云函数工作流)  

### Official

​	https://console.huaweicloud.com/functiongraph/  

### DEMO

​	暂无

### 注意事项

​	FG中，环境变量整体大小为2KB，所以最多添加2个盘（一个onedrive一个aliyundrive）。  

### How to Install

1. 在函数列表，点右边创建函数  
2. 输入名称，选择运行时语言为PHP7.3，点上传ZIP文件，选择文件，然后点右边的创建函数（这里的ZIP文件不能直接用从Github上下载的ZIP文件，要将它解压后，去掉外层文件夹后，再压缩为ZIP。）  
3. 创建触发器：选API网关，安全认证选None，后端超时（毫秒）将5000改成30000，上面创建分组一下，其它的点点点  
4. 访问触发器给的url，开始安装
5. 在【触发器界面】点【触发器名称】，跳到API网关管理，右边【更多URL】，可以添加自定义域名，自定义域名后发现还是要 xxxx.com/函数名 来访问，点上方的【编辑】，第1页不用改，点【下一步】，**请求Path改成/**，注意匹配模式是前缀匹配，Method为ANY，然后不用点下一步了，点【立即完成】，然后去【发布】生效  

----

# Deploy to Aliyun Function Compute (FC 阿里云函数计算)  

### Official: 

​	https://fc.console.aliyun.com/  

### DEMO

​	无  

### How to Install

1. 新建函数 -- HTTP函数  
2. 运行环境选择php7.2  
3. 触发器认证方式选择anonymous，请求方式里面，点一下GET，再点一下POST，最终框框里面有这2个  
4. 上传代码  
5. 触发器中点进去，找到配置自定义域名，点击前往，创建，路径中填 /* ，其它下拉选择。
6. 访问你的域名，开始安装  

---

# Deploy to Baidu Cloud Function Compute (CFC 百度云函数计算)  

### Official

​	https://console.bce.baidu.com/cfc/#/cfc/functions  

### DEMO

​	暂无

### 注意事项

​	**自定义域名需要另外使用API网关，并备案。**

### How to Install

1. 在函数列表，点创建函数  
2. 创建方式改为空白函数，点下一步  
  3. 输入名称，选择运行时为PHP7.2，点下一步  
  4. 触发器：下拉选择HTTP触发器，URL路径填 /{filepath+} ，HTTP方法全选，身份验证：不验证，点提交  
  5. 进入代码编辑页，编辑类型改上传函数ZIP包，选择文件（这里的ZIP文件不能直接用从Github上下载的ZIP文件，要将它解压后，去掉外层文件夹后，再压缩为ZIP。），开始上传  
  6. 点击右边触发器，复制并访问提供的url，开始安装  

---

# Deploy to Virtual Private Server (VPS 或空间)  

### DEMO

null

### How to Install

1. Start web service on your server (httpd or other), make sure you can visit it.  

2. Make the rewrite works, the rule is in .htaccess file, make sure any query redirect to index.php.  

3. Upload code.  

4. Change the file .data/config.php can be read&write (666 is suggested).  

5. View the website in chrome or other.  

----

# Features  

​	When downloading files, the program produce a direct url, visitor download files from MS OFFICE via the direct url, the server expend a few bandwidth in produce.  

​	When uploading files, the program produce a direct url, visitor upload files to MS OFFICE via the direct url, the server expend a few bandwidth in produce.  

​	The XXX_path in setting is the path in Onedrive, not in url, program will find the path in Onedrive.  

​	LOGO ICON: put your 'favicon.ico' in the path you showed, make sure xxxxx.com/favicon.ico can be visited.   

​	Program will show content of 'readme.md' & 'head.md'.  

​	guest upload path, is a folder that the guest can upload files, but can not be list (exclude admin).  

​	If there is 'index.html' file, program will only show the content of 'index.html', not list the files.  

​	Click 'EditTime' or 'Size', the list will sort by time or size, Click 'File' can resume sort.  

----

# Functional files

### favicon.ico

put it in the showing home folder of FIRST disk (maybe not root of onedrive). 

### index.html

show content of index.html as html. 

### head.md

### readme.md

it will showed at top or bottom as markdown.

### head.omf

### foot.omf

it will showed at top or bottom as html (javascript works!). 

----

# A cup of coffee

https://paypal.me/qkqpttgf  

-----

# Chat

### Telegram Group

https://t.me/joinchat/I_RVc0bqxuxlT-d0cO7ozw  
