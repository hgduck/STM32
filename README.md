（注：STM32 Cube IDE 在2.0.0版本以前，都集成了 STM32 Cube MX，可以直接在IDE内对芯片进行编辑；但是到了2.0.0版本及以后，STM32 Cube IDE 与 STM32 Cube MX 逐渐被分为了两个独立软件进行开发与维护，删除掉了集成的内容，需要单独下载 STM32 Cube MX。STM32 Cube IDE 与 MX 在下载安装与开发使用时，所有有关文件夹均必须是纯英文路径，否则会安装出错或文件出错。如需获取下载链接，请划至末尾查看）

# STM32 Cube IDE 项目/文件导入流程：  
### 1.导入 STM32 项目（即文件中包含.cproject与.project）：  
下载 STM32 Cube IDE 后，设置 workspace 文件夹（最好设置在熟悉的路径），将该项目复制或者移动到 workspace 文件夹下，随后打开 STM32 Cube IDE，依次点击  
File -> Import -> General -> Existing Project in workspace -> Select root directory[Browse]  
选择你的 workspace 文件夹，选择需要导入的项目，点击 Finish，即导入成功；随后关闭向导界面，即可看到左侧项目栏中的工程，打开 Core（没有添加其他实现文件夹时） 文件夹，可对 Inc 中的头文件或 Src 中的函数实现文件进行编辑。  

### 2.导入文件（.c函数实现文件 或 .h头文件）：  
直接复制或移动到对应的 Src / Inc 文件夹下，即可在 STM32 Cube IDE 进行编辑。  

# STM32 Cube IDE 项目/文件创建流程：  
### 1.创建 STM32 项目（2.0.0版本之后）：  
(1) 在 Cube MX 中创建 NEW Project，  
<img width="400" height="300" alt="first" src="https://github.com/user-attachments/assets/b8211eeb-11cf-47e7-a7e3-a65924df3ef4" />  
(2) 在芯片选择界面搜索STM32F407VET6芯片，并加入收藏（以后常用），随后双击芯片进入项目创建，  
<img width="1026" height="600" alt="second" src="https://github.com/user-attachments/assets/8a931752-7281-4bf5-ad85-8e69a1476613" />  
(3) 在 Project Manager 的 Project 栏目下，输入项目名称、项目地址（workspace）、选择编码工具（STM32 Cube IDE），  
<img width="1026" height="600" alt="third" src="https://github.com/user-attachments/assets/52a40089-db97-4881-a8c9-d6df12d8cfab" />  
(4) 在 Project Manager 的 Code Generator 栏目下，勾选为每个外设生成单独的 .c / .h 文件，  
<img width="1026" height="600" alt="forth" src="https://github.com/user-attachments/assets/94f6c1dd-63ca-4888-af7c-785c43d58bdb" />  
(5) 最后点击 Generate Code 按钮，即可在 workspace 文件夹下创建项目，  
<img width="654" height="312" alt="fifth" src="https://github.com/user-attachments/assets/481d5642-4a5b-484b-8b16-24ed98cd8268" />  
(6) 创建项目完成后，点击 Open Project 按钮，或者直接打开 STM32 Cube IDE，按照导入流程对项目进行导入，即可编辑项目。  

### 2.创建 .c/.h 文件：  
右键要创建文件的文件夹，在 New 目录下点击 File for Template，随后在 File name 栏输入文件名称（不要忘记加 .c/.h），点击Finish，即自动创建成功。创建成功后的 .c 文件包含文件创建信息，.h 文件包含文件创建信息以及头文件定义。  
如果创建文件的文件夹不是 Core 下的 Inc / Src，还需要对文件的编译进行包含：右键项目工程 -> 点击 Properties -> 展开窗口下的 C/C++ General -> 点击 Paths and Symbols。在 Includes 栏目下依次点击 Add -> Workspace，找到你要加入编译的 Inc（.h） 头文件夹，一路OK；在 Source location 栏目下点击 Add Folder，找到你要加入编译的 Source（.c） 函数实现文件夹，OK。随后点击 Apply and Close，即可成功通过编译。

<br>
<br>

### 附：  
STM32 Cube IDE 官网下载地址：https://www.st.com.cn/zh/development-tools/stm32cubeide.html  
STM32 Cube MX 官网下载地址：https://www.st.com.cn/zh/development-tools/stm32cubemx.html  
STM32 Cube IDE 开发基础教程视频【keysking】（非本人）：https://www.bilibili.com/video/BV1AsZGYtEA2/?share_source=copy_web&vd_source=b89b5101d7077c3f4c3ddbe273058ec4  
