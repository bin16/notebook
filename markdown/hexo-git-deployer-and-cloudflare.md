搭建通过 Git 部署的 Hexo 博客，并通过 Cloudflare 加速访问
===============

本地安装 Hexo
------------------

看文档，此处略。

<https://hexo.io/zh-cn/docs/setup>


配置部署环境
-----------------

建议阅读：[使用 Git Hook 自动部署 Hexo 到个人 VPS][ref-1]

> 大家都知道 Git 是分布式的版本控制系统，远程仓库跟本地仓库是没有什么不同的。

嘛，我先前就不知道。

1. 安装 git 并创建 git user。
2. 把公钥复制进 /home/git/.ssh/authorized_keys
3. 找个地方放内容，也就是 work-tree 比如 /var/www/blog
4. 在 /home/git 下面新建一个裸仓库 `git init --bare blog.git`
5. 在 /home/git/blog.git/hooks 下面创建 post-receive
	``` bash
	#!/bin/sh
	git --work-tree=/var/www/blog --git-dir=/home/git/blog.git checkout -f
	```
6. `chmod +x post-receive` 赋予执行权限
7. `chmod -R 600 /home/git/.ssh` .ssh 目录应当只有该用户可访问
8. `chown -R git:git /home/git` 因为之前用到了 root 用户，安全起见确保文件 owner 是 git 用户
9. `chown -R git:git /var/www/blog` 修改内容目录 owner 为 git 用户
10. 禁用 `git` 用户的 shell 登录权限。 修改 `/etc/passwd` git 为 `git:x:1001:1001:,,,:/home/git:/usr/bin/git-shell`
11. 完成本地配置，略
12. 增加 nginx 配置，略

配置 Cloudflare
------------------

1. 建立 Cloudflare 用户，建立站点
2. 修改域名的 DNS 服务器为 Cloudflare 提供的值
3. 在 Cloudflare 解析你的域名到你的服务器
4. 理论上这里还需要你在服务器上获取 SSL 证书的吧？
5. 在 Cloudflare 开启 SSL

参考文档
-----------

[使用 Git Hook 自动部署 Hexo 到个人 VPS][ref-1]



[ref-1]: http://www.swiftyper.com/2016/04/17/deploy-hexo-with-git-hook/
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1OTU1NDY0NjVdfQ==
-->