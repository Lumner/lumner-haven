---
share: true
category: mkdocs网站搭建教程
---
# 配置 MkDocs 以兼容 Obsidian 语法  
### 安装插件  
1. 打开Obsidian设置，点击第三方插件（Community plugins）,关闭安全模式  
2. 点击浏览（Browse）,搜索`Enveloppe`  
3. 点击后安装（install）并启用（enable）  
### 获取Github Token  
1. 登录Github  
2. 点击右上角头像 -> Settings -> Developer settings (最下面) -> Personal access tokens-> Tokens (classic)  
3. 点击Generate new tokens(classic)  
4. 登录  
5. Note随意填一个就好了  
6. Expiration (过期时间) 选 `No expiration` ，或者视你个人情况  
7. Scopes(权限)勾选：  
`repo` (全选，包含 repo:status, repo_deployment 等)  
`workflow` (如果要触发自动构建)  
8. 划到最下方，点击生成，复制`ghp_`开头的字符串，保存好，只会出现一次  
### 配置插件  
回到Obsidian，打开`Enveloppe`的设置页  
#### GitHub config  
1. 依次输入GitHub username，Repository name，GitHub token（你刚复制的那串字符）  
2. Main branch选择main  
3. 点击下方test connection检查，右上角报绿就连接成功了  
4. 关掉Automatically merge pull requests（gemini一开始没告诉我，我一直是错的，可以ctrl shift i调出来把console的报错扔给AI让它解释怎么改）  
#### File paths  
1. File tree in repository选择property key，这样以后方便设计索引  
2. 在docs下新建文件夹posts用于存放文章  
3. Root&Default folder都输入docs/posts  
#### Content  
1. 打开`[[Wikilinks]] to [MDlinks](links)`,选择strict  
2. 打开Markdown hard line break  
#### Attachment & embeds  
- Default attachment folder写docs/assets(如果没有就建一个assets文件夹)  
### 发布文章  
#### 正常步骤  
1. 在文章开头输入以下代码  
```  
---  
share: true  
---  
```  
2. 停留在笔记页面，按Ctrl P(mac:Cmd P)打开命令面板  
3. 输入关键词Enveloppe，选择`Upload single current active note` (发布当前文件)  
然后等待即Github Actions变绿即可  
#### 设置快捷键  
1. 打开Obsidian设置  
2. 在左侧找到快捷键（Hotkeys）  
3. 在搜索框中输入Enveloppe  
4. 选择`Upload single current active note`  
5. 输入喜欢的快捷键就好，我的是`Alt S`  
#### 索引设置  
![p1.jpg](assetsp1.jpg)![p2.jpg](assetsp2.jpg)![p3.jpg](assetsp3.jpg)  
- 上面的插件需要你再终端运行  
```  
pip install -r requirements.txt  
```  
