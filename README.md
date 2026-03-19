### 🚀[am-cf-tunnel](https://github.com/amclubs/am-cf-tunnel)
This is a script based on the Cloudflare Workers and Pages platforms. It is a modified version of the original, specifically enhanced to display and convert VLESS and Trojan configuration information into subscription content.

With this script, you can easily use online configuration converters to subscribe to VLESS and Trojan nodes within tools like Clash, Sing-box, and Quantumult X. By leveraging Cloudflare Workers and Pages, this script enables one-click node subscriptions via a built-in sub-converter.[最新视频教程](https://youtu.be/e1Lvo5F37vk)、[🎬 YouTube](https://youtube.com/@am_clubs?sub_confirmation=1)、 [💬 Telegram](https://t.me/am_clubs)、[📂 GitHub](https://github.com/amclubs)、[🌐 Blog](https://amclubss.com)

### Recommended Video Tutorials
- [Fixing Error 1101 and 522: Troubleshooting Guide](https://youtu.be/4fcyJjstFdg) | [Cloudflare Preferred IP & Reverse Proxy IP Tutorial](https://youtu.be/pKrlfRRB0gU) | [Common -1 Error: Troubleshooting Guide](https://youtu.be/kYQxV1G-ePw) | [Free Domain Tutorial](https://www.youtube.com/playlist?list=PLGVQi7TjHKXZGODTvB8DEervrmHANQ1AR) | [NAT64 Version Tutorial](https://youtu.be/nx80sGpVoBM)
- [VLESS Free Node Deployment Tutorial](https://youtu.be/dPH63nITA0M) | [Trojan Free Node Deployment Tutorial](https://youtu.be/uh27CVVi6HA) | [Free Deployment: From Beginner to Pro](https://youtu.be/ag12Rpc9KP4)| [Advanced Guide: Pinning Nodes to Specific Regions](https://youtu.be/wgeM9XvZ5RA)
- [Tutorial: Using Preferred IP Lists from Private GitHub Repos](https://youtu.be/vX3U3FuuTT8) | [Cloudflare KV: Storing Preferred IP Lists (Free Guide)](https://youtu.be/dzxezRV1v-o)  | [Tutorial: Generating Unlimited Nodes via Cloudflare Domains](https://youtu.be/novrPiMsK70) | [Tutorial: Aggregating Node Subscriptions](https://youtu.be/YBO2hf96150)
- [🔥Cloudflare NAT (amclubs-cfnat): Auto-Preferred IP (Windows Desktop)](https://youtu.be/-a6NJ6vPSu4) | [Linux & OpenWrt (Router Version)](https://youtu.be/ZC6fxZwPaiM) | [Mac Version](https://youtu.be/gf6gncc2yEE) | [Android Version](https://youtu.be/7yamDM38MFw) | [Docker Version](https://youtu.be/gRnNwoeUQKU)
- 🔥 Official Subscription Converter: https://sub.amclubss.com

## 📝一、Prerequisites
<details>
<summary>Click to Expand / Collapse</summary>

### 1、Sign up for a free Cloudflare account (Only an email address is required)
- Registration Link：https://cloudflare.com <a href="https://youtu.be/ITeuSbHVQ2E">[Click to Watch Video Tutorial]</a>

### 2、Registration**Free Domain** [Click to Watch All Free Domain Video Tutorials](https://www.youtube.com/playlist?list=PLGVQi7TjHKXZGODTvB8DEervrmHANQ1AR)

### 3、**Subscription Clients** [Click to Watch Usage Video Tutorial](https://youtu.be/xGOL57cmvaw)
👉 [Click to Join our Telegram Group | Discussion"](https://t.me/AM_CLUBS)Send Keyword **Tools** Get Download

### 4、Cloudflare Standard **Ports** Essentials  [Click to Watch Preferred IP Video Tutorial](https://youtu.be/pKrlfRRB0gU)
- 80 Ports (HTTP)：80，8080，8880，2052，2082，2086，2095
- 443 Ports (HTTPS)：443，2053，2083，2087，2096，8443
- [IP Exit Node Testing Tools" or "Outbound IP Checker Links](https://ip.sb/) 

</details>

## 
## ⚙️ II. Workers Deployment Method [Video Tutorial](https://www.youtube.com/watch?v=i-XnnP-MptY&t=165s)
<details>
<summary>Click to Expand/Collapse</summary>

1. Deploy Cloudflare Worker：
   - In the left-hand menu of the Cloudflare Dashboard `计算(Workers)` 选项卡 -> 点击 `Workers 和 Pages` -> 右上方点击 -> `创建应用程序` -> 选择 `Workers`里的 `从 Hello World! 开始` 点击 `开始使用` -> 填入 `Worker 名称`(此名称自己命名) 后 -> 右下方点击 `部署` 后-> 右上方点击 `断续处理项目`。(此步已有可忽略)。
2. 给UUID设置KV存储桶(推荐设置)： 
   - 在 CloudFlare主页的左边菜单的 `存储和数据库` 选项卡 -> 展开选择点击 `Workers KV` -> 右方点击 -> `创建实例(Create Instance)` -> 填入 `命名空间名称`(此名称自己命名) 后 -> 点击 `创建`。(此步已有可忽略)
   - 在 workers控制台的 `绑定` 选项卡 -> 右方点击 -> `添加绑定` -> 选择 `KV 命名空间` 右下方点击 -> `添加绑定` -> 变量名称 填入 `amclubs`(此名称固定不能变) -> KV 命名空间 选择 在上面创建的 `命名空间名称`后 -> 右下方点击 `添加绑定`。
3. 部署 Cloudflare Worker代码：
   - 在 workers控制台的 右上角方点击 `编辑代码(</>)` 图标进入代码编辑页面。
   - 将 [_worker.js](https://github.com/amclubs/am-cf-tunnel/blob/main/_worker.js) 的内容粘贴到 Worker 编辑器中 右上方点击 -> `部署` 完成部署。
4. 给 workers绑定 自定义域： [免费域名申请教程](https://www.youtube.com/playlist?list=PLGVQi7TjHKXZGODTvB8DEervrmHANQ1AR)
   - 在 workers控制台的 `设置` 选项卡 -> 点击 `域和路由` -> 右方点击 -> `添加` -> 选择 `自定义域`。
   - 填入你已转入 CloudFlare 域名 (amclubss.com) 解析服务的次级域名，例如:`vless.amclubss.com`后 点击 `添加域`，等待证书生效即可。
5. 验证部署是否成功：
   - 访问 `https://[YOUR-WORKERS-URL]` 即可进入登录页面,登录成功就是完成部署(默认登录密码(UUID)是：ec872d8f-72b0-4a04-b612-0327d85e18ed)。
   - 例如 `https://vless.amclubss.com` 然后进入登录页面 -> 输入密码 `ec872d8f-72b0-4a04-b612-0327d85e18ed` -> 点击登录 -> 成功登录。 
6. 修改默认登录密码(UUID)变量，使用KV存储桶(推荐修改，防止别人用你节点)： 
   - `https://vless.amclubss.com` 然后进入登录页面 -> 输入密码 `ec872d8f-72b0-4a04-b612-0327d85e18ed` -> 点击登录 -> 成功登录。 
   - 在登录成功页面 ID选项 -> 填入 `新的UUID` 后,[在线获取UUID](https://1024tools.com/uuid) -> 点击 `保存`。
   - 保存成功后，原登录密码(UUID)已作废不能访问，用新登录密码(UUID)登录访问即可。
7. 订阅连接和节点生成使用方法：  [视频教程](https://www.youtube.com/watch?v=i-XnnP-MptY&t=596s)
   - 进入 [am-cf-tunnel-sub](https://github.com/amclubs/am-cf-tunnel-sub) 项目 -> 根据项目教程部署和使用。(此步已有可忽略)
   - 本频道订阅器转换地址：https://sub.amclubss.com
   
</details>

## 
## 📦三、Pages 上传 部署方法 **(最佳推荐!!!)** [视频教程](https://www.youtube.com/watch?v=i-XnnP-MptY&t=1100s)
 <details>
<summary>点击展开/收起</summary>

1. 部署 Cloudflare Pages：
   - 下载 [_worker.js.zip](https://raw.githubusercontent.com/amclubs/am-cf-tunnel/main/_worker.js.zip) 文件，并点上 Star !!!
   - 在 CloudFlare主页的左边菜单的 `计算(Workers)` 选项卡 -> 点击 `Workers 和 Pages` -> 右上方点击 -> `创建应用程序` -> 选择 `Pages`里的 `拖放文件` 点击 `开始使用` -> 填入 `项目名称`(此名称自己命名)后 -> 右边点击 `创建项目` 后 -> 下方 `上传您的项目资产` 点击 `拖放或从计算机中选择` 后  -> 点击 `上传压缩文件` 然后上传你下载好的 [_worker.js.zip](https://raw.githubusercontent.com/amclubs/am-cf-tunnel/main/_worker.js.zip) 文件后点击 `部署站点`。
2. 给UUID设置KV存储桶(推荐设置)： 
   - 在 CloudFlare主页的左边菜单的 `存储和数据库` 选项卡 -> 展开选择点击 `Workers KV` -> 右方点击 -> `创建实例(Create Instance)` -> 填入 `命名空间名称`(此名称自己命名) 后 -> 点击 `创建`。(此步已有可忽略)
   - 在 Pages控制台的 `设置` 选项卡 -> 点击 `绑定` -> 右方点击 -> `添加` -> 选择 `KV 命名空间` -> 变量名称 填入 `amclubs`(此名称固定不能变) -> KV 命名空间 选择 在上面创建的 `命名空间名称`后 -> 右下方点击 `保存`。
   - 在 `设置` 选项卡，在右上角点击 `创建部署` 后，重新上传 [_worker.js.zip](https://raw.githubusercontent.com/amclubs/am-cf-tunnel/main/_worker.js.zip) 文件后点击 `保存并部署` 即可。
3. 给 Pages绑定 CNAME自定义域：[无域名绑定Cloudflare部署视频教程]->[免费域名教程1](https://youtu.be/wHJ6TJiCF0s) [免费域名教程2](https://youtu.be/yEF1YoLVmig)  [免费域名教程3](https://www.youtube.com/watch?v=XS0EgqckUKo&t=320s)
   - 在 Pages控制台的 `自定义域`选项卡，下方点击 `设置自定义域`。
   - 填入你的自定义次级域名，注意不要使用你的根域名，例如：
     您分配到的域名是 `amclubss.com`，则添加自定义域填入 `vless.amclubss.com`即可，点击 `激活域`即可。    
4. 验证部署是否成功：
   - 访问 `https://[YOUR-WORKERS-URL]` 即可进入登录页面,登录成功就是完成部署(默认登录密码(UUID)是：ec872d8f-72b0-4a04-b612-0327d85e18ed)。
   - 例如 `https://vless.amclubss.com` 然后进入登录页面 -> 输入密码 `ec872d8f-72b0-4a04-b612-0327d85e18ed` -> 点击登录 -> 成功登录。 
5. 修改默认登录密码(UUID)变量，使用KV存储桶(推荐修改，防止别人用你节点)： 
   - `https://vless.amclubss.com` 然后进入登录页面 -> 输入密码 `ec872d8f-72b0-4a04-b612-0327d85e18ed` -> 点击登录 -> 成功登录。 
   - 在登录成功页面 ID选项 -> 填入 `新的UUID` 后,[在线获取UUID](https://1024tools.com/uuid) -> 点击 `保存`。
   - 保存成功后，原登录密码(UUID)已作废不能访问，用新登录密码(UUID)登录访问即可。
6. 订阅连接和节点生成使用方法：  [视频教程](https://www.youtube.com/watch?v=i-XnnP-MptY&t=596s)
   - 进入 [am-cf-tunnel-sub](https://github.com/amclubs/am-cf-tunnel-sub) 项目 -> 根据项目教程部署和使用。(此步已有可忽略)
   - 本频道订阅器转换地址：https://sub.amclubss.com

</details>

## 
## 🧰四、Pages GitHub 部署方法 **(不推荐)** [视频教程](https://www.youtube.com/watch?v=dPH63nITA0M&t=654s)
<details>
<summary>点击展开/收起</summary>
   
1. 部署 Cloudflare Pages：
   - 在 Github 上先 Fork 本项目[am-cf-tunnel](https://github.com/amclubs/am-cf-tunnel)，并点上 Star !!!
   - 在 CloudFlare主页的左边菜单的 `计算(Workers)` 选项卡 -> 点击 `Workers 和 Pages` -> 右上方点击 -> `创建应用程序` -> 选择 `Pages`里的 `导入现有 Git 存储库` 点击 `开始使用` -> 选择GitHub 点击`连接GitHub`根据提示授权GitHub和项目(此步已有可忽略)后 -> 选中 `am-cf-tunnel`项目后 -> 点击 `开始设置` -> 可修改`项目名称`(此名称自己命名) 后 -> 右下方点击 `保存并部署`即可。
2. 给UUID设置KV存储桶(推荐设置)： 
   - 在 CloudFlare主页的左边菜单的 `存储和数据库` 选项卡 -> 展开选择点击 `Workers KV` -> 右方点击 -> `创建实例(Create Instance)` -> 填入 `命名空间名称`(此名称自己命名) 后 -> 点击 `创建`。(此步已有可忽略)
   - 在 Pages控制台的 `设置` 选项卡 -> 点击 `绑定` -> 右方点击 -> `添加` -> 选择 `KV 命名空间` -> 变量名称 填入 `amclubs`(此名称固定不能变) -> KV 命名空间 选择 在上面创建的 `命名空间名称`后 -> 右下方点击 `保存`。
   - 在 `设置` 选项卡，点击 `部署` -> 在所有部署 找到最新一条部署记录 ，在右边点击 3个点 `...` 选择 `重试部署` 即可。
3. 给 Pages绑定 CNAME自定义域：[无域名绑定Cloudflare部署视频教程]->[免费域名教程1](https://youtu.be/wHJ6TJiCF0s) [免费域名教程2](https://youtu.be/yEF1YoLVmig)  [免费域名教程3](https://www.youtube.com/watch?v=XS0EgqckUKo&t=320s)
   - 在 Pages控制台的 `自定义域`选项卡，下方点击 `设置自定义域`。
   - 填入你的自定义次级域名，注意不要使用你的根域名，例如：
     您分配到的域名是 `amclubss.com`，则添加自定义域填入 `vless.amclubss.com`即可，点击 `激活域`即可。    
4. 验证部署是否成功：
   - 访问 `https://[YOUR-WORKERS-URL]` 即可进入登录页面,登录成功就是完成部署(默认登录密码(UUID)是：ec872d8f-72b0-4a04-b612-0327d85e18ed)。
   - 例如 `https://vless.amclubss.com` 然后进入登录页面 -> 输入密码 `ec872d8f-72b0-4a04-b612-0327d85e18ed` -> 点击登录 -> 成功登录。 
5. 修改默认登录密码(UUID)变量，使用KV存储桶(推荐修改，防止别人用你节点)： 
   - `https://vless.amclubss.com` 然后进入登录页面 -> 输入密码 `ec872d8f-72b0-4a04-b612-0327d85e18ed` -> 点击登录 -> 成功登录。 
   - 在登录成功页面 ID选项 -> 填入 `新的UUID` 后,[在线获取UUID](https://1024tools.com/uuid) -> 点击 `保存`。
   - 保存成功后，原登录密码(UUID)已作废不能访问，用新登录密码(UUID)登录访问即可。
6. 订阅连接和节点生成使用方法：  [视频教程](https://www.youtube.com/watch?v=i-XnnP-MptY&t=596s)
   - 进入 [am-cf-tunnel-sub](https://github.com/amclubs/am-cf-tunnel-sub) 项目 -> 根据项目教程部署和使用。(此步已有可忽略)
   - 本频道订阅器转换地址：https://sub.amclubss.com

</details>

## 
## 🔧五、变量说明 [视频教程](https://www.youtube.com/watch?v=i-XnnP-MptY&t=468s)
| 变量名 | 示例 | 必填 | 备注 | YT |
|-----|-----|-----|-----|-----|
| ID   | ec872d8f-72b0-4a04-b612-0327d85e18ed（默认）|✅| 支持Cloudflare的KV存储桶设置 [在线获取UUID](https://1024tools.com/uuid) VLESS、Trojan节点共用 | |
| D_URL | https://cloudflare-dns.com/dns-query |❌| DNS解析获取作用，小白勿用                                                           |  |

## 
## ⚙️ Snippets Deployment Guide [Video Tutorial](https://www.youtube.com/watch?v=i-XnnP-MptY&t=165s)
<details>
<summary>Click to Expand / Collapse</summary>

1. 进入 Cloudflare Snippets：
   - 在 CloudFlare主页的左边菜单的 `域` 选项卡 -> 点击 `域` 菜单 -> 进入到 `域管理` -> 找到已开通**Snippets**的域名点击进入 -> 进入后在左边菜单的 `规则` 选项卡 点击展开 -> 点击 `Snippets` 菜单 -> 进入 `Snippets`片段代码主页面。
2. 部署 Cloudflare Snippets代码：
   - 在 `Snippets`片段代码主页面的 右下角方点击 `+创建片段` 图标进入代码编辑页面 -> 在右上方创建片段 -> 填入 `片段名称`(此名称自己命名)。
   - 将 [_worker.js](https://github.com/amclubs/am-cf-tunnel/blob/main/snippets.js) 的内容粘贴到 `Snippets` 编辑器中 -> 修改第一行代码`id`变量值(默认登录密码(UUID)是：ec872d8f-72b0-4a04-b612-0327d85e18ed) 建议自己要修改 [在线获取UUID](https://1024tools.com/uuid)。
   - 点击右上方 `片段规则` 图标 -> 选择 `自定义筛选表达式` -> 字段 选择 `主机名` -> 运算符 选择 `运算符` -> 值 填入 `Snippets进入的域名名称，再前面加多一节子域名名称`(子域名名称自己命名) 后 -> 点击 `完成`。(此步已有可忽略)
   - 在 码编辑页面 右上角方点击 `部署` -> 选择 `创建新代理 DNS 记录` -> 字段 `IPv4 地址（必填）` -> 查看下面显示 `使用 192.0.2.1 放弃请求` -> 显示IP值 填入后 -> 点击 `创建记录和部署规则`。
3. 验证部署是否成功：
   - 访问 `https://[YOUR-Snippets-URL]` 即可进入登录页面,登录成功就是完成部署(默认登录密码(UUID)是：ec872d8f-72b0-4a04-b612-0327d85e18ed)。
   - 例如 `https://vless.amclubss.com` 然后进入登录页面 -> 输入密码 `ec872d8f-72b0-4a04-b612-0327d85e18ed` -> 点击登录 -> 成功登录。 
4. 订阅连接和节点生成使用方法：  [视频教程](https://www.youtube.com/watch?v=i-XnnP-MptY&t=596s)
   - 进入 [am-cf-tunnel-sub](https://github.com/amclubs/am-cf-tunnel-sub) 项目 -> 根据项目教程部署和使用。(此步已有可忽略)
   - 本频道订阅器转换地址：https://sub.amclubss.com
   
</details>

## 
## 🧩六、节点订阅器部署  [Vercel部署视频教程](https://www.youtube.com/playlist?list=PLGVQi7TjHKXZGODTvB8DEervrmHANQ1AR) [Cloudfare部署视频教程](https://youtu.be/f8ZTvv4u3Pw)

#### `①` Vercel方式部署 [视频教程](https://www.youtube.com/watch?v=i-XnnP-MptY&t=596s)
<details>
<summary>点击展开/收起</summary>

1. Fork或克隆本仓库[am-cf-tunnel-sub](https://github.com/amclubs/am-cf-tunnel-sub)到您的 GitHub/GitLab 账户
2. 登录 [Vercel](https://vercel.com)，点击"New Project" <a href="https://www.youtube.com/watch?v=ZxHLLlxuJyI&t=28s">[点击观看注册视频教程]</a>
3. 导入您的仓库，使用默认设置
4. **⚠️ 重要：在"Settings" > "Environment Variables"中添加 `UUID` 和 `HOST` 变量（必须设置）**
5. 点击"Deploy"

访问 `http://部署域名` 即可。
</details>

#### `②` Cloudfare Workers 部署方法 [视频教程](https://www.youtube.com/watch?v=D4XqeRNm2JI&t=501s)
<details>
<summary>点击展开/收起</summary>

1. 部署 Cloudflare Worker：
   - 在 CloudFlare主页的左边菜单的 `计算和AI` 选项卡 -> 点击 `Workers 和 Pages` -> 右上方点击 -> `创建应用程序` -> 选择 `Workers`里的 `从 Hello World! 开始` 点击 `开始使用` -> 填入 `Worker 名称`(此名称自己命名) 后 -> 右下方点击 `部署` 后-> 右上方点击 `断续处理项目`。(此步已有可忽略)。
2. 设置节点UUID和HOST变量： 
   - 在 Workers控制台的 `设置` 选项卡 -> 点击 `设置` -> 左方点击 `变量和机密` -> 右方点击  `添加` -> 变量名称 填入 `UUID`(此名称固定不能变) ，值填入CF部署节点ID -> 再点击添加变量 填入 `HOST`(此名称固定不能变)，值填入CF部署的自定义域名 后 -> 右下方点击 `保存` 即可。
3. 部署 Cloudflare Worker代码：
   - 在 workers控制台的 右上角方点击 `编辑代码(</>)` 图标进入代码编辑页面。
   - 将 [_worker.src.js](https://github.com/amclubs/am-cf-tunnel-sub/blob/main/_worker.src.js) 的内容粘贴到 Worker 编辑器中 右上方点击 -> `部署` 完成部署。
4. 给 workers绑定 自定义域： [免费域名申请教程](https://www.youtube.com/playlist?list=PLGVQi7TjHKXZGODTvB8DEervrmHANQ1AR)
   - 在 workers控制台的 `设置` 选项卡 -> 点击 `域和路由` -> 右方点击 -> `添加` -> 选择 `自定义域`。
   - 填入你已转入 CloudFlare 域名 (amclubss.com) 解析服务的次级域名，例如:`sub.amclubss.com`后 点击 `添加域`，等待证书生效即可。
5. 验证部署是否成功：
   - 访问 `https://[YOUR-WORKERS-URL]` 即可进入登录页面,登录成功就是完成部署(默认登录密码(UUID)是：ec872d8f-72b0-4a04-b612-0327d85e18ed)。
   - 例如 `https://sub.amclubss.com` 然后进入登录页面 -> 输入密码 `ec872d8f-72b0-4a04-b612-0327d85e18ed` -> 点击登录 -> 成功登录。 
6. 修改默认登录密码(ID)变量，(强烈要求修改，防止别人用你节点)： 
   - 在 Worker代码控制台的 `设置` 选项卡 -> 点击 `设置` -> 左方点击 `变量和机密` -> 右方点击  `添加` -> 变量名称 填入 `ID`(此名称固定不能变) ，自己设置复杂的密码 -> 右下方点击 `保存` 即可。
   - 保存成功后，原登录密码(ID)已作废不能访问，用新登录密码(ID)登录访问即可。
7. 增加优选IP(ips)变量，**(要在线优选功能必须配置)**： 
   - 在 CloudFlare主页的左边菜单的 `存储和数据库` 选项卡 -> 展开选择点击 `Workers KV` -> 右方点击 -> `创建实例(Create Instance)` -> 填入 `命名空间名称`(此名称自己命名) 后 -> 点击 `创建`。(此步已有可忽略)
   - 在 Pages控制台的 `设置` 选项卡 -> 点击 `绑定` -> 右方点击 -> `添加` -> 选择 `KV 命名空间` -> 变量名称 填入 `ips`(此名称固定不能变) -> KV 命名空间 选择 在上面创建的 `命名空间名称`后 -> 右下方点击 `保存` 即可。
8. 本频道订阅器转换地址：https://sub.amclubss.com

</details>

#### III. Cloudflare Pages Upload Deployment **(Highly Recommended!!!)** [Video Tutorial](https://www.youtube.com/watch?v=D4XqeRNm2JI&t=982s)
<details>
<summary>Click to Expand / Collapse</summary>

1. Deploy Cloudflare Pages：
   - Download [_worker.src.js.zip](https://raw.githubusercontent.com/amclubs/am-cf-tunnel-sub/main/_worker.src.js.zip) file, and give it a Star !!!
   - On CloudFlare主页的左边菜单的 `计算(Workers)` 选项卡 -> 点击 `Workers 和 Pages` -> 右上方点击 -> `创建应用程序` -> 选择 `Pages`里的 `拖放文件` 点击 `开始使用` -> 填入 `项目名称`(此名称自己命名)后 -> 右边点击 `创建项目` 后 -> 下方 `上传您的项目资产` 点击 `拖放或从计算机中选择` 后  -> 点击 `上传压缩文件` 然后上传你下载好的 [_worker.src.js.zip](https://raw.githubusercontent.com/amclubs/am-cf-tunnel-sub/main/_worker.src.js.zip) 文件后点击 `部署站点`。
2. Configure Node UUID and HOST Variables： 
   - 在 Pages控制台的 `设置` 选项卡 -> 点击 `设置` -> 左方点击 `变量和机密` -> 右方点击  `添加` -> 变量名称 填入 `UUID`(此名称固定不能变) ，值填入CF部署节点ID -> 再点击添加变量 填入 `HOST`(此名称固定不能变)，值填入CF部署的自定义域名 后 -> 右下方点击 `保存`。
   - 在 `设置` 选项卡，点击 `部署` -> 在所有部署 找到最新一条部署记录 ，在右边点击 3个点 `...` 选择 `重试部署` 即可。
3. Bind a CNAME Custom Domain to Pages：[无域名绑定Cloudflare部署视频教程]->[免费域名教程1](https://youtu.be/wHJ6TJiCF0s) [免费域名教程2](https://youtu.be/yEF1YoLVmig)  [免费域名教程3](https://www.youtube.com/watch?v=XS0EgqckUKo&t=320s)
   - 在 Pages控制台的 `自定义域`选项卡，下方点击 `设置自定义域`。
   - 填入你的自定义次级域名，注意不要使用你的根域名，例如：
     您分配到的域名是 `amclubss.com`，则添加自定义域填入 `sub.amclubss.com`即可，点击 `激活域`即可。    
4. Verify Deployment：
   - 访问 `https://[YOUR-WORKERS-URL]` 即可进入登录页面,登录成功就是完成部署(默认登录密码(UUID)是：ec872d8f-72b0-4a04-b612-0327d85e18ed)。
   - 例如 `https://sub.amclubss.com` 然后进入登录页面 -> 输入密码 `ec872d8f-72b0-4a04-b612-0327d85e18ed` -> 点击登录 -> 成功登录。 
5. Change Default Password (ID)变量，(强烈要求修改，防止别人用你节点)： 
   - 在 Pages控制台的 `设置` 选项卡 -> 点击 `设置` -> 左方点击 `变量和机密` -> 右方点击  `添加` -> 变量名称 填入 `ID`(此名称固定不能变) ，自己设置复杂的密码 -> 右下方点击 `保存`。
   - 在 `设置` 选项卡，点击 `部署` -> 在所有部署 找到最新一条部署记录 ，在右边点击 3个点 `...` 选择 `重试部署` 即可。
   - 保存成功后，原登录密码(ID)已作废不能访问，用新登录密码(ID)登录访问即可。
6. Add Preferred IP(ips)Variable，**(Required for the online IP optimization feature.)**： 
   - 在 CloudFlare主页的左边菜单的 `存储和数据库` 选项卡 -> 展开选择点击 `Workers KV` -> 右方点击 -> `创建实例(Create Instance)` -> 填入 `命名空间名称`(此名称自己命名) 后 -> 点击 `创建`。(此步已有可忽略)
   - 在 Pages控制台的 `设置` 选项卡 -> 点击 `绑定` -> 右方点击 -> `添加` -> 选择 `KV 命名空间` -> 变量名称 填入 `ips`(此名称固定不能变) -> KV 命名空间 选择 在上面创建的 `命名空间名称`后 -> 右下方点击 `保存`。
   - Click `Save` 选项卡，点击 `部署` -> 在所有部署 找到最新一条部署记录 ，在右边点击 3个点 `...` 选择 `重试部署` 即可。
7. Subscription Converter：https://sub.amclubss.com

</details>

#### `④` Cloudfare Pages GitHub 部署方法 **(不推荐)** [视频教程](https://www.youtube.com/watch?v=f8ZTvv4u3Pw&t=137s)
<details>
<summary>点击展开/收起</summary>
   
1. 部署 Cloudflare Pages：
   - 在 Github 上先 Fork 本项目[am-cf-tunnel-sub](https://github.com/amclubs/am-cf-tunnel-sub)，并点上 Star !!!
   - 在 CloudFlare主页的左边菜单的 `计算(Workers)` 选项卡 -> 点击 `Workers 和 Pages` -> 右上方点击 -> `创建应用程序` -> 选择 `Pages`里的 `导入现有 Git 存储库` 点击 `开始使用` -> 选择GitHub 点击`连接GitHub`根据提示授权GitHub和项目(此步已有可忽略)后 -> 选中 `am-cf-tunnel-sub`项目后 -> 点击 `开始设置` -> 可修改`项目名称`(此名称自己命名) 后 -> 右下方点击 `保存并部署`即可。
2. 设置节点UUID和HOST变量： 
   - 在 Pages控制台的 `设置` 选项卡 -> 点击 `设置` -> 左方点击 `变量和机密` -> 右方点击  `添加` -> 变量名称 填入 `UUID`(此名称固定不能变) ，值填入CF部署节点ID -> 再点击添加变量 填入 `HOST`(此名称固定不能变)，值填入CF部署的自定义域名 后 -> 右下方点击 `保存`。
   - 在 `设置` 选项卡，点击 `部署` -> 在所有部署 找到最新一条部署记录 ，在右边点击 3个点 `...` 选择 `重试部署` 即可。
3. 给 Pages绑定 CNAME自定义域：[无域名绑定Cloudflare部署视频教程]->[免费域名教程1](https://youtu.be/wHJ6TJiCF0s) [免费域名教程2](https://youtu.be/yEF1YoLVmig)  [免费域名教程3](https://www.youtube.com/watch?v=XS0EgqckUKo&t=320s)
   - 在 Pages控制台的 `自定义域`选项卡，下方点击 `设置自定义域`。
   - 填入你的自定义次级域名，注意不要使用你的根域名，例如：
     您分配到的域名是 `amclubss.com`，则添加自定义域填入 `sub.amclubss.com`即可，点击 `激活域`即可。    
4. 验证部署是否成功：
   - 访问 `https://[YOUR-WORKERS-URL]` 即可进入登录页面,登录成功就是完成部署(默认登录密码(UUID)是：ec872d8f-72b0-4a04-b612-0327d85e18ed)。
   - 例如 `https://sub.amclubss.com` 然后进入登录页面 -> 输入密码 `ec872d8f-72b0-4a04-b612-0327d85e18ed` -> 点击登录 -> 成功登录。 
5. 修改默认登录密码(ID)变量，(强烈要求修改，防止别人用你节点)： 
   - 在 Pages控制台的 `设置` 选项卡 -> 点击 `设置` -> 左方点击 `变量和机密` -> 右方点击  `添加` -> 变量名称 填入 `ID`(此名称固定不能变) ，自己设置复杂的密码 -> 右下方点击 `保存`。
   - 在 `设置` 选项卡，点击 `部署` -> 在所有部署 找到最新一条部署记录 ，在右边点击 3个点 `...` 选择 `重试部署` 即可。
   - 保存成功后，原登录密码(ID)已作废不能访问，用新登录密码(ID)登录访问即可。
6. 增加优选IP(ips)变量，**(要在线优选功能必须配置)**： 
   - 在 CloudFlare主页的左边菜单的 `存储和数据库` 选项卡 -> 展开选择点击 `Workers KV` -> 右方点击 -> `创建实例(Create Instance)` -> 填入 `命名空间名称`(此名称自己命名) 后 -> 点击 `创建`。(此步已有可忽略)
   - 在 Pages控制台的 `设置` 选项卡 -> 点击 `绑定` -> 右方点击 -> `添加` -> 选择 `KV 命名空间` -> 变量名称 填入 `ips`(此名称固定不能变) -> KV 命名空间 选择 在上面创建的 `命名空间名称`后 -> 右下方点击 `保存`。
   - 在 `设置` 选项卡，点击 `部署` -> 在所有部署 找到最新一条部署记录 ，在右边点击 3个点 `...` 选择 `重试部署` 即可。
7. 本频道订阅器转换地址：https://sub.amclubss.com

</details>

🔧Environment Variables [Video Guide](https://www.youtube.com/watch?v=i-XnnP-MptY&t=808s)
<details>
<summary>Click to Expand / Collapse</summary>

| Variable Name | Example | Required | Remarks | YT |
|-----|-----|-----|-----|-----|
| ID   | ec872d8f-72b0-4a04-b612-0327d85e18ed（Default）|✅| Subscription Converter Login Password | |
| UUID | ec872d8f-72b0-4a04-b612-0327d85e18ed |✅| Cloudflare Deployment Node ID Variable Value[Generate UUID Online](https://1024tools.com/uuid)   |  |
| HOST | vless.amclubss.com |✅| Cloudflare Deployment Domain or Custom Domain | |
| IP_URL           | [https://raw.github.../ipUrl.txt](https://raw.githubusercontent.com/amclubs/am-cf-tunnel/main/example/ipUrl.txt) </br>或</br> [https://raw.github.../ipv4.txt](https://raw.githubusercontent.com/amclubs/am-cf-tunnel/main/example/ipv4.txt) |❌| （推荐）优选(ipv4、ipv6、域名、API)地址(支持多个之间`,`或 换行 作间隔)，支持文件连接后里带PROXYIP参数，可以实现不同区域优先IP使用不同的PROXYIP固定区域，解决IP乱跳问题  | [视频教程](https://www.youtube.com/watch?v=4fcyJjstFdg&t=349s)|
| PROXYIP          | proxyip.amclubs.kozow.com </br>或</br> [https://raw.github.../proxyip.txt](https://raw.githubusercontent.com/amclubs/am-cf-tunnel/main/example/proxyip.txt)  |❌| 访问CloudFlare的CDN代理节点(支持多PROXYIP, PROXYIP之间使用`,`或 换行 作间隔),支持端口设置默认443 如: proxyip.amclubs.kozow.com:2053 ，支持远程txt或csv文件| [视频教程](https://youtu.be/pKrlfRRB0gU) |
| SOCKS5           | user:password@127.0.0.1:1080         |❌| 优先作为访问CFCDN站点的SOCKS5代理                                                   | [视频教程](https://youtu.be/Bw82BH_ecC4) |
| NAT64           | true/false                           |❌| 默认false,是否开启nat做PROXYIP(反代IP)，开启后优选使用NAT64再用PROXYIP       | [视频教程](https://www.youtube.com/watch?v=nx80sGpVoBM&t=533s) |
| NAT64_PREFIX  | 2602:fc59:b0:64::  </br>或</br> [https://raw.github.../nat64Prefix.txt](https://raw.githubusercontent.com/amclubs/am-cf-tunnel/main/example/nat64Prefix.txt)    |❌| 指定自定NAT64前缀,不填走CF默认的 (https://amclubss.com/public/)     | [视频教程](https://www.youtube.com/watch?v=nx80sGpVoBM&t=533s)|
| SUB_CONFIG       | [https://raw.github.../ACL4SSR_Online_Mini.ini](https://raw.githubusercontent.com/amclubs/ACL4SSR/main/Clash/config/ACL4SSR_Online_Full_MultiMode.ini) |❌| clash、singbox等 订阅转换配置文件  ||
| SUB_CONVERTER    | url.v1.mk                    |❌| clash、singbox等 订阅转换后端的api地址                               ||
| PROT_TYPE        | 默认空          |❌|      默认空,就是生成vless和trojan节点，vless(只生成vless节点)，trojan(只生成trojan节点)           | [视频教程](https://www.youtube.com/watch?v=emEBm8Gw2wI&t=922s) |
| NIP_HOST | 553558.xyz(默认) |❌| 优先IP时需要的nip服务 | |
| EXTRA_IP | [https://raw.github.../ipv4.txt](https://raw.githubusercontent.com/amclubs/am-cf-tunnel/main/example/ipv4.txt) |❌| 优先IP时需要的nip服务 | |
| EXTRA_IP_PROXY | [https://raw.github.../proxyip_am.txt](https://raw.githubusercontent.com/amclubs/am-cf-tunnel/main/example/proxyip_am.txt) |❌| 优先IP时需要的nip服务 | |
| CF_NAMESPACE_ID  | 37cf3x8xxx(Vercel方式部署才需求)     |❌ | 优先IP时需要CF的KV存桶ID（存储和数据库->Workers KV->创建的命名空间ID）        ||
| CF_ACCOUNT_ID    | 0b0e49ba2xxxx(Vercel方式部署才需求)  |❌ | 优先IP时需要CF的帐号ID（计算和AI->Account Details->Account ID）         ||
| CF_EMAIL         | xxx@gmail.com(Vercel方式部署才需求)  |❌ | 优先IP时需要CF的帐号邮箱        ||
| CF_API_KEY       | 49ba2xxxx(Vercel方式部署才需求)      |❌ | 优先IP时需要CF的API令牌（管理帐户->帐户API令牌->创建的令牌D）          ||

- Channel Subscription Converter URL：https://sub.amclubss.com
  
</details>

## 
## 🛠Compatible Subscription Tools [Click for Video Tutorial](https://youtu.be/xGOL57cmvaw) [Click for Karing Video Tutorial](https://youtu.be/M3vLLBWfuFg)
<details>
<summary>Click to Expand / Collapse</summary>

- Mac
   - [v2rayU](https://github.com/yanue/V2rayU/releases) | [clash-verge-rev](https://github.com/clash-verge-rev/clash-verge-rev/releases) | [Quantumult X](https://apps.apple.com/us/app/quantumult-x/id1443988620) |  [小火箭](https://apps.apple.com/us/app/shadowrocket/id932747118) | [surge](https://apps.apple.com/us/app/surge-5/id1442620678) | [karing](https://karing.app/download) | [sing-box](https://github.com/SagerNet/sing-box/releases)  | [Clash Nyanpasu](https://github.com/keiko233/clash-nyanpasu/releases) | [openclash](https://github.com/vernesong/OpenClash/releases) | [Hiddify](https://github.com/hiddify/hiddify-next/releases)

- Win
   - [v2rayN](https://github.com/2dust/v2rayN/releases) |  [clash-verge-rev](https://github.com/clash-verge-rev/clash-verge-rev/releases) | [sing-box](https://github.com/SagerNet/sing-box/releases) |  [Clash Nyanpasu](https://github.com/keiko233/clash-nyanpasu/releases) | [openclash](https://github.com/vernesong/OpenClash/releases)  | [karing](https://karing.app/download) |  [Hiddify](https://github.com/hiddify/hiddify-next/releases)
     
- IOS
   - [clash-verge-rev](https://github.com/clash-verge-rev/clash-verge-rev/releases) |  [Quantumult X](https://apps.apple.com/us/app/quantumult-x/id1443988620)  |  [小火箭](https://apps.apple.com/us/app/shadowrocket/id932747118)  |  [surge](https://apps.apple.com/us/app/surge-5/id1442620678) |  [sing-box](https://github.com/SagerNet/sing-box/releases) | [Clash Nyanpasu](https://github.com/keiko233/clash-nyanpasu/releases) | [karing](https://karing.app/download) | [Hiddify](https://github.com/hiddify/hiddify-next/releases)
     
- Android
   - [v2rayNG](https://github.com/2dust/v2rayNG/releases) |  [clash-verge-rev](https://github.com/clash-verge-rev/clash-verge-rev/releases) | [sing-box](https://github.com/SagerNet/sing-box/releases) |  [Clash Nyanpasu](https://github.com/keiko233/clash-nyanpasu/releases) |  [karing](https://karing.app/download) | [Hiddify](https://github.com/hiddify/hiddify-next/releases)

- Software Router
   - [openclash(clash.meta)](https://github.com/vernesong/OpenClash/releases) 
  
</details>

##
### 🙏Thank you
[3Kmfi6HP](https://github.com/3Kmfi6HP/EDtunnel)、[ACL4SSR](https://github.com/ACL4SSR/ACL4SSR/tree/master/Clash/config)

# 
<center>
<details><summary><strong> ☕ [Click to Expand] Support & Donations ~🧧🧧</strong></summary>
*I truly appreciate your appreciation and support; it greatly inspires me to keep innovating and consistently producing valuable work.*

- **USDT-TRC20:** `TWTxUyay6QJN3K4fs4kvJTT8Zfa2mWTwDD`
- **TRX-TRC20:** `TWTxUyay6QJN3K4fs4kvJTT8Zfa2mWTwDD`

<div align="center"> 
  <img src="https://github.com/user-attachments/assets/e6cdc42a-6374-4722-b833-601738f72196" width="200"></br> 
  Scan to Pay via TRC10 / TRC20 
</div> 
</details>
</center>

#
⚠️Disclaimer:
 - 1、Purpose & Copyright: This project is designed and developed solely for learning, research, and security testing purposes. Please delete all files within 24 hours of downloading. It may not be used for any commercial purposes. All text, data, and images are copyrighted; any reproduction must clearly credit the original source.
 - 2、Legal Compliance: Users of this program must strictly comply with the laws and regulations of the region where the server is deployed, as well as the laws of the hosting country and the user's own country. Any consequences resulting from the use of this project by any individual or group shall be borne entirely by the user.
 - 3、Limitation of Liability: The author shall not be held responsible for any direct or indirect damages arising from the use of this project. The author reserves the right to update this disclaimer at any time without prior notice.


## ⭐ Don't forget to Star!
[![Stargazers over time](https://starchart.cc/amclubs/am-cf-tunnel.svg?variant=adaptive)](https://starchart.cc/amclubs/am-cf-tunnel)

