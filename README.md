# 智能设计技术与方法课程 - 智能感知技术与硬件设计课堂资料
#### 龚卿


## 课堂内容回顾
本堂课在情绪设计的大背景下，详细讲解了实用的感知器和执行器，学习目标是学习者能够对智能硬件设计与开发快速入门，并且作为设计师了解当前的技术边界，不再被技术束缚，未来能够自顶而下地考虑产品设计方案。

在AI技术迅猛发展的当下，设计师入门嵌入式开发已经不再像过去一样困难，但却对AI产品设计带来了新的挑战。本堂课因此也介绍了AI产品设计的原则以及AI赋能的智能硬件开发工作流，帮助学习者对AI技术祛魅，拓宽思路，系统性认识AI赋能的嵌入式开发。

最后，本堂课安排了两项技术实验，在课堂条件与学习者拥有的实验材料受限的情况下，设计了用电脑摄像头模拟感知器，用电脑作为云计算服务器，用wokwi模拟执行器的技术实验。实验1为跑通我已经写好的实验程序，感受智能感知情绪的产品大概是一个什么样的使用体验；实验2为在我已写好的程序的基础上进行修改，并用wokwi连线新的元件，考察学习者是否能够活用本节课学习的知识，完成一个最简单的智能感知情绪产品原型。同时，我已写好的情绪感知软件亦可以作为后续课程大作业的基础算法参考，修改使用或直接使用。



## 实验1：运行“你开心所以我开心”模拟机器人原型
> 运行条件：有摄像头的windows 或 Mac电脑，且可以快乐上网
### （1）快乐上网，打开已做好的wokwi硬件仿真网页
https://wokwi.com/projects/465152177007070209
<img width="2556" height="1283" alt="image" src="https://github.com/user-attachments/assets/f23119e0-c5fe-406b-bf94-caebc987ca08" />

### （2）点击wokwi仿真页面的开始按钮，等待虚拟wifi完成连接
<img width="248" height="163" alt="image" src="https://github.com/user-attachments/assets/2e3d566c-e288-4678-9d6c-e54df7d88964" />

### （3）下载已做好的情绪识别软件：

> Windows电脑使用：情绪识别软件/youhappyIhappy-windows.zip

> MacOS电脑使用：情绪识别软件/你开心所以我开心实验软件-macos.zip
### （4）运行情绪识别软件，看到摄像头启动
Windows 运行方法：
* 解压文件夹后，双击运行根目录下的.bat文件；
* 观察是否有弹出安全警告，进行授权（VC++框架安装可能需要验证，无安全隐患）；
* 若弹出的摄像头窗口无画面，检查相机硬件开关或隐私设置；
* 出现摄像头拍摄窗口，且命令行窗口输出实时情绪，即成功。

MacOS运行方法：
* 进入dist/brain_new文件夹，双击brain_new文件（黑色图标）；
* 如果弹出未识别的应用等类似提示，在隐私与安全设置里选择“仍要打开”，输入电脑密码；
* 如果此时运行报错，则打开终端，输入指令 xattr -cr 并加一个空格，然后把解压出来的软件总文件夹直接拖进终端窗口，回车运行；
* 再次双击brain_new文件，授权摄像头权限，关闭终端窗口；
* 再次双击brain_new文件，出现摄像头拍摄窗口，且终端输出实时情绪，即成功。
### （5）对摄像头做出不同表情，观察wokwi仿真页面硬件的变化；
软件支持三种表情识别：快乐（使用嘴角位置判定）、中立、悲伤（为方便测试，使用张嘴程度判定）
### （6）若wokwi页面硬件无变化或响应慢，刷新页面重新运行。

<img width="648" height="448" alt="image" src="https://github.com/user-attachments/assets/748dceea-598b-4ad4-928b-61d2631c4382" />
<img width="2539" height="1374" alt="599233390-47c11d30-c8e2-4fdf-aed9-fc3508c63887" src="https://github.com/user-attachments/assets/cefac8d4-f4b1-42ab-acf4-77617c17551d" />


