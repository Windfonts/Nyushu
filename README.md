﻿# 𛆁𛈬𛇋𛋒｜女书柳叶｜Nüshu Serif
<p align="center">
<a href="https://afdian.net/@FairyFloss" target="_blank">
<img src="https://user-images.githubusercontent.com/58043328/223596267-22fef57b-83c9-4075-b97e-fa4585129180.png">
</a><br/>𛆤𛅽𛊓𛆁 𛈖𛋉𛅰𛉊
</p>

这是一套女书「柳叶体(衬线体)」书法字体，旨在通过[OpenType特性](#特性)支持女书各种已知变体 (异体)，允许同一女字变换各种写法。

<h3 align="center"><a href="https://github.com/nushu-script/Nyushu/releases"><strong>»»» 这边下载 «««</strong></a></h3>

### 改善
如有更多变体依据欢迎提供，即便[日文报纸](http://www.thurcacca.org/upload/image/201710/23/0310263926.jpg "出处：www.thurcacca.org/bookpage/45/")上的也行。发 [议题（issues）](../../issues)、[讨论（discussions）][Disc]或在别的地方私信我都可以。别的地方若未回复那是没收到，请看看我是否在线，再发一次。\
当然如果能编辑字体的话，可以直接打开源文件修改并发布，也开源并通知我的话那就更好了，只要字形符合[设计规范][Disc3]还会合并到本字体，并添加到字体内信息以[致谢](#致谢)。\
关于字形的文件格式，可以给我未合并曲线的.otf或.svg。可以用开源的Inkscape来制作编辑.svg矢量图，我正是用Inkscape绘制本字体的。

但需注意 女书提案09-03-18[^3598]53页起认为收录了3400女“字”的《女漢字典[^NHZD]》有伪作问题：
> …all the characters in Nuhan Dictionary is written by the author himself, some of which is faked and created by him. They have never photocopied one character from the original works. …\
As a kind of script system which is used by rural women, it is impossible for them to have a huge and complicated script system such as three or four thousand characters included. …

甚至封面｢漢｣｢典｣二字查无出处（上述提案57页起，应作｢𛊧｣｢𛉸[^HYX]｣），因此虽《女漢》有一定参考价值，但其所列变体如无其它出处概**不采纳**。

据[相关研究成果](http://www.thurcacca.org/bookpage/37/)，可参考 赵丽明《中国女书合集[^NSHJ]》、《女书读本[^NSDB]》（但我手上没有，参考的是《女书用字比较[^NSDB]》）

手头还有 周硕沂《女书字典[^NSZD]》，发觉这本不仅有《女漢》的问题，还更多：将女书和甲骨文等楷书之前的文字比对、文字释义无关女书而大抄《现汉》……因此其所列变体亦**不采纳**。

有一介绍网站 [传奇女书 - 清华大学中国古文字艺术研究中心](http://www.thurcacca.org/indexbook.html)，看上去未完成就停更了，尚有大量错误没改，其中[女书赏析](http://www.thurcacca.org/bookpage/3/)页或可作美术字设计参考。

### 特性
GSUB features: calt, salt, ss01, ss02, ss03, ss04, ss09, ss10

`calt` **上下文替换**，根据上下文，在不改变字义的前提下调整字形。该特性一般浏览器无需设置默认开启。

> 以下特性需要软件支持和开启设置。目前各大浏览器应该都支持，[在网页CSS里添加相应代码即可](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Fonts/OpenType_fonts_guide "OpenType字体特性指南 - CSS | MDN")。

`ss**` **样式集<sub>第几</sub>**，替换默认字形为<sub>第几个</sub>变体，最多20个。本字体暂只用到几个，其中有3个指定了特定用途：
- `ss01` **原始书法**：将默认字形还原为胡欣(?)[^NSZT]书体，即便它与统一码所示不同。
- `ss10` **异体书法**：作为`ss01`子集，只含与统一码所示不同的部分。
- `ss04` **错字修正**：本字体有意保留此前存在的错误字形方便学术研究，开启这个会将错的字形替换为我修正的——不一定是默认，而是形最接近的。
> 错字需手动输入，为避免出错，故意不设替换为错字的样式集。
- `ss02` 笔画一致，只调整了书法、间架之类的。
- `ss03` 目前是放笔画有差别的变体。
- `ss05~08` 预留，毕竟不止3个变体。
- `ss09` 目前是放完全不一致的变体，例如阳焕宜写的｢𛈵｣（《比较[^NSDB]》p14）
- `ss11~20` 或预留给帮忙改善字形的人。

`salt` **样式替换**，和其它字体不同，本字体指定了特定用途“负负得正”：将任意非默认字形（比如被**样式集**替换的）退回本字体默认的统一码规定字形。如果和**样式集**同时开启……那得看谁优先级更高，或执行更靠后了。\
自不必说`ss**` `calt`由于性质上都是换字形，互相之间都会干扰的。

为免误会顺带一提：字体特性只会改变字形，字码当然不变。但若所用的软件不支持以上OT特性，那就只能手动改字码，详见[NyushuSrc.csv](#nyushusrccsv)章节。

### 更新
𛅱𛆊𛆥𛆊𛇃𛅴𛇈｜2023年3月8日 **第一版**
- 解决有无问题。现已支持全部396+1女书字符，及其它字符。ASCII数字是对应的小型女书。
- 笔画为“[防爆刺][Disc3]”设计：尝试解决某些大厂软件的字体勾边会意外在笔画的锐角处爆刺的问题。
- 为兼容过时软件，[除了｢𛇢｣](#女书概述)，395个女书及其变体多重映射到1000个较为对应的汉字字码，详见[NyushuSrc.csv]的汉字列。如对应有问题请[发给我](#改善)。
- 统一码截至15.0版未收录的2种女书行尾填空符暂用￬ (位于东亚用符号区段，字形取自｢𛉕｣，因为不用于横排，暂设全角宽度)、㇣(汉字笔画)顶替。预期竖排时居中对齐。
- 如果你也在做字体，本字体为各种变体特性提供了参考范例。例如其中`calt`特性在检测到上下文出现｢天下妇女｣或｢姊妹一家｣时会将相关字形改为太平天囯一枚雕母钱上的式样。\
![刻有女书的雕母钱](https://nushuscript.org/static/coin.jpg "太平天国 (咸丰年间)，仅一枚，未见翻铸的子钱")

𛆊𛇃𛅵𛇈｜2023年3月10日 **第1.001版**
- 改善一些偏旁为`:`字形的美感问题，涉及`斗时柳娘拜气心到派配等别刻鸳清淡`约16个字形。
- 多重映射到更多汉字（本版为1336个），并修正[NyushuSrc.csv]。现在也可以用｢々｣输出｢𖿡｣了。
- 自绘｢𛇶｣变体。补充别的符号。
- 添加特性`ss10`
- 补充浏览器更易加载的.woff2网页字体。

2023年3月12日 **第1.002版**
- 将自撰“偏旁”放到私用区以便调用，列表：[NyushuCompMY.csv](/NyushuCompMY.csv)
- 多重映射到已知汉字完成（共1765个，欠修正），大量替换映射的女书如｢昨做祭｣等，大幅改善[NyushuSrc.csv]，预备[变体来源考据](https://github.com/nushu-script/Nyushu/discussions/6)表格。
- 改善｢𛊥𛋡｣字形，自绘｢𛈻𛊀｣变体并补充相应特性。

### 已知问题
**下一版**预定𛈗或𛈕月发布
- 改善美感问题。继续调整全部默认字形，使字重、字面、中轴视觉统一。替下字形删除或移至`ss01` `ss02`
- 尽量解决约204个字缺少原始书法`ss01`，约14个字缺少统一码所示字形`salt`的问题。

**推敲中**
- 数字`0`是否应从小型｢𛉀｣改为圈？因为｢𛉀｣不仅对应零。
- 需要“女书风格”的ASCII西文吗？
- 观察已有文献，女书排版可以是等宽不等高的，这要求给每个字形单独指定垂直度量，需要擅长这方面的设计师帮忙。

### 未来计划
字重可变、衬线向无衬线可变、美术风格可变……实际上我绘制曲线的同时已经为可变字体[作好准备][Disc3]了。


# [NyushuSrc.csv]
本字体使用说明书，纯文本表格。
- 汉字一般第一个依 赵丽明、徐焰《女书规范字书法字帖[^NSZT]》（或有误），“ss1~ss9”列摆放变体字形映射的汉字，“ss10”的`〃`表示同“ss1”，方括号为一形对多字（即括号`[ ]`内的字与括号前方一个字共用字形。这难免有误，毕竟 宫哲兵、唐功𬀩《女书标准字字典[^NSBZ]》与《字帖[^NSZT]》选择的对应汉字可能完全不同）
- 此表仅为字体制作而制。不考虑OT特性，字体当然只能是输入唯一字码给出唯一字形，不能处理同一汉字对应多个女字的情况。
- 备注中的《女漢》为 陳其光《女漢字典[^NHZD]》的对应，《比较》为 赵丽明<sup>等</sup>《女书用字比较[^NSDB]》的对应。[若有矛盾](#改善)，以《比较》为准。
- `≈`标的汉字是[统一码15.0.0 NamesList.txt](https://www.unicode.org/Public/15.0.0/ucd/NamesList.txt) 备注的，其中｢抆｣有[勘误](http://www.unicode.org/L2/L2022/22138-nushu-font-update.pdf)，应为｢坟｣，经过勘误的备注`up!`。与《字帖[^NSZT]》不同的以`!`号标记。
- 读音（kReading）取自 [统一码15.0.0 NushuSources.txt](https://www.unicode.org/Public/15.0.0/ucd/NushuSources.txt)，但下面我会说明不一定只有一个读音。
- “偏旁”为自撰，方便字体制作，难免有误。其中`。`表示其偏旁即其本身，` \ `是表示此字形多种拆法的分界。偏旁排序未按先中间后两边的笔顺。尚未考虑那些与统一码规定[完全不同](http://www.thurcacca.org/copyinfo/324.html)的变体。


# 女书概述
女书对应的江永土话音节，21个声母、38个韵母、5声调（《比较[^NSDB]》p162，[声调应该说是5度，不止5个](https://github.com/nushu-script/rime-nushu/wiki/关于女书拼音的说明-%7C-Notes-on-the-Romanization-of-Nüshu#声调tones)），因此其数量有上限（《比较》p194：300多个），不可无限加字——但可有异体。
> 城关音系，
> 黄雪贞系统和陈其光系统都可以看，两者有些区别，但都是正确的，一般的女书文字学考察都用的黄雪贞系统

已知有些土话音节底层不是汉语，因此女字不能与汉字一一对应。虽然本字体把女书各个变体与选定汉字多重映射到同一字形上（与我仅用几百字形对应111,4112个码位的字体[｢典迹末境｣](https://github.com/MY1L/Unicode#monu-last)用的同款技术），但这是便于某些过时软件使用（比如只支持[基本平面](https://github.com/MY1L/Unicode/tree/main/Blocks#平面)BMP的那些，输入位于SMP的女书会爆炸），不意味着我选的映射是唯一和准确的，学术研究可不能用这个便宜设计偷懒。

比如我发现的一例｢𛇢｣ (ie²¹，音完全同｢𛅳｣)，《女书读本[^NSDB]》p42对应到｢⼞<sub>个</sub>/派｣，但｢个｣对应｢𛆅｣，｢派｣对应｢𛈜｣，无汉字可用。《比较》p37可见是｢𛆱｣音ie²¹（同时还有ie⁴⁴、ie³⁵、ie³³多个音），｢𛅳｣却是ie⁴²，上一页p36｢𛇢｣对应ie¹³｢引｣，但｢引｣对应｢𛊉 (ie¹³)｣。《比较》p86可见｢𛇢｣还有音tchy²¹对应｢去｣，但｢去｣对应｢𛇂 (tchy²¹)｣，至p201“女书基本字与字源考：6画”给出字源｢依/个｣，音只有ie²¹，｢个｣不用说，｢依｣对应的｢𛆱(ie⁴⁴) 𛊺(i⁴²) 𛋕(i³⁵)｣，仍无汉字可用。至于为何同一本《比较》前后标音不一致我不好说啥。《女书字典[^NSZD]》638页注音iə⁴⁴，译为“因\茵\音\阴\姻”，注“疑为｢阴｣”……🤔\
因此本字体的｢𛇢｣未对应任何汉字，考虑到过时软件或不能渲染她，暂多重映射到私用区uE1E2“”，如有更好的建议请[发给我](#改善)。
> 《比较》所附“女书基本字”为2006年10月二稿。女书提案09-03-18[^3598]含有“女书基本字”新版，p78对照可见对应汉字补充了｢派｣

女书起源不可考，专家们[^UNCO]写推荐书时皆称妇女所创，但这些专家不都是专研女书的，也未考据创制者。大多女书资料也未深入探究，只知必然晚于汉字楷化，唯《女漢[^NHZD]》推理女书最初可能是受汉字教育的男性发明。我想在未新发掘可靠文物验证前，还是不要过多猜想。

目前所见女书皆一笔一画没有连笔草书。顺带一提，统一码按笔画数排序，但其中｢𛉧｣应订正为9笔，没法改了😥

<details><summary>﹎点此展开\折叠 统一码笔数范围 表格﹎</summary>

|笔数|范围|全列|
| -: | :-: | - |
| 1|1B170	|𛅰|
| 2|1B171~1B177|𛅱𛅲𛅳𛅴𛅵𛅶𛅷|
| 3|1B178~1B18A|𛅸𛅹𛅺𛅻𛅼𛅽𛅾𛅿𛆀𛆁𛆂𛆃𛆄𛆅𛆆𛆇𛆈𛆉𛆊|
| 4|1B18B~1B1A7|𛆋𛆌𛆍𛆎𛆏𛆐𛆑𛆒𛆓𛆔𛆕𛆖𛆗𛆘𛆙𛆚𛆛𛆜𛆝𛆞𛆟𛆠𛆡𛆢𛆣𛆤𛆥𛆦𛆧|
| 5|1B1A8~1B1DD|𛆨𛆩𛆪𛆫𛆬𛆭𛆮𛆯𛆰𛆱𛆲𛆳𛆴𛆵𛆶𛆷𛆸𛆹𛆺𛆻𛆼𛆽𛆾𛆿𛇀𛇁𛇂𛇃𛇄𛇅𛇆𛇇𛇈𛇉𛇊𛇋𛇌𛇍𛇎𛇏𛇐𛇑𛇒𛇓𛇔𛇕𛇖𛇗𛇘𛇙𛇚𛇛𛇜𛇝|
| 6|1B1DE~1B215|𛇞𛇟𛇠𛇡𛇢𛇣𛇤𛇥𛇦𛇧𛇨𛇩𛇪𛇫𛇬𛇭𛇮𛇯𛇰𛇱𛇲𛇳𛇴𛇵𛇶𛇷𛇸𛇹𛇺𛇻𛇼𛇽𛇾𛇿𛈀𛈁𛈂𛈃𛈄𛈅𛈆𛈇𛈈𛈉𛈊𛈋𛈌𛈍𛈎𛈏𛈐𛈑𛈒𛈓𛈔𛈕|
| 7|1B216~1B243|𛈖𛈗𛈘𛈙𛈚𛈛𛈜𛈝𛈞𛈟𛈠𛈡𛈢𛈣𛈤𛈥𛈦𛈧𛈨𛈩𛈪𛈫𛈬𛈭𛈮𛈯𛈰𛈱𛈲𛈳𛈴𛈵𛈶𛈷𛈸𛈹𛈺𛈻𛈼𛈽𛈾𛈿𛉀𛉁𛉂𛉃|
| 8|1B244~1B283|𛉄𛉅𛉆𛉇𛉈𛉉𛉊𛉋𛉌𛉍𛉎𛉏𛉐𛉑𛉒𛉓𛉔𛉕𛉖𛉗𛉘𛉙𛉚𛉛𛉜𛉝𛉞𛉟𛉠𛉡𛉢𛉣𛉤𛉥𛉦𛉧𛉨𛉩𛉪𛉫𛉬𛉭𛉮𛉯𛉰𛉱𛉲𛉳𛉴𛉵𛉶𛉷𛉸𛉹𛉺𛉻𛉼𛉽𛉾𛉿𛊀𛊁𛊂𛊃|
| 9|1B284~1B2AF|𛊄𛊅𛊆𛊇𛊈𛊉𛊊𛊋𛊌𛊍𛊎𛊏𛊐𛊑𛊒𛊓𛊔𛊕𛊖𛊗𛊘𛊙𛊚𛊛𛊜𛊝𛊞𛊟𛊠𛊡𛊢𛊣𛊤𛊥𛊦𛊧𛊨𛊩𛊪𛊫𛊬𛊭𛊮𛊯|
|10|1B2B0~1B2CD|𛊰𛊱𛊲𛊳𛊴𛊵𛊶𛊷𛊸𛊹𛊺𛊻𛊼𛊽𛊾𛊿𛋀𛋁𛋂𛋃𛋄𛋅𛋆𛋇𛋈𛋉𛋊𛋋𛋌𛋍|
|11|1B2CE~1B2E0|𛋎𛋏𛋐𛋑𛋒𛋓𛋔𛋕𛋖𛋗𛋘𛋙𛋚𛋛𛋜𛋝𛋞𛋟𛋠|
|12|1B2E1~1B2ED|𛋡𛋢𛋣𛋤𛋥𛋦𛋧𛋨𛋩𛋪𛋫𛋬𛋭|
|13|1B2EE~1B2F3|𛋮𛋯𛋰𛋱𛋲𛋳|
|14|1B2F4~1B2F6|𛋴𛋵𛋶|
|15|1B2F7~1B2F9|𛋷𛋸𛋹|
|16|1B2FA~1B2FB|𛋺𛋻|

</details>


# 女书笔画｜Nüshu Strokes
据称统一码前期论证已否决了女书（或 西夏、契丹）笔画区段，因此下表为我方便字体制作而自撰。
暂依《女漢字典[^NHZD]》p1描述顺序。“撰符”借用汉字笔画和括号。

|#|笔画|缩略|撰符|例字|注释|
| - | - | :-: | :-: | :-: | - |
|1|左斜|P|㇒|𛅰𛅱|U+31D2 CJK Stroke **P**，撇
|2|右斜|N|㇏|𛅳𛅵|U+31CF CJK Stroke **N**，捺
|3|左弧|R|) |𛅶𛆁|**右**括号(**R**ight par.)，开口向左
|4|右弧|L|( |𛅷𛅴|**左**括号(**L**eft parenthesis)
|5|圆点|D|㇔|𛆈𛇺|U+31D4 CJK Stroke **D**，点(dot)
|6|上弧|U|︶|?|开口朝上(**U**pper)，形如闭括号，但《女漢》给的例字未见实例🤔
|7|下弧|A|︵|?|拱形(**A**rch)，形如开括号，但《女漢》给的例字做字体时没遇到过
|8|短竖|S|㇑|𛅺𛆅|U+31D1 CJK Stroke **S**，竖
|9|短横|H|㇐|𛈏|U+31D0 CJK Stroke **H**，横(horz.)

据 《女漢[^NHZD]》、女书提案09-03-18[^3598]p52，女书的“小圈”实由左右弧(LR)合成，不过我实际做字体时图省事缩略为“O”(撰符：㇣)


# 女书偏旁｜Nüshu Components
[知乎有图](https://github.com/MY1L/Nyushu/discussions/2)待查证。

据称统一码前期论证已否决了女书偏旁区段，因此我的 [NyushuSrc.csv] 里为方便字体制作而自撰了一些，列表很长，如下。

<details><summary>﹎点此展开\折叠 女书偏旁 表格﹎</summary>

|撰符|笔数|定位|注释|
| :-: | -: | - | - |
)	|1笔	|𛆟𛊬𛊱𛋂𛋅	左边						|= 小𛅰，派生符之一[^o]
x	|2笔	|𛇉𛇧𛈉𛉉𛉔𛉫	左边						|= 小𛅵
o	|2笔	|𛆪𛆲𛇔𛇜	左边；𛇄	右边；𛇱	左右边				|派生用，女漢[^NHZD]￫对应｢口｣[^o]：𛇄-如 𛆪-吹 𛇱-哭
V	|2笔	|𛆜𛇷𛆷𛊤	上边						|我猜某些对应｢亠｣？𛆜-六 𛆷-之
)V	|3笔	|𛇳𛈤𛉊𛊛	左上；𛉽	半包围					|女漢[^NHZD]￫对应｢宀｣：𛈤-字 𛉊-家 𛉽-定
Λ	|2笔	|𛇶𛉇	下边；𛋄	上边
Δ	|3笔	|𛈏	上边；𛊮	里面
\|	|1笔	|𛈕	中插；𛅹𛆰𛉱	下边					|𛈕减去𛆺之余
Ȝ	|2笔	|𛉜𛋧	右边						|女漢[^NHZD]￫“Ɛ Ȝ”对应｢𢆶｣，但𛉜就不是
Ɛ	|2笔	|𛇮𛊄𛈝𛉢𛋧	左边；𛊾	中间					|女漢[^NHZD]￫对应｢幺｣：𛉢-紅 𛋧-樂 𛊾-紗
Ɛ	|〃	|𛇐𛇙𛉹	左边；𛉘	左下					|女漢[^NHZD]￫也对应｢辶｣：𛇐-还[^simp] 𛇙-边[^simp] 𛉘-过[^simp]
.	|1笔	|𛇁𛈐	左右边；𛈣	左右上下边
:	|2笔	|𛇺𛆸𛇋𛇼𛇣𛈭	左边；𛇘𛇬𛊎	右边					|女漢[^NHZD]￫对应｢刂｣[^2d]：𛇋-刘[^simp] 𛇼-到 𛊎-别
︙	|3笔	|𛋟𛋠𛋳	左边；𛇺𛊧	右边					|女漢[^NHZD]￫对应｢氵｣，但多反例[^2d]
…	|3笔	|𛉢𛉸𛊢𛊑𛊼𛋋	右下						|女漢[^NHZD]￫对应｢灬｣：𛉸-点[^simp] 𛊢-魚 𛊑-焦
⁘	|4笔	|𛈯𛉒	下边；𛊰	上下边
※	|6笔	|𛉓𛉘𛊋	右上						|⿵⿶𛆏..
ㄑ	|2笔	|𛆋𛇑	左边；𛊳	上边					|≈ Ȝ
⺈	|2笔	|𛆩𛇽𛈬𛈑	下边						|形似𠂊，躺平的𛅳？
乚	|3笔	|𛇎𛈋𛈚	右上；𛋢	右下
忄	|3笔	|𛉣𛊲	左下						|形似𛅿，女漢[^NHZD]￫对应｢忄｣：𛉣-怕[^pa] 𛊲-恨
⼢	|3笔	|𛇇𛈼	中间；𛇒𛉿	左边；𛉕	右边				|形似𛆂，但出头，女漢[^NHZD]￫𛇇-虫[^simp]
宀	|4笔	|𛊆𛊦𛋢	上边						|形似但不是｢宀｣
不	|4笔	|𛉗𛊛	下边；𛉯𛊩𛋥	左下					|⿱𛅰𛅿，派生符之一[^o]，女漢[^NHZD]￫对应木字旁
朩	|4笔	|𛇰𛊖𛈰	上边；𛈃	右边					|⿵⿷𛅵..，形似但不是｢木｣
口	|4笔	|𛉞𛉥𛊱	上边						|女漢[^NHZD]￫对应｢口｣之二：𛉞-品 𛉥-号[^simp]
龵	|4笔	|𛇤𛉮𛉒𛋍𛊌	上边						|形似𛆣，疑似春字头｢𡗗｣
㓁	|5笔	|𛈨	右边；𛉲𛊘𛊎	上边					|形似𛇃，但内不交叉
半	|5笔	|𛈺	右边；𛈿	中间					|𛈺-伴
区	|5笔	|𛉧	左下						|统一码误作4笔的𛆢
⻊	|5笔	|𛉕	左下						|形似⿿♂︎，比较[^NSDB]p236￫对应｢足｣：𛉕-跳
亚	|6笔	|𛉏	右上						|女漢[^NHZD]￫对应｢亚[^simp]｣
⾑	|6笔	|𛊟	右上						|形似但不是｢襾｣
⾉	|7笔	|𛉴𛊇𛊲𛊷𛋀𛋕	右边
龺	|8笔	|𛊻𛋺	右边						|女漢[^NHZD]￫源自｢朝｣省略
昌	|10笔	|𛋬𛋳𛋷	右边						|⿱𛇈𛇈
ㆬ	|4笔	|𛉰𛉆𛊝𛊸𛋂	下边						|形似ᲅ
Ш	|4笔	|𛉆𛋄	右上
|	|	|	**↓以下是瞎掰都掰不出的**
①	|5笔	|𛈟𛊏𛈝	右上						|⿼⿶𛆀..，形似｢半｣无脚
②	|6笔	|𛊄	右边；𛋜𛋰	下边					|⿵⿰ㄑȜ:，女漢[^NHZD]￫源自｢乃｣
③	|4笔	|𛆱𛈀𛉵	右边；𛇂𛈽	右下					|⿻丨⿻𛅰𠃋——不会拼，似｢去⻒｣共同下半
④	|7笔	|𛊉𛋛𛋴	右上						|形似𛈾，但不出头
⑤	|5笔	|𛋂𛋃𛋞	上边						|⿱𛆀⿰..

</details>


# 女书排版
原本不用标点或空格，某种程度上算音节文字，但大多女字是多音字（一对多。而且也有同音异形字，多对一）所以不是。实际上女书在同一篇文中对同一事物会用不重复的女字表达，避免文章呆板[^4Nyu]。上面提到的𛈺｢伴｣，《女漢[^NHZD]》称有40多个变体，但未逐一给出来源。

女书重文号(叠字符)｢𖿡｣是必须的（《女漢[^NHZD]》所示变体超过6种，若属实的话），并非图省笔的略写，即便是｢人人｣也得写作｢𛅳𖿡｣[^HYX]。

女书“换行符”是可见的，有2个，称为行尾填空符，竖排形如↓、o，填补行列的剩余空间，未见横排形式，统一码截至15.0版未收录。我需要斟酌字体该怎么做。目前暂用￬、㇣顶替。


# Sans
𛆁𛈬𛋚𛋒 | 女书黑体 | Nüshu Sans

为sans-serif样式，因撞车搁置中。不过字形与Noto完全不同，譬如我的黑体是菱形点。

## 致谢
这里列出帮忙绘制或修改𛆁𛈬𛇋𛋒字形的人。

对字体设计师而言，若要创作衍生字体，需以`Nyu`开头。如果该字体还有汉字或女书名，则需以`女`或`𛆁`开头。由于同名字体不能重复安装和同时使用，仅为避免未来字体名称撞车的目的，回避名称（Reserved Font Name）局限于`Nyushu` `𛆁𛈬𛇋𛆼` `𛆁𛈬𛇋𛋒` `女书柳叶` `女書柳葉`及这些[样式后缀](https://github.com/MY1L/Ctrl/blob/main/abbr.md)（含缩略及组合）。但若命名是必要的，可以[与我协商][Disc]，比OFL宽松，例如“女书柳叶体”是允许的，因为“体”不是样式后缀。

对字体使用者而言，个人非商业用途下使用是免费的，如果用在不错的作品上，不妨让我也看看。如果该作品有staff表或发布页面有简介，标注在那里即可。但若使用不满足前述条件，请[先问问我][Disc]。\
特别是，将字体用于商业项目或书籍而未盈利前不必捐赠我。如果在学术出版使用我的字体，也不必捐赠我，但欢迎向我发送该作品的网页版或pdf等电子档案。（If you do use any of my fonts for a commercial project or in a commercial book, please do consider making a donation that reflects their commercial worth to you. If you use my fonts in an academic publication then I do not expect a financial donation, but you are welcome to send me a copy of the publication if you think it may be of interest to me.）

<p align="right">（本页出现的“我”均为<strong>綿雲飴里</strong>，<a href="https://afdian.net/@FairyFloss">向我打赏或约稿请点这~</a>）</p>

[NyushuSrc.csv]: /NyushuSrc.csv
[n3340]: https://unicode.org/wg2/docs/n3340.pdf
[Disc]: https://github.com/MY1L/Nyushu/discussions "github论坛"
[Disc3]: https://github.com/MY1L/Nyushu/discussions/3 "设计心得与规范"

### 备注
[^o]: 《女漢》9~10页称小圈等符号在女书中有派生字“圈破”区分读音作用，不一定对应｢口｣
[^2d]: 但𛊭对应｢清｣，𛇼是｢到｣也是｢汪｣，此为我读《女漢》的疑点。
[^pa]: 但𛉣读mau³³，｢怕｣对应𛇲(pw¹³)，此亦为我读《女漢》的疑点。
[^simp]: 没错，《ISO/UCS 女书编码提案》[n3340]、《女漢》强调对应的就是简化字。不过｢虫｣在《女漢》外暂未查到。顺带一提[n3340]p25、26照片放反了。
[^4Nyu]: 范例可见《女漢》32页義年華感谢信，四句分别用“女文”“女书”“女字”“女文章”表述女书。
[^HYX]: 范例可见《中国女书合集》卷四（女书提案09-03-18[^3598]64页）何艳新“突然发生非**典**病 **人人**感觉好忧愁 万众一心团结起 坚决战胜非**典**病”
[^UNCO]: 指《比较》前附申报联合国教科文组织“世界记忆遗产名录”专家推荐书：季羡林、周有光、李学勤、谭琳、董琨 5位，除李学勤谨慎不提外，其余均认定妇女所创。
[^3598]: 女书提案09-03-18：[unicode.org/wg2/docs/n3598.pdf](https://unicode.org/wg2/docs/n3598.pdf "女书提案09-03-18.docx")，69页附 赵丽明“女书基本字与字源考”的2008年2月四稿，基本字共398字（可搜索文字，非扫描）
[^NSZT]: [女书规范字书法字帖](https://book.douban.com/subject/27045237/)，出版于2017-5（统一码10版公布前1个月），ISBN: 9787302467052，书法家似为[胡欣](http://www.thurcacca.org/booksearch.html)。
[^NHZD]: [女汉字典](https://book.douban.com/subject/2055324/)，出版于2006-8，ISBN: 9787810569866
[^NSZD]: [女书字典](https://book.douban.com/subject/1417170/)，出版于2002-1-1，ISBN: 9787806652343
[^NSHJ]: [中国女书合集](https://book.douban.com/subject/1434610/)，出版于2005-1，ISBN: 9787101044058
[^NSDB]: ISBN-10: [7-80198-261-4](https://isbnsearch.org/isbn/7801982614)，豆瓣数据有误。不过，著者还有[女书读本](https://book.douban.com/subject/10779889/)，出版于2008-6，ISBN: 9787543852822，第五章：女书用字比较，照片见于[清华大学抢救女书SRT小组](http://www.thurcacca.org/bookpage/38/)
[^NSBZ]: [在线女书字典](https://nushuscript.org/) > 工具，我咨询相关人士，称其不可靠。