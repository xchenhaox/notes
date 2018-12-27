
##Vim 实用技巧（Drew Neil 著）
2018/06/11

vim -u NONE -N

ESC 切换模式


:help <命令>
:h <命令>
:h vimtutor 查看文档
:h key-notation 按键标记方式


.
* 查找当前光标下的单词
$ 将光标移到行尾
i 从光标所字符前前追加
I 在行首添加
a 从光标所在字符后追加
A 在行尾追加
o 在下一行添加
O 在上一行添加
f{char} 在行内查找一下指定字符并将光标移到那里
t{char} 
F{char} 在行内查找上一指定字符
T{char}
; 重复上次f命令所查找的字符
, 反向查找f所查找的字符
/pattern 在文档中查找下一处匹配项
?pattern
n 正向继续查找
N
:s/target/replacement 替换
:%s/content/copy/g
&
qx{changes}q
@x



:set hls 高亮显示匹配内容
s 删除光标下的字符并插入模式
cw 删除从光标位置到当前词结尾处的文本并切换到插入模式
x 删除光标下的字符
u 撤销上次修改
dd 剪切行
>> 缩进当前行
gUgU
gUU
>G 增加从当前行到文档末尾处的缩进层级
j 使光标下移一行
:grep Waldo *




k <Up>
j <Down>
h <Left>
l <Right>

db 删除从光标起始位置到单词开头的内容
b 把光标移到单词的开头
dw 删除整个单词
daw 删除整个单词
<数字><命令> 指定命令执行次数
<数字>Ctrl+a 把当前光标之上或之后数值加<数字>，如果光标不在数字上则在当前行正向查找一个数字，如果找到了就径直跳到那里。在不带<数字>执行时，会逐个加减
<数字>Ctrl+x 对数字减

d2w 删除单个单词
2dw
c3w
操作符+动作命令=操作
d{motion}
dl
daw
dap
c{motion}
y{motion}

c 修改
d 删除
y 复制到寄存器
> 增加缩进
> 减小缩进
= 自动缩进
=G 自动缩进从光标位置到文件结尾的所有内容
g~ 反转大小写
gu 转换为小写
gU 转换为大写
gUaw
gUap
! 使用外部程序过滤{motion}所跨越的行
\\{motion}
\\ap 切换当前段落的注释状态
\\G 从当前行到文件结尾间的所有内容注释掉
\\\ 注释当前行














