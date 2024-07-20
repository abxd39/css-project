

npm init 命令 生产 package.json 包

在package script 中加入
 "server": "live-server ./ --port=8181 --host=localhost --proxy=/api:http://www.abc.com/api/",
 执行命令

 npm run server