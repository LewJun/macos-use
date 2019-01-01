# macos-use

## 在Mac上安装nginx

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