插入模式
Ctrl+h 删除前一个字符（退格键）
Ctrl+w 删除前一个单词
Ctrl+u 删至行首
Esc 切换到普通模式
Ctrl+[ 切换到普通模式
Ctrl+o 切换到插入-普通模式
	插入-普通模式：它能让我们执行一次普通模式命令。在此模式中，我们可以执行一个普通模式命令，执行完后，马上就又返回到插入模式
	zz 重绘屏幕，并把当前行显示在窗口正中

yt, 把,前的文本复制到专用寄存器中
Ctrl+r{register}
Ctrl+r0 粘贴到光标所在位置
Ctrl+rCtrl+p{register} 按原义插入寄存器内的文本并修正任何不必要的缩进
Ctr+r=6*35 表达式寄存器

Ctrl+v{code} 用字符编码插入非常用字符
> Ctrl+v{065} 以十进制字符编码插入字符
Ctrl+vu{1234} 以十六进制字符编码插入字符
Ctrl+vu00bf
如果想知道文档中任意字符的编码，只需把光标移到它上面并按ga命令，然后屏幕下方就会显示出一条消息，分别以十进制和十六进制的形式显示出其字符编码
Ctrl+v非数字键 插入这个按键本身所代表的字符
Ctrl+r<Tab> 插入制表符
Ctrl+k{char1}{char2} 以二合字母{char1}{char2}插入字符
R 由普通模式进入替换模式

gR 切换到虚拟替换模式（会把制表符当成一组空格进行处理） 
r{char}
gr{char}




可视模式
Ctrl+g 在可视模式及选择模式间切换
	在选择模式中输入任意可见字符的话，此字符会替换所选内容并切换到插入模式
viw 
v 激活面向字符的可视模式（再按v会回到普通模式）
V 激活面向行的可视模式
Ctrl+v 激活面向列块的可视模式
gv 重选上次的高亮选区
o 切换高亮选区的活动端






命令行模式
/
Ctrl+r=
:edit
:write
:tabnew
:split
:prev
:next
:bprev
:bnext
:[range]copy {address} 在指定范围内的行拷贝到{address}所指定的行之下
:[range]move {address} 在指定范围内的行移到到{address}所指定的行之下
:[range]join 连接指定范围内的行
:[range]normal {commands} 对指定范围内的每一行执行普通模式命令{commands}
:[range]delete [x] 删除指定范围内的行[到寄存器x中]
:[range]yank [x] 复制指定范围的行[到寄存器x中]
:[line]put [x] 在指定行后粘贴寄存器x中的内容
:[range]substitute/{pattern}/{string}/[flags] 把指定范围内出现{pattern}的地方替换为{string}
:[range]global/{pattern}/[cmd] 对指定范围内匹配{pattern}的所有行，在其上执行Ex命令{cmd}

Ctrl+w 删除至上个单词的开头
Ctrl+u 删除至上个单词的行首
Ctrl+k
Ctrl+v
Ctrl+r{register}


:1 跳到指定到的行
:print 打印光标所在行
:$ 跳到文件末尾
:p 同:print
:3p 跳到第3行并打印
:3d 跳到第3行并删除此行
:2,5p 打印2到5行(光标将停留在第5行)
:.,$p 打印当前光标所在行至文件末尾
:%p 打印当前文件中的所有行
:%s/Practical/Pragmatic/

3G 跳到第3行
VG 进行可视模式选区到结尾
:'<,'>p 打印上一次高亮选区所选中的内容
:/<html>/,/<\/html>/p 打印<html>所在行到对应闭标签所在行
:/<html>/+,/<\/html>/-1p 偏移
	（偏移的一般形式:{address}+n，若n被省略，那么缺省偏移量为1。{address}可以是一个行号、一个位置标记或是一个查找模式）
:2
:.,.+3p

Ex命令的地址及范围的符号：
1 文件的第一行
$ 文件的最后一行
0 虚拟行，位于文件第一行上方
. 光标所在行
'm 包含位置标记m的行
'< 高亮选区的起始行
'> 高亮选区的结束行
% 整个文件（:1,$的简写形式）

:copy (简写:t，或:co)
:move

:6copy 将第6行复制到当前行的下方
:6t.
:t6 把当前行复制到第6行下方
:t. 为当前行创建一个副本（类似于yyp） 区别：yyp全使用寄存器，而:t.则不会）
:t$ 把当前行复制到文本结尾
:'<,'>t0 把高亮选中的行复制到文件开头

Ctrl+o 跳回原先的位置
:[range]move {address}
:m
:'<,'>m$
dGp
Vjj
@: 重复上次的Ex命令
:'<,'>normal . 对整个范围内的连续行同时执行.命令
:%normal A;
:%normal i// 在执行指定的普通模式命令之前，Vim会先把光标移到该行的起始处。因此在执行时用不着担心光标的位置
:normal @q
遍历缓冲区列表
:bnext
:bn
:previous
:p
@: 寄存器:总是保存着最后执行的命令行命令。在运行过一次@:后，后面就可以用@@命令来重复它
Ctrl+o
:tnext

:col<Ctrl+d> 显示可用的补全列表
	按Tab或S+Tab正向、反向遍历补全列表
	
:tag ...
:set ...
:help ...

<Ctrl+r><Ctrl+w> 会复制光标下的单词并把它插入到命令行
<Ctrl+r><Ctrl+a> 插入光标下的字串



:<Up> 回溯历史命令
:<Down>

:write
:!ruby %
:q

J
q/ 打开查找命令历史的命令行窗口
q: 打开Ex命令历史的命令行窗口
Ctrl+f 从命令行模式切换到命令行窗口


:!ls 调整Shell的程序
:ls 显示缓冲区列表的内容

在Vim的命令行中，符号%代表当前文件名（在运行那些操作当前文件的外部命令时，我们可以使用它）
:!{cmd} 适用于执行一次性命令
:shell 启动一个交互的shell会话
	pwd
	ls
	exit 退出此shell并返回Vim

Ctrl+z 挂起Vim所属的进程，并把控制权交还给bash
jobs 查看当前的作业列表
fg 唤醒一个被挂起的作业，把它移到前台

:read !{cmd} 把命令的标准输出重定向到缓冲区（把标准输出插入到光标下方）
:[range]write !{cmd} 把缓冲区内容作为指定{cmd}的标准输入
:write! sh 覆盖任何已存的sh文件
:[range]!{filter} 使用外部程序{filter}过滤指定的[range]

:2,$!sort -t',' -k2









:args
:argdo



:write
:update
:saveas

vim *.txt
:ls 列出所有被载入到内存中的缓冲区的列表
:bnext 切换到列表的下一个缓冲区
:bpre
Ctrl+^ 可以在当前文件和软换文件间快速切换
:bfirst 跳到缓冲区列表的开头
:blast
:buffer N 直接凭编号中跳转到一个缓冲区
:buffer {bufname} 其中{bufname}只需包含文件路径中足以唯一标识此缓冲区的字符即可
:bufdo 允许我们在:ls列出的所有缓冲区上执行Ex命令
:bf
:bn
:b N
:first
:last
:next
:n
:previous



:bdelete N1 N2 N3 删除缓冲区
:N,M bdelete


:args 参数列表记录了在启动时作为参数传递给 Vim 的文件列表
:args {arglist}
:args index.html app.js 填充参数列表


vim code/files/mvc/

*符号用于匹配0个或多个字符，但它的范围仅局限于指定的目录，而不会递归其子目录
**也匹配0个或多个字符，但它可以递归进入指定目录的子目录
:args *.*
:args **/*.js
:args **/*.js **/*.css
:args **/*.*
:args `cat .chatpters`
:next 遍历参数列表中文件
:prev

:argdo 在列表中每个缓冲区上执行同一条命令

:quit
:edit! 重新从磁盘读取此文件（回滚所做修改:）
:e!
:qall! 退出Vim而不想对未保存的修改进行检查
:qa!
:wall 保存所有有改动的缓冲区而无需逐个检查
:wa!
:argdo write



Ctrl+ws水平切分窗口
Ctrl+wv垂直切分窗口
:split {file} 水平切分窗口，并在新窗口载入{file}
:sp {file}
:vsplit {file} 垂直切分窗口，并在新窗口载入{file}
:vsp {file}

Ctrl+ww 在窗口间循环切换（或Ctrl+w Ctrl+w）
Ctrl+wh 切换到左边的窗口
Ctrl+wj 切换到下边的窗口
Ctrl+wk 切换到上边的窗口
Ctrl+wl 切换到右边的窗口

:close 关闭活动窗口
:clo
Ctrl+wc
:only 只保留活动窗口，关闭其他所有窗口
:on
Ctrl+wo


Ctrl+w= 使所有窗口等宽、等高
Ctrl+w_ 最大化活动窗口的高度
Ctrl+w| 最大化活动窗口的宽度
NCtrl+w_ 把活动窗口的高度设为N行
NCtrl+w| 把活动窗口的宽度设为N列

:lcd {path} 让我们可以设置当前窗口的本地工作目录

:tabedit {filename} 在新标签页中打开{filename}
:tabe
Ctrl+wT 把当前窗口移到一个新标签页
:tabclose 关闭当前标签页及其中的所有窗口
:tabc
:tabonly 只保留活动标签页，关闭所有其他标签页
:tabo


:tabnext {N} 切换到编号为{N}的标签页
:tabn {N} 切换到下一标签页
	{N}gt
:tabnext 切换到下一标签页
:tabn
	gt
:tabprevious 切换到上一标签页
:tabp
	gT
:tabmove [N] 重排标签页（当 [N] 为0时，当前标签页会被移到开头；如果省略了 [N]，当前标签页会被移到结尾）






:pwd
:edit {file} 可以接受相对于工作目录的文件路径
:edit %Tab
:edit %:hTab 修饰符:h会去除文件名，但保留路径中的其他部分


:set path
:set path+=app/**
:find Main.js 打开文件


vim ./ 打开文件管理器
:edit . 打开文件管理器并显示当前工作目录
:e .
:e.
:Explore 打开文件管理器并显示活动缓冲区所在的目录
:E

:Sexplore 在一个水平切分窗口打开文件管理器
:Vexplore 在一个垂直切分窗口打开文件管理器


:edit {file} 如果{file}不存在则会创建一个新的空白缓冲区（创建新文件）
Ctrl+g 显示当前文件的文件名及状态

:!mkdir -p %:h










h 左移一列
l 右移一列
j 下移一行
k 上称一行
:set number
:set nu
j 根据实际行向下及向上移动
k
gj 按屏幕行向下及向上移动
gk
0 移动到实际行的行首
g0 移动到屏幕行的行首
^ 移动到实际行的第一个非空白字符
g^ 移动到屏幕行的第一个非空白字符
$ 移动到实际行的行尾
g$ 移动到屏幕行的行尾


w 正向移动到下一单词的开头
b 反向移动到当前单词/上一单词的开头
e 正向移动到当前单词/下一单词的结尾
ge 反向移动到上一单词的结尾

一个单词由字母、数字、下划线，或其他非空白字符的序列组成，单词间以空白字符分隔
字串由非空白序列组成，字串间以空白字符分隔
W
B
E
gE


cw

f{char} 在光标位置与当前行行尾之间查找指定的字符，如果找到了就会把光标移到此字符上；如果未找到则保持光标不动
; 重复上次的字符查找命令
, 反转方向查找上次的字符查找命令
f{char} 正向移动到下一个{char}所在之处
F{char} 反向移动到上一个{char}所在之处
t{char} 正向移动到下一个{char}所在之处的前一个字符上
T{char} 反向移动到上一个{char}所在之处的后一个字符上


f,
dt.

/take
n
N

d/ge



分隔符广本对象
a) 或 ab 一对圆括号
i) 或 ib 圆括号内部
a} 或 aB 一对花括号
i} 或 iB 花括号内部
a] 一对方括号
i] 方括号内部
a> 一对尖括号
i> 尖括号内部
a' 一对单引号
i' 单引号内部
a" 一对双引号
i" 双引号内部
a` 一对反引号
i` 反引号内部
at 一对XML标签
it XML标签内部


iw 当前单词
aw 当前单词及一个空格
iW 当前字串
aW 当前字串及一个空格
is 当前句子
as 当前句子及一个空格
ip 当前段落
ap 当前段落及一个空格



m{a-zA-Z} 用选定的字母标记当前光标所在的位置
		小写位置标记只在每个缓冲区里局部可见
		大写位置标记则全局可见
'{makr} 跳到位置标记所在行，并把光标置于该行第一个非空白字符上
`{mark} 把光标移到到设置此位置标记时光标所在之处（恢复行、列）的位置

`` 当前文件中上次跳转动作之前的位置
`. 上次修改的地方
`^ 上次插入的地方
`[ 上次修改或复制的起始位置
`] 上次修改或复制的结束位置
`< 上次高亮选区的起始位置
`> 上次高亮选区的结束位置


% 允许我们在一组开、闭括号间跳转，可作用于()、{}、以及[]




Ctrl+o 后退
Ctrl+i 前进
:jumps 查看跳转列表

跳转动作
[count]G 跳转到指定的行号
/pattern 跳转到下一个/上一个模式出现之处
?pattern
n
N
% 跳转到匹配的括号所在之处
( 跳转到上一句/下一句的开头
)
{ 跳转到上一段/下一段的开头
}
H 跳到屏幕最上方/正中间/最下方
M
L
gf 跳转到光标下的文件名
Ctrl+] 跳转到光标下关键字的定义处
'{mark} 跳转到一个位置标记
`{mark}


:changes 查看改变列表
g; 反向遍历改变列表
g,



gf 尝试打开光标下的文件（会检查 path 目录列表中的每个目录，看该目录中是否包含一个匹配光标下文本的文件名，path 也会用于 :find 命令）
:set suffixesadd+=.rb
Ctrl+o 返回原处
:set path?
	path=.,/usr/include,, 其中.代表当前文件所在的目录，而空字符则代表工作目录

Ctrl+] 也需要进行一些配置


:vimgrep 会直接跳转到它所找到的第一处匹配上，这或许会切换到另外一个文件
:vimgrep /fooBar/ **
Ctrl+o 返回



qq 录制？



xp 调换光标之后的两个字符
dd 调换当前行和它的下一行

"{register} 指定要用的寄存器（若不指明 Vim 将缺省使用无名寄存器）
"bdd 把当前整行文本剪切至寄存器b中
"ap 粘贴来自寄存器a的内容

"_ 黑洞寄存器

:delete c 当前行剪切到寄存器c
:put c 粘贴来自寄存器c的内容至当前光标所在行之下

"" 无名寄存器
""p  等同于 p
"0 复制专用寄存器：使用 y{modtion} 命令（仅当）时，要复制的文本不仅会被拷贝到无名寄存器中，而且也被拷贝到了复制专用寄存器中

:reg "0

有名寄存器"a-"z
用小写字母引用有名寄存器，会覆盖该寄存器的原有内容
换用大写字母的话，则会将新内容添加到该寄存器的原有内容之后

"+ 系统剪贴板
"* 选择专用寄存器

"= 表达式寄存器


其它寄存器
"% 当前文件名
"# 轮换文件名
". 上次插入的文本
": 上次执行的 Ex 命令
"/ 上次查找的模式


p 将寄存器中的文本粘贴到光标之后
P 将文本插入到光标之前

Ctrl+r{register} 粘贴面向字符的文本区域
Ctrl+r"
Ctrl+r0


gp
gP





宏
q 录制/停止
q{register}
:reg a
@{register} 执行指定寄存器的内容
@@ 重复最近调用过的宏

如果宏执行动作命令失败了，Vim 将中止执行宏的其余命令
10@q 指定执行次数
:'<,'>normal @a

qa 覆盖宏
qA 追加宏

:argdo normal @a

:let i=0
:echo i
:let i += 1
:echo i
Ctrl+r=i


/#\([0-9a-fA-F]\{6}\|[0-9a-fA-F]\{3}\)
/\v#([0-9a-fA-F]{6}|[0-9a-fA-F]{3})
/\v#(\x{6}|\x{3})

/a.k.a.
/a\.k\.a\.
/\Va.k.a.

/\v<(\w+)\_s+\1>


/v%(And|D)rew Neil 指示Vim不要将括号内的内容赋给寄存器\1
:%s//\2, \1/g


\w
\W
\zs
\ze

/\v"[^"]+"
/\v"\zs[^"]+\ze"    引号本身被排除于匹配之外，只剩下引用的内容被高亮起来

/\Vhttp:\/\/vimdoc.net\/search?q=\/\\
?http://vimdoc.net/search\?q=/\\



:set nohlseach
:se nohls
:se hls!




Ctrl+rCtrl+w 会用当前预览的匹配结果对查找域进行自动补全

:%s///gn 统计当前模式的匹配个数（n抑制正常的替换动作）

/\X(ht)?mlo\C

/\v'.+'
/\v'[^']+'
/\v'([^']|'\w)+'
:%s//"\1"/g


q/ 调出命令行窗口



:[range]s[ubstitute]/{pattern}/{string}/[flags]
标志位
g 在全局范围内执行
c 询问确认与否
n 抑制替换行为，而是报告本次匹配的个数
& 指示Vim重用上一次所用过的标志位

替换域的特殊字符
\r 插入一个换行符
\t 插入一个制表符
\\ 插入一个反斜杠
\1 插入第1个子匹配
\2 插入第2个子匹配（以此类推，最多到\9）
\0 插入匹配模式的所有内容
& 插入匹配模式的所有内容
= 使用上一次调用:substitue时的{string}
\={Vim script} 执行{Vim script}表达式，并将返回的结果作为替换{string}


:set hlsearch
:%s/going/rolling/g

:%s/content/copy/gc
交互选项：
y 替换此处匹配
n 忽略此处匹配
q 退出替换过程
l "last"替换此处匹配后退出
a "all"替换此处与之后所有的匹配
Ctrl+e 向上滚动屏幕
Ctrl+y 向下滚动屏幕

	
	
:%s/\v'(([^']|'\w)+)'/"\1"/g
/\v'(([^']|'\w)+)'
:%s//"\1"/g

:%s/\n/,


:%s/<Ctrl+r>//"\1"/g 把上次的查找内容粘贴进来
:%s//<Ctrl+r>0/g  将寄存器的内容插入到命令行
:%s//\=@0/g


g& 在整个文件的范围内重复 substitute 命令

:&& 重新执行替换操作（作用于当前行）
:'<,'>&& 作用于高亮选区
:%&& 作用于整个文件



/\v\<\/?h\zs\d
:%s//\=submatch(0)-1/g



:let swapper={"dog":"man","man":"dog"}
:echo swapper["dog"]
:echo swapper["man"]
/v(<man>|<dog>)
:%s//\={"dog":"man","man":"dog"}[submatch(1)]/g



/Pragmatic\ze Vim
:%s//Practical/g
:args **/*.txt
:set hidden 启用该设置后，我们就可以在不保存文件改动的前提下，跳转至其它文件了
:argdo %s//Practical/g
:argdo %s//Practical/ge 加上e屏蔽错误消息（找不到模式：有些文件中没有查找到）
:argdo update  其中:update 用于保存文件，但只有在文件发生改动时，才会被执行）



/Pragmatic\ze Vim
:vimgrep /<Ctrl+r>// **/*.txt
:copen









:[range]global[!] /{pattern}/ [cmd]
缺少情况下 :global 作用范围为整个文件%
如果查找域留空则自动使用当前的查找模式
如果我们不指定任何 [cmd]，缺省使用 :print
:global! 或 :vglobal 反转执行


/v\<\/?\w+>
:g//d

:vglobal 简写 :v
:v/href/d


:g/TODO
:reg a
:g/TODO/yank A
:reg a
:g/TODO/t$


:sort
:'<,'>sort


:g/{start}/ .,{finish} [cmd]

:g/{/ .+1,/}/-1 sort


:g/{pattern}/[cmd]
:g/{pattern}/[range][cmd]


:.+1,/}/-1 sort