### 技术栈
MacOS版： Python + Google MediaPipe (AI三维人脸网格) + OpenCV (本地图像渲染) + MQTT (物联网通信)

Windows版: Python + OpenCV Haar (传统特征级联识别人脸/微笑) + MQTT

如需修改源码，请修改brain_new.py文件，Mac需要重新打包运行或直接运行python文件；windows可以依旧使用bat文件运行，不需要打包。

## 第三方资料链接
#### 开源生态相关
[M5Stack官网](https://www.m5stack.com/)
[M5Stack：模块化硬件的艺术](https://www.bilibili.com/video/BV1eNkNBCERF/?spm_id_from=333.1387.favlist.content.click&vd_source=95cb2f19566155bb73393c4156455e36)
[M5Stack 全球创新大赛 2025 获奖作品集锦](https://www.bilibili.com/video/BV1G65961Epk/?spm_id_from=333.1387.favlist.content.click&vd_source=95cb2f19566155bb73393c4156455e36)
[DFRobot官网](https://www.dfrobot.com.cn/)
[DFRobot教程资料大全](https://wiki.dfrobot.com.cn/)
[DFRobot可编程机器人小车](https://www.bilibili.com/video/BV18p411f7Fq/?spm_id_from=333.1387.favlist.content.click&vd_source=95cb2f19566155bb73393c4156455e36)
[DF创客周刊Vol. 111 ](https://www.bilibili.com/video/BV1Qfk9YnET4/?spm_id_from=333.1387.favlist.content.click&vd_source=95cb2f19566155bb73393c4156455e36)

#### 有意思的感知器和执行器相关
[视觉类执行器：TouchDesigner花随脉搏共呼吸](https://www.bilibili.com/video/BV17gQVYNEKj?spm_id_from=333.788.recommend_more_video.-1&trackid=web_related_0.router-related-2479604-9shrk.1780294404371.204&vd_source=95cb2f19566155bb73393c4156455e36)
[气动类执行器：Ecomorphs气动柔性机器人](https://www.bilibili.com/video/BV1Lq4y117fh?spm_id_from=333.788.videopod.sections&vd_source=95cb2f19566155bb73393c4156455e36)
[电机类执行器：机械郁金香](https://www.bilibili.com/video/BV1dK411A7qq?spm_id_from=333.788.recommend_more_video.-1&trackid=web_related_0.router-related-2479604-9xr68.1780295031370.210&vd_source=95cb2f19566155bb73393c4156455e36)
[电机类执行器：71个舵机交互装置](https://www.bilibili.com/video/BV1NT421k74U/?spm_id_from=333.337.search-card.all.click&vd_source=95cb2f19566155bb73393c4156455e36)
[电机类执行器：100个舵机交互装置](https://www.bilibili.com/video/BV1ay411z7CC/?spm_id_from=333.337.search-card.all.click&vd_source=95cb2f19566155bb73393c4156455e36)
[IMU类感知器：手搓云台](https://www.bilibili.com/video/BV16v411v7rb/?spm_id_from=333.337.search-card.all.click&vd_source=95cb2f19566155bb73393c4156455e36)
[哈士奇HuskyLens AI视觉传感器教程](https://www.bilibili.com/video/BV1gZ4y1k7n2/?spm_id_from=333.1387.favlist.content.click&vd_source=95cb2f19566155bb73393c4156455e36)
[记忆合金有意思的应用：基于记忆合金的电控锁](https://www.bilibili.com/video/BV1NdWmz9EUf/?spm_id_from=333.1387.favlist.content.click&vd_source=95cb2f19566155bb73393c4156455e36)
[半导体制冷片有意思的应用：何同学的外卖柜](https://www.bilibili.com/video/BV1fqVh6sEaF/?spm_id_from=333.337.search-card.all.click&vd_source=95cb2f19566155bb73393c4156455e36)


## 课后推荐阅读
《Arduino技术指南》-图灵程序设计丛书（又称动物书） /有电子书，系统性学习Arduino开发必读经典老书
《Making Things Talk》 -Tom Igoe /通俗语言讲解交互技术与案例





