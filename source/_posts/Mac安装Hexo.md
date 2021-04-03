---
title: Mac安装Hexo
date: 2021-04-03 16:26:48
tags:
---

Mac安装Hexo

Hexo -- https://hexo.io/

1.安装 hexo-cli
2.初始化到博客目录 hexo init
3.b博客目录下安装npm

brew install git,node

    npm install hexo-cli -g
    hexo init blog
    cd blog
    npm install
    hexo server
    
4.git配置帐号信息

git config --global user.name "chaphol"
git config --global user.email "chaphol86@gmail.com"

5.hexo关联github配置

创建SSH密钥
ssh-keygen -t rsa -C "chaphol86@gmail.com"

cat ~/.ssh/id_rsa.pub

ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQC2ZTBfLlN6C8RvQ+It9YRmEtDLx9KVC2mxdSemjcut04yUSO3zcYoDt9pDAZzUtLSYzJm8WHFCXLVL9tO5N7/JZ7FlPmt6OOzvryketKxcdF6zumyXTMSVIKDkNrYbA8W3WUxTgAcAuNaXAWej+GawSO80ekNBShvYiTRJC+sKRK52jdcQ3SBQrbjecTfzEx5p64RHeHgaIIzETtdKjHzHzUlOws7hSz7Ez57nIGZiTkQdZ3r/xmxlcxsZWt5ka/8/ZMyriJE+4ddo8FAnm+viVPttogDxPwHGnmndd94mXyjXtLczffq9QNsnaOC+Ck69e6TTDoqHH/njLiIx4bdym3v07v5FkDCLrxXkgzJ03R3LjboQc8+H82rw1EPeEMqncrl13fcFUkypneza3ZR+VyDwPiX7aKwkXiraXAfGgXSctJpYVlCnAsLTLaJOkZKNjTgDoYIj631VhYUnu5k7NvXhFxyg9mMjiMEyHcZCWV88C4P8ulDM+ZKRNqas3BM= chaphol86@gmail.com

添加到github设置里的ssh

用编辑器打开blog项目，修改_config.yml文件的一些配置（记得冒号后必须有空格，不然配置不生效，这是Hexo的一个坑！）

nano ~/blog/_config.yml 

deploy:
	type: 'git'
	repo: https://github.com/Chaphol/Chaphol.github.io.git
	branch: master


6.注意备份工程文件夹

7.上传编译后的站点到Github

安装Hexo上传仓库的工具
cd ~/blog
npm install hexo-deployer-git --save

执行命令（建议每次都这样做，先清除、再编译上传）

hexo clean
hexo generate
hexo deploy

删除文章
先删除本地文件，然后通过生成和部署命令进而将远程仓库中的文件也一并删除。

source / _post 文件夹中，在本地直接执行删除。再同步到服务器

hexo g
hexo d

在线博客
https://chaphol.github.io/

