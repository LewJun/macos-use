# macos-use

## 解决brew install 很慢
参考 [https://mirrors.tuna.tsinghua.edu.cn/help/homebrew/](https://mirrors.tuna.tsinghua.edu.cn/help/homebrew/)
### Homebrew 镜像使用帮助
注:该镜像是 Homebrew 的 formula 索引的镜像（即 brew update 时所更新内容）。本镜像站同时提供 Homebrew 二进制预编译包的镜像，请参考 Homebrew bottles 镜像使用帮助。

### 替换现有上游
cd "$(brew --repo)"
git remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/brew.git

cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core"
git remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-core.git

brew update
### 使用homebrew-science或者homebrew-python
(已经deprecated了)

cd "$(brew --repo)/Library/Taps/homebrew/homebrew-science"
git remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-science.git

cd "$(brew --repo)/Library/Taps/homebrew/homebrew-python"
git remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-python.git

brew update
### 复原
(感谢Snowonion Lee提供说明)

cd "$(brew --repo)"
git remote set-url origin https://github.com/Homebrew/brew.git

cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core"
git remote set-url origin https://github.com/Homebrew/homebrew-core

brew update
## nginx
### 配置反向代理

```
  1     #配置一个反向代理，当访问localhost:3333或192.168.1.234:3333时，转向到localhost:8888 
  2     server {
  3       listen  3333;
  4       server_name localhost 192.168.1.234;
  5 
  6       location / {
  7         proxy_pass http://localhost:8888;
  8       }
  9     }
```

### 在Mac上安装nginx

```
   
HuiYedeMacBook-Pro:~ huiye$ brew search nginx
==> Formulae
nginx
HuiYedeMacBook-Pro:~ huiye$ brew install nginx
Updating Homebrew...
==> Auto-updated Homebrew!
Updated 1 tap (homebrew/core).
==> New Formulae
atomist-cli         jmxterm             ruby@2.5            termtosvg
==> Updated Formulae
checkstyle                 http-parser                pgbadger
dcd                        imagemagick                swi-prolog
dfmt                       knot-resolver              tika
diamond                    laszip                     topgrade
docker-machine-parallels   ldc                        verilator
dscanner                   mariadb-connector-c        wtf
easyengine                 meson                      xonsh
get_iplayer                neovim                     ydcv
gobject-introspection      newsboat                   youtube-dl
grakn                      nnn
gzip                       node-build

==> Installing dependencies for nginx: pcre
==> Installing nginx dependency: pcre
==> Downloading https://homebrew.bintray.com/bottles/pcre-8.42.mojave.bottle.tar
######################################################################## 100.0%
==> Pouring pcre-8.42.mojave.bottle.tar.gz
🍺  /usr/local/Cellar/pcre/8.42: 204 files, 5.5MB
==> Installing nginx
==> Downloading https://homebrew.bintray.com/bottles/nginx-1.15.8.mojave.bottle.
######################################################################## 100.0%
==> Pouring nginx-1.15.8.mojave.bottle.tar.gz
==> Caveats
Docroot is: /usr/local/var/www

The default port has been set in /usr/local/etc/nginx/nginx.conf to 8080 so that
nginx can run without sudo.

nginx will load all files in /usr/local/etc/nginx/servers/.

To have launchd start nginx now and restart at login:
  brew services start nginx
Or, if you don't want/need a background service you can just run:
  nginx
==> Summary
🍺  /usr/local/Cellar/nginx/1.15.8: 23 files, 1.4MB
==> Caveats
==> nginx
Docroot is: /usr/local/var/www

The default port has been set in /usr/local/etc/nginx/nginx.conf to 8080 so that
nginx can run without sudo.

nginx will load all files in /usr/local/etc/nginx/servers/.

To have launchd start nginx now and restart at login:
  brew services start nginx
Or, if you don't want/need a background service you can just run:
  nginx
HuiYedeMacBook-Pro:~ huiye$ 
```