:g/{/ .+1,/}-1 >











ctags
安装：
sudo apt-get install exuberant-ctags #Ubuntu
brew install ctags #OS X

ctags *.rb 生成标签文件

:!ctags -R 从Vim当前的工作目录开始，遍历其所有的子目录，并为其中的每一个文件建立索引，最终再把这个标签文件保存到当前工作目录中


Ctrl+] 光标将从当前所在的关键字跳转到它的定义处
Ctrl+t 后退返回
:pop 同 Ctrl+t
gCtrl+] 如果发生了多处匹配的情况，标签匹配列表中可选择
:tselect 调出标签匹配列表，从而进行回溯
:tprev
:tnext
:tfirst
:tlast


:tag {keyword} 等同于 Ctrl+]
:tjump {keyword} 等同于 gCtrl+]

:tag /{pattern}
:tjump /{pattern}







浏览 Quickfix 列表的命令
:cnext 跳转到下一项
:cprev 跳转到上一项
:cfirst 跳转到第一项
:clast 跳转到最后一项
:cnfile 跳转到下一个文件中的第一项
:cpfile 跳转到上一个文件中的最后一项
:cc N 跳转到第n项
:copen 打开quickfix窗口
:cclose 关闭quickfix窗口

:colder 回溯 quickfix 列表之前的某个版本（支持次数）
:cnewer


