Unlocker 3是针对VMware 11~15的补丁，
==========================================

+----------------------------------------------------------------------------
 重要:                                                                  
 ==========                                                                  
                                                                             
在使用新版VMware之前，请务必卸载旧版Unlocker，否则可能会导致VMware产品不可用！                   
                                                                             
-----------------------------------------------------------------------------

1. 简介
---------------

Unlocker 3专为VMware Workstation 11-15和Player 7-15设计。

如果您使用的是较早版本的产品，请继续使用Unlocker 1。

Unlocker 3已针对以下各项进行了测试：

* Linux 和 Windows 版 Workstation 11/12/14/15
* Linux 和 Windows 版 Workstation Player 7/12/14/15

修补程序代码根据产品执行以下修改
打补丁时：

* 修复VMware虚拟机配置文件和衍生工具以允许macOS引导
* 修复vmware应用程序拓展以允许在虚拟机创建期间选择[Apple macOS X]
* 下载适用于MacOS的最新VMware tools副本

请注意，并非所有产品都能通过安装工具菜单项识别darwin.iso。
例如，您必须在workstation 11和player 7上手动挂载darwin.iso。

破解期间，请务必确保所有VMware服务和后台进程处于停止状态！

此项目使用Python编写

2. 条件
----------------

代码需要Python2.7才能运行。大多数Linux发行版都附带了兼容的Python解释器，应该可以在不需要任何额外软件的情况下工作。


Windows Unlocker有一个使用PyInstaller的Python脚本的打包版本，因此不需要安装Python。

3. 局限性
--------------

如果您在Windows上运行workstation或player，可能会遇到”不可恢复错误“

最新的Linux产品没问题，不会出现此问题。

-----------------------------------------------------------------------------
重要:                                                                  
 ==========                                                                  
                                                                             
如果创建新的VM，VMware可能会停止并创建核心转储。
有两种方法可以解决此问题：
                                                                             
  1.将VM更改为HW 10，这不会影响性能。
  2.编辑VMX文件：
    找到smc.present = "TRUE"
    在其后一行添加smc.version =“ 0”                                                        
-----------------------------------------------------------------------------

4. Windows
----------
在Windows上，您需要以管理员身份运行cmd.exe或使用文件资源管理器右键单击win-install.cmd，然后选择“以管理员身份运行”。

win-install.cmd   - 破解 VMware
win-uninstall.cmd - 取消破解 VMware
win-update-tools.cmd - 检索最新的macOS VMware tools

5. Linux
---------
在Linux上你需要以root用户或sudo命令运行脚本

您可能需要通过对2个文件运行chmod + x来确保Linux脚本具有执行权限。

lnx-install.sh   - 破解 VMware
lnx-uninstall.sh - 取消破解 VMware
lnx-update-tools.sh - 检索最新的macOS VMware tools
   
6. 鸣谢
---------

感谢Zenith432最初构建的C ++解锁程序以及Mac Knife（MSoK）的所有测试和支持。

也感谢Sam B为ESXi 6找到解决方案并帮助我获得调试专业知识。 
Sam还编写了用于修补ESXi ELF文件的代码，并修改了Unlocker 代码以在ESXi 6.5环境中的Python 3上运行。


历史
-------
27/09/18 3.0.0-首次发布
18/02/10 3.0.1-修复了gettools.py与Python 3配合使用并正确下载darwinPre15.iso的问题
18/10/10 3.0.2-修复了带有Windows可执行文件的防病毒软件引起的误报
              -允许Python 2和3从Bash脚本运行Python代码


(c) 2011-2018 Dave Parsons
翻译：@GitHub yjydjk
