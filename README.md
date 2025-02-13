# 联机斗地主

支持三人(一副牌3底牌)、四人(两副牌8底牌)的斗地主游戏。

- 多人进入同一房间即可开始对战，后续进入玩家可观战。
- 出牌无时间限制，中途关闭网页后可以随时再回来继续对战（很适合多人线下排队无聊时玩）。

前后端通信基于websocket，前端基于React，后端基于Daphne。无数据库。

这是后端仓库，前端仓库位于 https://github.com/HullQin/poker_fe

## 部署方法

### 前提
- 安装node。js，拥有npm.(use official ways in official website)
- 安装yarn。`npm install -g yarn`. 
- npm换源
```
    // 查询源
    yarn config get registry
    
    // 更换国内源
    yarn config set registry https://registry.npmmirror.com
    
    // 恢复官方源
    yarn config set registry https://registry.yarnpkg.com
    
    // 删除注册表
    yarn config delete registry
```
- yarn 换源
>注意 npm 更换国内镜像源之后，将无法再使用 npm search
命令，需要恢复为官方源才可以使用，如果恢复官方源后还不可使用，运行删除注册表命令后重试即可。
```
// 查询源
    npm config get registry
   
    // 更换国内源
    npm config set registry https://registry.npmmirror.com
   
    // 恢复官方源
    npm config set registry https://registry.npmjs.org
   
    // 删除注册表
    npm config delete registry
```

### 步骤

1. 在前端代码仓库执行`yarn`和`yarn build`，得到产物`build/*`。
2. 前端产物`build/*`放在后端代码仓库的`static/*`下(后端仓库没创建这个文件夹，需要手动新建文件夹static，再把内容复制过来，例如static/index.html)。
3. 参考Dockerfile启动后端服务后，浏览器访问后端的端口即可。如果不懂Docker也没关系，安装好python依赖后，启动服务的命令是`daphne -b 0.0.0.0 -p 8000 server:application`，需要在项目根目录执行，其中8000就是运行的端口，你可以修改。

## 体验地址

https://game.hullqin.cn/ddz

(注: 本仓库只是早期版本，与线上最新版本有些差异)

## 公众号

欢迎关注"线下聚会游戏"公众号，我会做更多**没广告的纯粹的**小游戏。

之后也会分享其中的技术，以及分享如何做个联机对战小游戏。欢迎关注我的掘金账号: [HullQin - 掘金](https://juejin.cn/user/615367094054285/posts)

![公众号"线下聚会游戏"](qrcode.jpg)
