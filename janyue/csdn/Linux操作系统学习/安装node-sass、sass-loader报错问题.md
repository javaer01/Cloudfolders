### 可行版本（针对 node 16+ 版本）

不想浪费时间看的，可直接去尝试

```bash
npm install node-sass@6.0.1 -D
npm install sass-loader@10.2.0 -D
```



### 问题描述

问题描述：在进行一个vue项目练习时需要导入node-sass、sass-loader这两个依赖，书本提供代码是`npm install sass-loader@7.2.x node-sass@4.12.x -` 尝试n次也无法成功执行。

报错：

![image-20221029072713129](https://raw.githubusercontent.com/javaer01/cloudimage/main/TyporaImg/co_img/202210290727290.png)

于是上网查找问题解决得方法，经过数小时得尝试最终解决，以下是总结出的经验教训。



### 解决方法

1、首先执行以下代码，卸载老版node-sass、sass-loader（因为你有可能安装上了其中一个，但另一个安装不了）

```bash
npm uninstall sass-loader node-sass
```

2、查找与自己node版本对应得node-sass版本，并且要==先安装node-sass，再去找匹配的sass-loader==，这一点非常重要，我就是被这个坑住了

如何查看自己的node版本号呢？进入终端输入指令

```bash
node -v
```



版本对照表：

![image-20221029073637836](https://raw.githubusercontent.com/javaer01/cloudimage/main/TyporaImg/co_img/202210290736920.png)

你也可以进入github自行查看[Releases · sass/node-sass (github.com)](https://github.com/sass/node-sass/releases)

比如我的node版本号是 v16.17.0，我就成功安装了`"node-sass": "^6.0.1"`版本，执行以下代码安装node-sass

```bash
npm install node-sass@6.0.1 -D
```





3、安装sass-loader

最后安装sass-loader，适合的版本可以直接到网上去搜索，比如我一开始找到的版本是 10.0.1 然后还是安装失败，最后换成 10.2.0 安装成功

```bash
npm install sass-loader@10.2.0 -D
```

最后希望我的尝试能帮助你解决问题！！！