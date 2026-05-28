# 智能设计技术与方法课程 - 智能感知技术与硬件设计课堂资料
#### 龚卿

## 实验1：运行“你开心所以我开心”模拟机器人原型
> 运行条件：有摄像头的windows 或 Mac电脑，且可以快乐上网
### （1）快乐上网，打开已做好的wokwi硬件仿真网页
https://wokwi.com/projects/465152177007070209
<img width="2556" height="1283" alt="image" src="https://github.com/user-attachments/assets/f23119e0-c5fe-406b-bf94-caebc987ca08" />

### （2）点击wokwi仿真页面的开始按钮，等待虚拟wifi完成连接
<img width="248" height="163" alt="image" src="https://github.com/user-attachments/assets/2e3d566c-e288-4678-9d6c-e54df7d88964" />

### （3）下载已做好的情绪识别软件：
https://github.com/oDumbledoreArmyo/Intelligent-Perception-Technology-Hardware-Design/tree/main
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
<img width="2539" height="1374" alt="image" src="https://github.com/user-attachments/assets/47c11d30-c8e2-4fdf-aed9-fc3508c63887" />

### 技术栈
MacOS版： Python + Google MediaPipe (AI三维人脸网格) + OpenCV (本地图像渲染) + MQTT (物联网通信)

Windows版: Python + OpenCV Haar (传统特征级联识别人脸/微笑) + MQTT

如需修改源码，请修改brain_new.py文件，并重新打包运行或直接运行。
