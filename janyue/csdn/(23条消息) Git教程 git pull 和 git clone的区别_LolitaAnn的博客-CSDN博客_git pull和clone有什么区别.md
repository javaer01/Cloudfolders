> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [blog.csdn.net](https://blog.csdn.net/qq_36667170/article/details/121264178)

网上看好多人解释pull和clone的区别，说什么pull是更新本地代码，clone是本地从无到有的过程，但有一点没提到，恰好我今天又犯了这个问题，因为我原来都是直接从远程仓库pull，今天突然发现发现pull不能用，clone才生效，我才意识到这个问题。决定记录一下。

* * *

使用方法
====

*   有权限的仓库 本地无代码
    *   `git pull`
    *   `git clone`
*   有权限的仓库 本地有代码
    *   `git pull`
*   无权限的仓库 本地无代码
    *   `git clone`
*   无权限的仓库 本地有代码
    *   删了重新下

换个说法

*   `git pull`：必须连接远程仓库才能用。可以用于下载完整代码更新本地代码。
*   `git clone`：只要你想往本地下远程仓库完整的代码就可以用，不用连接远程仓库（连接了也可以）。 不适用于更新本地代码。

如果只想知道怎么用就不用往下看了，如果想知道原因继续看。

* * *

---------------------------分割线---------------------------
=========================================================

* * *

1 git pull
==========

`git pull`适用于**从用户有权限的仓库下拉代码**，**不管本地有没有代码**。

因为我平时下拉代码都是直接`git pull`。

1.1 我有权限的仓库
-----------

**我有权限的仓库指的是我自己的，或者团队中我可以使用的仓库。**

要使用`git pull`首先你要确定已经连接远程仓库。要不然你直接`git pull orgin master`那[Github](https://so.csdn.net/so/search?q=Github&spm=1001.2101.3001.7020)会问你：“😧？什么master？哪个master？你就是老子的master吗？”

所以首先要连接远程仓库。

![在这里插入图片描述](https://img-blog.csdnimg.cn/f4d4df8f911d45078b341208d28a4a21.png)

1.  init初始化空白的本地仓库，里边除了`.git`啥也没有
2.  连接远程仓库

### 1.1.1 本地没代码

![在这里插入图片描述](https://img-blog.csdnimg.cn/2825f007a72a4c398d326b43c7353aad.png)  
`git remote -v`用于显示当前本地仓库连接的远程仓库，你可以连接好几个。然后一个仓库是成对存在的，一个上传一个下拉。前边origin我一般称为远程仓库代称，后边的是你的连接方式。

现在显示我连接了一个github的远程仓库取名叫origin。

![](https://img-blog.csdnimg.cn/4c652e03f514462a85ffb1ac94ca0391.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBATG9saXRhQW5u,size_20,color_FFFFFF,t_70,g_se,x_16)

空白仓库直接使用`git pull`就可以下拉代码了。

### 1.1.2 本地有代码

本地有代码是什么情况。

*   团队合作，一个仓库多人使用
*   你自己的仓库，你在多台电脑上使用（比如宿舍一个，实验室一个）

为什么要`git pull`呢？不同电脑上代码版本不一样。所以为了减少工作并且保证代码版本一致，要在每次写代码的时候下拉代码。在写完之后push到远程仓库。画个图解释一下。  
![在这里插入图片描述](https://img-blog.csdnimg.cn/3b0525e100854fc5a27bc1286b3e56bf.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBATG9saXRhQW5u,size_20,color_FFFFFF,t_70,g_se,x_16)  
![在这里插入图片描述](https://img-blog.csdnimg.cn/b692febb72f24c06b1085546a9a01d2d.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBATG9saXRhQW5u,size_20,color_FFFFFF,t_70,g_se,x_16)

1.2 我没权限的仓库
-----------

**没权限的仓库指的是别人的仓库。别人不给权限，你当然不能随意修改人家的代码了。**

**没权限的仓库不能使用`git pull`**。比如：

今天我像往常一样去下载代码。但是这是我第一次下载别人的代码。  
![在这里插入图片描述](https://img-blog.csdnimg.cn/425a4a92d6bc4bba822a52a9fbd75d2a.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBATG9saXRhQW5u,size_20,color_FFFFFF,t_70,g_se,x_16)  
我像往常一样添加仓库链接，git pull下拉。但是他提示我：

> Permission denied (publickey).  
> fatal: Could not read from remote repository.
> 
> Please make sure you have the correct access rightsand the repository exists.

Permission denied是说SSH密钥无法使用，让我确认我是否有权限访问或者这个仓库是不是存在。  
仓库确实是存在的。所以肯定是我没有权限。  
![在这里插入图片描述](https://img-blog.csdnimg.cn/a48ede7f906c40d8b4aebf9c0239cff4.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBATG9saXRhQW5u,size_20,color_FFFFFF,t_70,g_se,x_16)  
解释一下三步操作：

1.  添加远程仓库，用SSH连接
2.  从仓库master分支下拉代码
3.  删除我添加的远程仓库（既然不能用我当然删掉了）

这时候我想起来：SSH只有仓库所有者能用。因为你电脑上配置的SSH和你github上的SSH是一对的，只有你在你电脑上使用你的github仓库才能用SSH。

既然仓库所有者才能用SSH，那我换HTTP不就行了。（此时我还没意识到问题的严重性😓）  
![在这里插入图片描述](https://img-blog.csdnimg.cn/2c007efb966d42928437ebc8625f159e.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBATG9saXRhQW5u,size_20,color_FFFFFF,t_70,g_se,x_16)

1.  我又添加了https的连接
2.  第二步我又下拉的仓库

然后他又提示我：

> fatal: unable to access ‘https://github.com/hitvoice/DrQA.git/’: OpenSSL SSL_read: Connection was reset, errno 10054

意思还是我无法连接。  
这时候我突然意识到了问题😐。这好像是人家的仓库哎，我不能使用remote连接远程仓库之后下拉啊。因为如果我能连上的话就意味着我能随意修改人家的代码。所以我肯定不能使用这样的方式pull代码啊！！！

所以得用`git clone`

2 git clone
===========

**`git clone`适用于本地没有代码**，你要下载。

**你连不连接远程仓库都可以，有无仓库权限皆可**。

接上边的说，意识到使用`git clone`之后，我删除了刚才的HTTPS连接远程仓库，然后直接`git clone`，代码成功下载下来了😎😎😎。  
![在这里插入图片描述](https://img-blog.csdnimg.cn/a48792e763134b2886f85f38b66377aa.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBATG9saXRhQW5u,size_20,color_FFFFFF,t_70,g_se,x_16)

1.  我删除了上边的https连接远程仓库的方法
2.  `git remote -v`用于查看你本地仓库都连接了哪些远程仓库，如果连接了会显示仓库代号和连接方式，我这里输出空白，就是没连接任何远程仓库的状态
3.  `git clone`下载代码成功了。

**上边说的是别人的仓库，那如果是我有权限的仓库呢？**

新建一个空白的本地仓库。直接用SSH clone能成功，那HTTPS必定成功。不用remote能成功，那用了remote也必定成功。（觉得这些稍微会用github的一般不用解释了，如果实在不明白评论区问我。）  
![在这里插入图片描述](https://img-blog.csdnimg.cn/1c07dcbc41ef4470bed2caae6f55f657.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBATG9saXRhQW5u,size_20,color_FFFFFF,t_70,g_se,x_16)

* * *

我是萝莉安。今天又拿出勤时间写博客了。离谱。