vim goldrush.txt +9
:grep Waldo *
:grep -i Waldo *


:vim[grep][!] /{pattern}/[g][j] {file}...

/\v'(([^']|'\w)+)'
:vim /<Ctrl+r>// **
如果将模式域清空的话，将会匹配所有被查找文件内的所有文本行




Ctrl+p 触发自动补全（反向选择）
Ctrl+n

Ctrl+xCtrl+n 当前缓冲区关键字
Ctrl+xCtrl+i 包含文件关键字
Ctrl+xCtrl+] 标签文件关键字
Ctrl+xCtrl+k 字典查找
Ctrl+xCtrl+l 整行补全
Ctrl+xCtrl+f 文件名补全
Ctrl+xCtrl+o 全能（Omni）补全

<Down> 选择来自补全列表的下一个匹配项
Ctrl+y 确认使用当前选中的匹配项(yes)
Ctrl+e 还原最早输入的文本（从自动补全中exit）
Ctrl+h 从当前匹配项中删除一个字符  (<BS>)
Ctrl+l 从当前匹配项中增加一个字符
{char} 中止自动补全并插入字符{char}



:set spell
]s 跳到下一处拼写错误
[s 跳到上一处拼写错误
z= 为当前单词提供更正建议
zg 把当前单词添加到拼写文件中
zw 把当前单词从拼写文件中删除
zug 撤销针对当前单词的zg或zw命令

---



编辑器之神-vim
vi简介
vi是“Visual interface”的简称，它在Linux上的地位就仿佛Edit程序在DOS上一样。它可以执行输出、删除、查找、替换、块操作等众多文本操作，而且用户可以根据自己的需要对其进行定制。Vi不是一个排版程序，它不象Word或WPS那样可以对字体、格式、段落等其他属性进行编排，它只是一个文本编辑程序。 vi没有菜单，只有命令，且命令繁多。

Vi有三种基本工作模式：
+  命令模式
+  文本输入模式
+  末行模式。 
vim模式

命令行模式
任何时候，不管用户处于何种模式，只要按一下ESC键，即可使Vi进入命令模式；我们在shell环境(提示符为$)下输入启动Vi命令，进入编辑器时，也是处于该模式下。在该模式下，用户可以输入各种合法的Vi命令，用于管理自己的文档。此时从键盘上输入的任何字符都被当做编辑命令来解释，若输入的字符是合法的Vi命令，则Vi在接受用户命令之后完成相应的动作。但需注意的是，所输入的命令并不在屏幕上显示出来。若输入的字符不是Vi的合法命令，Vi会响铃报警。

文本输入模式
在命令模式下输入插入命令i、附加命令a 、打开命令o、修改命令c、取代命令r或替换命令s都可以进入文本输入模式。在该模式下，用户输入的任何字符都被Vi当做文件内容保存起来，并将其显示在屏幕上。在文本输入过程中，若想回到命令模式下，按键ESC即可。

末行模式
末行模式也称ex转义模式。在命令模式下，用户按“:”键即可进入末行模式下，此时Vi会在显示窗口的最后一行(通常也是屏幕的最后一行)显示一个“:”作为末行模式的提示符，等待用户输入命令。多数文件管理命令都是在此模式下执行的(如把编辑缓冲区的内容写到文件中等)。末行命令执行完后，Vi自动回到命令模式。例如：

:sp newfile
则分出一个窗口编辑newfile文件。如果要从命令模式转换到编辑模式，可以键入命令a或者i；如果需要从文本模式返回，则按Esc键即可。在命令模式下输入“:”即可切换到末行模式，然后输入命令。

vim基础操作
vim是从 vi 发展出来的一个文本编辑器 。代码补完、编译及错误跳转等方便编程的功能特别丰富

进入插入模式:

i: 插入光标前一个字符 

I: 插入行首 

a: 插入光标后一个字符 

A: 插入行未 

o: 向下新开一行,插入行首 

O: 向上新开一行,插入行首
进入命令模式:

ESC:从插入模式或末行模式进入命令模式

移动光标:

h: 左移 

j: 下移 

k: 上移 

l: 右移

M: 光标移动到中间行 

L: 光标移动到屏幕最后一行行首 

G: 移动到指定行,行号 -G

w: 向后一次移动一个字 

b: 向前一次移动一个字

{: 按段移动,上移 

}: 按段移动,下移

Ctr-d: 向下翻半屏 

Ctr-u: 向上翻半屏

Ctr-f: 向下翻一屏 

Ctr-b: 向上翻一屏

gg: 光标移动文件开头 

G: 光标移动到文件末尾
删除命令:

x: 删除光标后一个字符,相当于 Del 

X: 删除光标前一个字符,相当于 Backspace

dd: 删除光标所在行,n dd 删除指定的行数 D: 删除光标后本行所有内容,包含光标所在字符 

d0: 删除光标前本行所有内容,不包含光标所在字符

dw: 删除光标开始位置的字,包含光标所在字符
撤销命令:

u: 一步一步撤销 


Ctr-r: 反撤销
重复命令:

.: 重复上一次操作的命令
文本行移动:

>>: 文本行右移 

<<: 文本行左移
复制粘贴:

yy: 复制当前行,n yy 复制 n 行 

p: 在光标所在位置向下新开辟一行,粘贴
可视模式:

v: 按字符移动,选中文本 

V: 按行移动,选中文本可视模式可以配合 d, y, >>, << 实现对文本块的删除,复制,左右移动
替换操作:

r: 替换当前字符 

R: 替换当前行光标后的字符
查找命令:

/: str查找
n: 下一个
N：上一个
替换命令：

把abc全部替换成123

末行模式下，将光标所在行的abc替换成123
:%s/abc/123/g

末行模式下，将第一行至第10行之间的abc替换成123
:1, 10s/abc/123/g
vim里执行 shell 下命令:

末行模式里输入!,后面跟命令













vim分屏操作
分屏操作:

sp: 上下分屏,后可跟文件名 

vsp: 左右分屏,后可跟文件名

Ctr+w+w: 在多个窗口切换
启动分屏:

1.使用大写O参数进行垂直分屏

$ vim -On file1 file2 ...
2.使用小写o参数进行水平分屏

$ vim -on file1 file2 ...
注: n是数字，表示分屏的数量,n要大于等于文件个数

关闭分屏

1.关闭当前窗口

ctrl+w c
2.关闭当前窗口，如果只剩最后一个，则退出vim

ctrl+w q
编辑中分屏

1.上下分割当前打开的文件

ctrl+w s
2.上下分割，并打开一个新的文件

:sp filename
3.左右分割当前打开的文件

ctrl+w v
4.左右分割，并打开一个新的文件

:vsp filename
分屏编辑中光标的移动

vi中的光标键是h,j,k,l,要在各个屏之间切换，只需要先按一下ctrl+w

1.把光标移动到上边的屏

ctrl+w k
2.把光标移动到下边的屏

ctrl+w j
3.把光标移动到右边的屏

ctrl+w l
4.把光标移动到左边的屏

ctrl+w h
5.把光标移动到下一个的屏

ctrl+w w
移动分屏

1.向上移动

ctrl+w K
2.向下移动

ctrl+w J
3.向右移动

ctrl+w L
4.向左移动

ctrl+w H
屏幕尺寸

1.增加高度

ctrl+w +
2.减少高度

ctrl+w -
3.让所有屏的高度一致

ctrl+w =
4.左加宽度

ctrl+w >
5.右加宽度

ctrl+w <
6.右增加n宽 (如：n=30)

ctrl+w n <
vim打造IDE
简洁版IDE
C+p: 生成tags
C+]: 跳转到函数定义
C+t：从函数定义返回

C+o：在左侧打开文件列表
F4:  在右侧打开函数列表

C+n：补齐函数，向下翻
vimrc是vim的配置文件，可以修改两个位置

1. /etc/vim/vimrc

2.~/.vimrc

~/.vimrc优先级高

