一、常用工具：

1、浏览器：chrome、firefox

2、编辑器：intelliJ IDEA、sublime

3、版本控制：git、svn

4、后端：tomcat、maven、nodejs、mongodb、java、石墨vpn、fileZilla、天行vpn翻墙

5、包管理工具：homebrew

6、沟通交流：foxmail、qq、wechat、钉钉

7、个人知识管理：Evernote、百度云盘



二、使用技巧：

1、软件安装：
* 下载以.dmg结尾的压缩包，解压后安装到mac应用程序里(如chrome)； 
* homebrew安装：terminal终端输入命令—— brew install nodejs/tomcat等；软件默认安装在/usr/yujian/local/Cellar；

2、文件共享：
* 使用mac自带的airdrop实现文件共享
* 参考资料：http://jingyan.baidu.com/article/6dad5075f7fb7aa123e36e86.html
* 我的airdrop共享名称： 余健的MacBook Pro
3、vpn设置:
* 系统偏号设置—>网络—>添加vpn(接口选择vpn;类型选择L2tp;创建）—>输入服务器地址:114.55.124.15、账户名称—>点击签定设置（输入vpn密码、共享密钥aGELf6EsInxB2YiuSzJoqj1JcL2bc）—>点击连接即可； 
4、java项目启动，以btime.console为例：
* 相关的依赖：intelliJ IDEA /tomcat/maven/svn/相关权限开通（svn/vpn）
* SVN下载代码：打开idea—>选择从svn下载代码(输入svn用户名和密码)—>选择下载到mac文稿自定义目录下即可；
* 配置tomcat：打开idea系统设置—>选择Application Server—>新建tomcat server，tomcat home输入/usr/local/Cellar/tomcat/8.5.12/libexec即可；参考资料：http://www.cnblogs.com/sweetie/archive/2011/05/17/2049078.html
    * 命令行启动/停止tomcat：cd到tomcat目录（可选），输入catalina run/stop;
    * 参考资料：http://blog.sina.com.cn/s/blog_76550fd70101fn14.html
    * 参考资料：http://www.cnblogs.com/sweetie/archive/2011/05/17/2049078.html
* 配置maven:打开idea系统设置—>搜索maven并设置
    * maven home directory :/usr/local/Cellar/apache-maven-3.3.9;
    * User setting file:/usr/local/Cellar/apache-maven-3.3.9/conf/settings.xml
        * 修改配置文件setting.xml指定本地Repository目录<localRepository>/Users/yujian/Documents/yj/project/maven_dependency/Repository</localRepository>
    * Local responsity: /Users/yujian/Documents/yj/project/maven_dependency/Repository
* 配置JDK：
* 其他相关文件修改：
    * web.xml:
        * api.path=http://192.168.1.5:8080/btime.webser/api
        * api.config.hosts=http://test.qbb6.com/btime.webser
    * pom.xml:
        * <build>   <resources>      <resource>         <directory>src/main/resources/develop</directory>      </resource>   </resources></build>
        * pom.xml依赖更新后，maven 需要重新reImport
5、mac外接显示器：
* 依赖：显示器、HDMI转VGA接口转换器
* 操作流程：http://jingyan.baidu.com/article/fdbd4277cf6dc6b89e3f48e4.html
6、mac 下配置maven 环境变量：
* 打开终端，使用 touch 命令创建 .bash_profile 文件
    * touch .bash_profile
* 编辑刚刚创建的文件 .bash_profile
    * vim .bash_profile
* 使用vim 输入以下内容（:i,启动编辑模式，:wq,保存退出）
    * M2_HOME=/Users/lizhimin/Documents/maven/apache-maven-3.3.3（maven安装路径）
    * PATH=$M2_HOME/bin:$PATH
    * export M2_HOME 
    * export PATH
* 保存退出后，输入：
    * source .bash_profile
* 查看是否配置成功：
    * mvn -v
7、mac取消首字母自动大写：
* 设置 —> 键盘 —> 文本：取消自动首字母大写的选项
8、mac快速获取文件路径方法
* 窗口顶端标题中显示路径
    * 终端输入：defaults write com.apple.finder _FXShowPosixPathInTitle -bool TRUE;killall Finder
    * 还原：defaults delete com.apple.finder _FXShowPosixPathInTitle;killall Finder
* 参考资料：http://jingyan.baidu.com/article/380abd0a12007b1d91192c5e.html

三、常用命令及快捷键：

1、Mac快捷键:
* command+space：Spotlight搜索
* command+F3：回到桌面
* Ctrl+space：切换输入法
* Ctrl+W：关闭窗口
* command键相当于window中的ctrl键
* 不同程序切换：command+tab
* 同一程序不同窗口切换：command+`
* 全屏/退出：command+ctrl+F
* 隐藏应用：command + H
* 任务管理器：command + alt + Esc
* 截图：command + shift + 4  (图片自动保存在桌面)
* 截全图：command + shift + 3  (图片自动保存在桌面)

2、Mac手势：
* 单指按下：鼠标单击
* 双指按下：鼠标右键
* 双指上下滑动：鼠标滚轮，上下滚动页面； 

3、intelliJ IDEA for Mac 快捷键：keymap 选择Mac OS 10.5+
* 参考资料：http://www.cnblogs.com/exmyth/p/5949192.html
* 版本控制
    * 更新代码：command+t
    * 上传代码：command+k
    * 查看提交记录：fn + command + 9
    * 添加到svn：command + option + a
* 编辑相关：
    * 注释：command+/
    * 历史粘贴板：command+shift+v
    * 换行：shift+enter
    * 复制当前行：command+d
    * 删除当前行：command+delete
    * 上下移动当前行：command + shift + up/down
    * 折叠/展开代码块：command++/command+-
    * 折叠展开所有代码块：command+shift++/command+shift+-
    * 关闭当前选项卡：command+w
    * 格式化代码：command+option+l
    * 忽略格式化：@formatter:off的注释标记 
        * “<!--@formatter:off—>”
        * “@formatter:on“
    * 多行编辑：shift+option
    * 新建文件：command + N
    * 设置文件重命名：option + Q
    * 撤销：command + Z
    * 恢复撤销内容：command + shift + Z
    * 快速预览方法定义：option + space
    * 快速将选中内容一行显示：ctrl + shift + J
    * 快速添加代码模板片段：ctrl + command + S（自定义）
    * 安装vim插件
        * 设置启动快捷键：control + ,
    * 添加tasks：command + alt + N
        * 通过新建task，可以快速打开指定文件，并只提交指定文件；
    * 返回上一次操作位置：command + option + left/right;
    * 查看调用层次：fn + option + F7;
* 查询/替换：
    * 查找：command+f
    * 替换：command+r
    * Double shift
* 导航：
    * 跳转到指定行：command+l
    * 打开当前文件所在目录：fn+option+f1
    * 自动打开文件所在目录：目录设置，勾选autoScroll to Source 及 autoScroll from Source
    * 打开系统设置：command + ,
* 调试：
    * 查看变量值：option + 单击
    * 进入方法/类：command + 单击
    * 进入下一个断点：option+command + R
    * 打开server日志：command + 5
    * 查看接口实现类：c
* 激活：http://idea.iteblog.com/key.php

4.evernote印象笔记快捷键：
* 编辑：
    * 无序列表： command + shift + U
    * 有序列表：
    * 输入当前时间：command + shift + D
* 搜索：
    * 全局搜索：command + option + F
    * 局部搜索：command + F 

四、工作方式与方法：
  1.每天开始工作之前要把每天要做的事先列好，每天的事尽量在当天完成
  2.增加沟通，对于自己负责的活动或项目要主动跟进
  3.在提交测试之前要做好自测

五、chrome 快捷键使用 http://blog.csdn.net/duanyipeng/article/details/8637391
1. 调试：
    * 打开js文件：command+P
    * 搜索：command+F (支持css选择器)
    * 全局搜索：command+option+F
    * 打开元素审查：command+shift+C
    * 切换手机模式：command+shift+M
    * 跳转到下一个断点：command+\
    * 进入方法：command + ;
    * 跳出方法：command+shift+ ;
    * 取消断点：command+ F8
    * 跳转到指定行：ctrl+G
    * 查看获取页面的请求信息：Network>Doc；
    * 查看ajax请求：Network>XHR;
    * 获取当前元素：$0
    * 运行预定义的代码片段：Sources > Snippets
    
2. 浏览器常规操作：
    * 切换到第n个标签页：command+数字n
    * 切换到地址栏：command+L
    * 关闭标签页：command+W
    * 跳转到行尾/头：command+right/left
    * 刷新浏览器：command+R
    * 强制刷新浏览器：command+shift+R
    * 打开系统设置：command+ ,
    * 打开历史记录：command+Y
    * 收藏书签：command+ D
    * 改变开发工具位置：command + shift + D

六、terminal使用技巧：
1、编辑：
* Ctrl+A： 光标移动到行首
* Ctrl+E：光标移动到行尾
* Ctrl+C：强制退出
* Command+K：清屏
* Command+T：新建标签
* Double  Tab：快速选中列出的代选命令/文件

2、进程操作：
* Ps -A  | grep[process name regex]：查看指定进程 
    * 如： ps-A | grep tomcat : 查看tomcat 进程
* kill [PID]：强制kill掉指定进程
* sudo lsof -I -P | grep 9092 : 查看指定端口的PID
* lsof -I:8080 : 查看指定端口的PID

3、使用iTerm2代替系统自带的terminal
* 下载地址：http://www.iterm2.com/
* ssh登陆远程服务器本地免密钥登陆:
    * 参考资料：https://codingstyle.cn/topics/31
    * ssh脚本：
        * set timeout 30
        * spawn ssh root@192.168.1.3
        * expect {
        *              "(yes/no)?"
        *               {send "yes\n";exp_continue}
        *              "password:"
        *               {send "EqAnQyHz2iWexxHEuJJD7Rnd\n"}
        *              }
        * interact
    * 添加ssh脚本到iTerm2中：打开iTerm2的设置里，点开Profiles，左下角点+号新增一个配置文件，然后在Genernal->Command下选择 Command，在输入框里填入 expect ~/.ssh/whatevername (脚本所在目录)
    
4、查看本地ip
* ifconfig> in0 > inet对应的ip: http://192.168.200.182/

七、前端调试技巧：
1、打断点：
* 在页面中输入debugger
* 在chrome中打到相关文件，打断点；

八、ps技巧：
1、调整图片大小：
* 参考资料：http://jingyan.baidu.com/article/f71d60379f40031ab741d161.html

九、石墨vpn破解：
* 进入应用程序、删除原有石墨程序；
* 输入命令：sudo spctl --master-disable
* 解压即可；

十、vim使用技巧：
1. 快捷键：
    * 上下左右移动：HJKL;
    * 快速选中一个单词：viw;
    * 快速选中一行：shift + v;
    * 快速查找光标所在单词：*
    * 复制当前行：yy;
    * 删除当前行：dd;
    * 粘贴到下一行：p
    * 粘贴到上一行：P
    * 跳转到某行：37gg;
    * 跳转到顶部：gg;
    * 跳转到尾部：G；
    * 跳转到行尾：$;
    * 跳转到行首：0；
    * 上一行插入：o
    * 快速跳转到当前行字母a处：fa;
    * 查找fun：/fun;下一个查找项：n;上一个查找项：N;
    * 上一次编辑处：Ctrl + i;
    * 下一次编辑处：Ctrl + o;
    * 全局查找替换并确认：%s/旧字符/新字符/gc;
    * 重复上一个命令：.
    * 撤销操作：u

九、工作流及版本控制：
1. 代码部署正式环境前，需要记录提交的文件名，提交代码均以任务关键字开关：如妈妈群管理；
    1. 获取提交文件名：
        * idea版本控制提交记录(fn + command + 9)，filter工具可以筛选出任务关键字，Ctrl+C即可拷贝文件名；

十、前端问题域：
1. 用户体验：前端界面相关，需用户体验。在技术上包括「性能」「图形」「文本」3 大方面。
2. 团队协作：这是工程核心。 1000w 与 1亿 pv 流量，前后端有很大差异。
    * 后端因架构厚，问题多样化。异地，机房，SLA 等问题，不同量级架构完全不同。
    * 前端的架构薄，更重协作效率。前端在面对流量的架构上则无明显差异。但是，对「协作」的要求更高，加 1 个人手开发能更快，加 2 个人手开发效率比加 1 个人手快。我们现在所说的模块化，工程化，MV** 之类都是解决此类问题。
    * 链接：https://www.zhihu.com/question/31948284/answer/55972652
3. 资源管理：这是 Web 端与客户端差异。客户端把静态资源打包到 APP 里，而 Web 是通过中间 CDN 与 HTTP 的加载，所以如何优化静态资源（HTML/CSS/JavaScript）加载方式在架构中权重很大。

十一、linux命令：
1. 删除文件： rm -rf  文件名；

2. 查看文件内容： vi 文件名；



