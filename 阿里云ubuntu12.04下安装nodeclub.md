1. 首先确保已经正确安装了node和mongodb，安装方法见

2. 安装forever模块，用于在后台运行node.js程序和代码热部署

        npm install forever -g
        
3. 获取nodeclub源码并存入我们自己的项目目录

        git clone https://github.com/cnodejs/nodeclub.git myapp

4. 进入项目目录
        
        cd myapp

5. 复制config.default.js并重命名为config.js
6. 编辑config.js

    将
    
        debug: true
        
    改为
    
        debug: false
        
    因为调试模式下不能发邮件
    
    ---
    
    将
    
        name: 'Node Club',
        description: 'Node Club 是用Node.js开发的社区软件',
        
    改为
    
        name: '你的网站名称',
        description: '你的网站描述',

    ---
    
    将
    
        host: 'localhost.cnodejs.org'
        
    改为
    
        host: '你网站的实际ip或域名'

    ---
    
    将
    
        site_google_search_domain:  'cnodejs.org'
        
    改为
    
        site_google_search_domain: '你网站的实际ip或域名'
    
    ---
    
    将
    
        db: 'mongodb://127.0.0.1/node_club_dev'
        
    改为
    
        db: 'mongodb://127.0.0.1/你网站数据库的实际名称'
        
    ---
    
    将
    
        session_secret: 'node_club',
        auth_cookie_name: 'node_club',
        
    改为
    
        session_secret: '你自己的标识',
        auth_cookie_name: '你自己的标识',
        
    --- 
    
    将
    
        rss: {
            title: 'CNode：Node.js专业中文社区',
            link: 'http://cnodejs.org',
            language: 'zh-cn',
            description: 'CNode：Node.js专业中文社区',
        
            //最多获取的RSS Item数量
            max_rss_items: 50
        },
    
    中的信息改成你网站的相关信息
    
    ---
    
    将
    
          mail_opts: {
            host: 'smtp.126.com',
            port: 25,
            auth: {
              user: 'club@126.com',
              pass: 'club'
            }
          },
          
    中的host、port、user、pass等信息改成你的邮箱信息，然后保存，退出编辑
    
7. 输入命令

        npm install
        
    进行安装
    
8. 安装完毕之后，输入命令
    
        forever start -w app.js

    启动程序
    
在浏览器中访问一下 你的域名或ip:端口号，如果能看到NodeClub空白站点，则表示网站已经安装成功。
