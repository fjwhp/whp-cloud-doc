# Jetbrains离线破解教程

本教程中的资源由知名JetBrains全家桶破解大神Rover12421制作，搬运自Telegrams```Jetbrains Channel```。


## jar包破解的好处

离线破解，无需联网
支持破解信息自定义，满足自己的个(zhuang)性(bi)需求。


## 破解教程

下载群文件里的jar包，版本不是越高越好，新版当然不能用老版破解，但是老版也没法使用新版破解的，因此注意版本对应。

## 安装JetBrains软件

这个不提了。

## 修改idea.exe.vmoptions文件

找到软件安装目录下bin目录下的
idea.exe.vmoptions（对应32位启动程序idea.exe，一般不推荐使用）和idea64.exe.vmoptions（对应32位启动程序idea64.exe，一般64位机器安装的就是这个）这两个文件，如果是32位机器只需要修改idea.exe.vmoptions，64位的配置文件是无效的，不是32位机器的话修改idea64.exe.vmoptions就行，因为默认不会安装32位的JRE，所以如果系统没有自带32位的jdk或者jre的话甚至idea.exe都无法启动。一句话：**32位机器修改idea.exe.vmoptions，64位机器修改idea64.exe.vmoptions。**

它的默认参数如下：
```
-Xms128m
-Xmx750m
-XX:ReservedCodeCacheSize=240m
-XX:+UseConcMarkSweepGC
-XX:SoftRefLRUPolicyMSPerMB=50
-ea
-Dsun.io.useCanonCaches=false
-Djava.net.preferIPv4Stack=true
-Djdk.http.auth.tunneling.disabledSchemes=""
-XX:+HeapDumpOnOutOfMemoryError
-XX:-OmitStackTraceInFastThrow
-javaagent:D:/jar-crack/JetbrainsIdesCrack-3.4-release-enc.jar
```
如果机器ok的话其实调整这个文件的Xms和Xmx可以带来显著的性能提升，并且注意**这里的配置影响的是全局的，如果要修改个人用户的VM配置，可以进入idea在Help->Edit Custom VM Options在里面进行编辑**。

其实更为推荐的是修改个人级的配置，可以避免因为官方升级的影响，如果电脑多用户操作的话也不会影响别的用户。

修改方法很简单，就是在文件后面加一句话

```
-javaagent:你的破解jar包路径，支持绝对和相对路径
```

如果是windows系统，jar包的位置也不需要必须和安装路径一致，甚至在不同的盘符也可以，通过绝对路径进行定位即可。以我的为例，改造后的整个文件如下：
```
-Xms128m
-Xmx750m
-XX:ReservedCodeCacheSize=240m
-XX:+UseConcMarkSweepGC
-XX:SoftRefLRUPolicyMSPerMB=50
-ea
-Dsun.io.useCanonCaches=false
-Djava.net.preferIPv4Stack=true
-Djdk.http.auth.tunneling.disabledSchemes=""
-XX:+HeapDumpOnOutOfMemoryError
-XX:-OmitStackTraceInFastThrow
-javaagent:D:/jar-crack/JetbrainsIdesCrack-3.4-release-enc.jar
```
建议不管是windows还是linux都是用/作为文件分割符，windows下如果使用\作为分割符要写成\\\\。并且这个文件位置不建议带有空格，带空格的话整个文件路径要用引号引起来，wondows下著名的一个会有空格的目录就是**Program Files**

**注意:**
一般情况下覆盖升级IDEA时会覆盖检测这两个文件，可以提前备份或者重新修改。



## 个性教程

R大的包支持自定义认证信息，只需要传入特定格式的json格式即可，3.x的版本的格式如下:

```json
Code:{"licenseId":"1337", 
"licenseeName":"lishangbu",
"assigneeName":"",
"assigneeEmail":"shangshili@hotmail.com",
"licenseRestriction":"Unlimited license till end of the century.",
checkConcurrentUse":false,
"products":[
{"code":"II","paidUpTo":"9999-12-31"},
{"code":"DM","paidUpTo":"9999-12-31"},
{"code":"AC","paidUpTo":"9999-12-31"},
{"code":"RS0","paidUpTo":"9999-12-31"},
{"code":"WS","paidUpTo":"9999-12-31"},
{"code":"DPN","paidUpTo":"9999-12-31"},
{"code":"RC","paidUpTo":"9999-12-31"},
{"code":"PS","paidUpTo":"9999-12-31"},
{"code":"DC","paidUpTo":"9999-12-31"},
{"code":"RM","paidUpTo":"9999-12-31"},
{"code":"CL","paidUpTo":"9999-12-31"},
{"code":"PC","paidUpTo":"9999-12-31"},
{"code":"DB","paidUpTo":"9999-12-31"},
{"code":"GO","paidUpTo":"9999-12-31"},
{"code":"RD","paidUpTo":"9999-12-31"}
],
"hash":"2911276/0",
"gracePeriodDays": 7,
"autoProlongated": false}
```

2.x的版本的格式对应关系如下:

```json

ThisCrackLicenseId-{

"licenseId":"ThisCrackLicenseId",

"licenseeName":"lishangbu",

"assigneeName":"",

"assigneeEmail":"shangshili@hotmail.com",

"licenseRestriction":"It’s OK!",

"checkConcurrentUse":false,

"products":[

{"code":"II","paidUpTo":"2099-12-31"},

{"code":"DM","paidUpTo":"2099-12-31"},

{"code":"AC","paidUpTo":"2099-12-31"},

{"code":"RS0","paidUpTo":"2099-12-31"},

{"code":"WS","paidUpTo":"2099-12-31"},

{"code":"DPN","paidUpTo":"2099-12-31"},

{"code":"RC","paidUpTo":"2099-12-31"},

{"code":"PS","paidUpTo":"2099-12-31"},

{"code":"DC","paidUpTo":"2099-12-31"},

{"code":"RM","paidUpTo":"2099-12-31"},

{"code":"CL","paidUpTo":"2099-12-31"},

{"code":"PC","paidUpTo":"2099-12-31"}

],

"hash":"2911276/0",

"gracePeriodDays":7,

"autoProlongated":false}
```

之后就可以在**Help**->**About**菜单中看到定制的结果了。


## 版本对应关系

都是自己试的，以下亲测可用。
| 破解jar包版本 | 对应IDEA版本 | 
| :----: | :----: | 
| 3.4 | 2018.3 |
| 3.1 | 2018.2 |
| 2.9 | 2018.1.5|

## 更新日志,搬运至R大的google+

**V3.4**

-   Support JDK 9/11

**V3.1**
-   fix key no save.


**V2.9**
-   fix custom Date and PhpStorm 2018.1.5 custom username

