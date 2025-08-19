laravel10 + vue3 + element-ui的后台极速开发框架，采用前后端分离架构，

安全性 (JWT 校验、中间件、验证器、路由、异常处理、权限控制)

网址：https://download.notestore.cn/20231212/ 账号：admin 密码：admin

注意事项：
后端项目部署，尽量用域名，不要用php artisan serve，启用后端项目，否则会出现后台无法登录问题

输入图片说明

服务器环境：
PHP8.2 [已测]

Mysql 5.740 [已测]

目录结构：
/backend （后端目录）

/frontend （前端目录）

/resource （资源目录，包含数据库以及安装说明以及相关截图）

快速安装：
创建MYSQL数据库，导入/resource/数据库.v10.sql

修改 .env 配置 APP_URL、DB_开头的配置

设置 public 目录作为 web目录访问内容

配置伪静态 location / { try_files uri
uri/ /index.phpisargs
query_string; }

后台入口 你的网址/admin，账号密码 admin admin

后端命令行安装（非必须）
php artisan migrate #第一步：安装数据表

php artisan generate:cms #第二步：添加demo数据

php artisan key:generate #第三步：生成APP_KEY

php artisan passport:keys --force #第四步：生成oauth密钥

php artisan storage:link #第五步：创建目录软连接

php artisan passport:client --password --provider=admins #第六步：生成OAuth令牌

复制生成OAuth令牌参数，到.env文件中的PASSPORT_CLIENT_ID PASSPORT_CLIENT_SECRET

chown -R 777 storage #更改权限目录

安装依赖 （非必须）
由于众所周知的原因，国外的网站连接速度很慢。因此安装的时间可能会比较长，我们建议使用国内镜像 （腾讯云）。

composer config -g repos.packagist composer https://mirrors.cloud.tencent.com/composer/

根目录执行

composer update 或者 composer install

前端环境配置：
打开frontend/config/dev.env.js，并全局搜索 http://139.155.45.209:84/ 并替换域名为 你的后端域名，注意后面，要有反斜杠结尾

前端一键安装：
npm install --registry=https://registry.npm.taobao.org

npm run dev #本地热开发

npm run build:prod #打包编译

编译并覆盖
npm run build:prod && \cp -r -f dist/* ../backend/public/admin/

<a href="https://pan.notestore.cn/laravel/24.html">已购50+，自动发货，无需等待</a>
