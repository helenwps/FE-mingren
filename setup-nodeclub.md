### 参考

跳转@老赵 博客[使用Jscex改进Node Club（1）：运行Node Club网站][blog]

[blog]: http://blog.zhaojie.me/2012/02/jscexify-nodeclub-1-prepare-nodeclub-website.html

后来增加了运行 `make build` 生成 assets 文件的一个步骤:

https://github.com/cnodejs/nodeclub/issues/194

### 大致流程

* 预备 Node, MongoDB 环境, Unix(Mac, Linux 等) 环境更好..
* 一个邮箱用来发送激活邮件等..
* `cp config.default.js config.js` 并且编辑 `config.js` 加入配置
* `make build` 生成一些静态资源
* 启动 MongoDB 和 `node app.js` 启动论坛
* 注册名为 `admin` 的账户, 触发管理员权限

