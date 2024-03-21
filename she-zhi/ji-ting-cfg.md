# 急停CFG

**制作者**: 藤原染色体/鸽子梨

**相关视频**：[BV1SG411y7HT](https://www.bilibili.com/video/BV1SG411y7HT)

**安装方法：**

下载 **QuickStop Latest.zip** , [解压](https://answer.baidu.com/answer/land?params=9%2BIX4C88WSGy3lAHzCyTt96MU5ocEzurGlIK68n2FmnZjiLV4EBtxg7ZKZIWW8npEy6WUF5Z1rv7pMdtnAKQWsgCDU%2FCcjntADkIdVJTHWw2SbYWKM9wFN9l2ygaBvhyark7qiC958YlqyX927UZUeTySJCwYrUVBbLbEZFILtw7mFoekTxUWXDbBYvfxjXFVh2cwbt77WBTqUkCmT87dw%3D%3D&from=dqa&lid=94f6b53c001c888f&word=%E5%A6%82%E4%BD%95%E8%A7%A3%E5%8E%8B%E6%96%87%E4%BB%B6)此压缩包。

0. 打开解压后的文件，里面有个名为 **jiting** 的文件，或者是名为 **jiting.cfg** 的文件，复制它。
1. 在 Steam 中点开您的库，在库中选择 **Counter-Strike 2**。
2. 点击右边的齿轮，点击 **属性...**，选择 **已安装文件**，点击 **浏览...**。
3. 打开 **game** 文件夹，再点开 **csgo** 文件夹，再点开 **cfg** 文件夹。
4. 将刚刚复制的文件放在这个文件夹里。

之后回到第1步，点击右边的齿轮，点击 **属性...** 之后，选择 **通用**，在 **启动选项**（高级用户可以选择对启动选项的修改。）处，加入以下内容：
`+exec jiting`

既可使用急停辅助。其他问题解决方法请加入Q群：*327978675*

*急停CFG代码展示*
```
//瓦式急停
alias "+_forward" "+forward; forwardback 0.0001 0 0;clear";
alias "-_forward" "-forward; forwardback -0.0001 0 0;rightleft 0 0 0";
alias "+_back" "+back; forwardback -0.0001 0 0";
alias "-_back" "-back; forwardback 0.0001 0 0;rightleft 0 0 0";
alias "+_left" "+left; rightleft -0.0001 0 0";
alias "-_left" "-left; rightleft 0.0001 0 0;forwardback 0 0 0";
alias "+_right" "+right; rightleft 0.0001 0 0";
alias "-_right" "-right; rightleft -0.0001 0 0;forwardback 0 0 0";

//双键急停
alias "+_forward1" "+forward; forwardback 0.0001 0 0;clear";
alias "-_forward1" "-forward; forwardback 0 0 0";
alias "+_back1" "+back; forwardback -0.0001 0 0";
alias "-_back1" "-back; forwardback 0 0 0";
alias "+_left1" "+left; rightleft -0.0001 0 0";
alias "-_left1" "-left; rightleft 0 0 0";
alias "+_right1" "+right; rightleft 0.0001 0 0";
alias "-_right1" "-right; rightleft 0 0 0";

//ws瓦式急停，ad双键急停
alias "+ws_forward" "+forward; forwardback 0.0001 0 0;clear";
alias "-ws_forward" "-forward; forwardback -0.0001 0 0";
alias "+ws_back" "+back; forwardback -0.0001 0 0";
alias "-ws_back" "-back; forwardback 0.0001 0 0";
alias "+ws_left" "+left; rightleft -0.0001 0 0;forwardback 0 0 0";
alias "-ws_left" "-left; rightleft 0 0 0";
alias "+ws_right" "+right; rightleft 0.0001 0 0;forwardback 0 0 0";
alias "-ws_right" "-right; rightleft 0 0 0";

alias "+jt" "+ljt";
alias "-jt" "+xjt";
alias "+jt1" "+xjt";
alias "-jt1" "+ljt";

wsjiting;

alias "huifu" "echo 已经取消辅助急停，恢复默认移动设置。 ; forwardback 0 0 0; rightleft 0 0 0; cl_hud_color 0; bind w "+forward"; bind s "+back"; bind a "+left"; bind d "+right";";

alias "xinjiting" "echo 已经开启瓦罗兰特式急停，松开方向键即可急停，该急停包含双键急停。;cl_hud_color 6; bind capslock wsjiting; bind "w" "+_forward";bind "s" "+_back";bind "a" "+_left";bind "d" "+_right"";
alias "wsjiting" "echo 已经开启ws瓦罗兰特式急停、ad双键急停。;cl_hud_color 1; bind capslock "laojiting"; bind "w" "+ws_forward";bind "s" "+ws_back";bind "a" "+ws_left";bind "d" "+ws_right";";
alias "laojiting" "echo 已经开启双键劲舞团急停，同时按住ad或者ws即可急停。; cl_hud_color 9; bind capslock "xinjiting"; bind "w" "+_forward1";bind "s" "+_back1";bind "a" "+_left1";bind "d" "+_right1";";
alias "buqiehuan" "echo 已经关闭CAPSLOCK大小写键和ALT键切换功能。; unbind CAPSLOCK; unbind alt;"; 

//使用方法：

//瓦式急停：ui颜色为红色，瓦罗兰特式急停，松开对应方向键即可急停，包含常规急停、双键急停。		缺陷：失去了惯性，且因为代码局限，上楼梯和飞行模式会无法控制地//往一边走。
//双键急停：ui颜色为绿色，劲舞团急停，见视频：BV12841167nH，按住a时同时按d即可急停，包含常规急停。	补充：负责用在新一键急停中无法上楼梯的情况。
//ws瓦式急停，ad双键急停：ui颜色为白色。

//按键说明：
//	CAPSLOCK（切换大小写）	：切换双键急停（见视频：BV12841167nH）
//如果想更改按键设置，可以使用文本文档搜索功能（Ctrl + F），搜索并更改。
//
//游戏中默认使用瓦罗兰特式松开急停，瓦式急停包含双键急停，属于全自动急停，如果想关闭或者只使用双键急停，控制台可以直接输入：
//	xinjiting	：点击CAPSLOCK切换为双键急停，直接松开对应方向键即可急停
//	laojiting	：点击CAPSLOCK切换为瓦式急停，如视频BV12841167nH一样，原汁原味的劲舞团双键急停。
//	huifu	：关闭一键急停，将按键设置恢复为默认。
```
