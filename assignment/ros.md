##在Ubuntu中安装ROS Jade		
1. 安装


 
 

1.1 配置 Ubuntu 软件仓库

配置你的 Ubuntu 软件仓库(repositories) 以允许 "restricted"、"universe" 和 "multiverse"这三种安装模式。 你可以 按照ubuntu中的配置指南来完成配置。 



1.2 添加 sources.list
 
	$sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

1.3 添加 keys  

	$sudo apt-key adv --keyserver hkp://pool.sks-keyservers.net --recv-key 0xB01FA116

![](http://yotuku.cn/link?url=4JlBfQnef&tk_plan=free&tk_storage=tietuku&tk_vuid=d6e09a87-a4bd-4886-a056-1eb59c23faff&tk_time=2016110922)

1.4 安装

首先，确保你的Debian软件包索引是最新的：   

	$sudo apt-get update
安装ROS：  
桌面完整版安装：（推荐） 包含ROS、rqt、rviz、通用机器人函数库、2D/3D仿真器、导航以及2D/3D感知功能。   

	$sudo apt-get install ros-jade-desktop-full
![](http://yotuku.cn/link?url=E1AQQQ3xG&tk_plan=free&tk_storage=tietuku&tk_vuid=d6e09a87-a4bd-4886-a056-1eb59c23faff&tk_time=2016110922)
要查找可用软件包，请运行：   

	$apt-cache search ros-jade

![](http://yotuku.cn/link?url=E1X57mhxM&tk_plan=free&tk_storage=tietuku&tk_vuid=d6e09a87-a4bd-4886-a056-1eb59c23faff&tk_time=2016110922)
1.5 初始化 rosdep

在开始使用ROS之前你还需要初始化rosdep。rosdep可以方便在你需要编译某些源码的时候为其安装一些系统依赖，同时也是某些ROS核心功能组件所必需用到的工具。   

	$sudo rosdep init
	$rosdep update
![](http://yotuku.cn/link?url=VJ2YV72xG&tk_plan=free&tk_storage=tietuku&tk_vuid=d6e09a87-a4bd-4886-a056-1eb59c23faff&tk_time=2016110922)
![](http://yotuku.cn/link?url=Ekk2VQ2ef&tk_plan=free&tk_storage=tietuku&tk_vuid=d6e09a87-a4bd-4886-a056-1eb59c23faff&tk_time=2016110922)
1.6 环境配置

如果每次打开一个新的终端时ROS环境变量都能够自动配置好（即添加到bash会话中），那将会方便很多：  
 
	echo "source /opt/ros/jade/setup.bash" >> ~/.bashrc
	source ~/.bashrc
如果你安装有多个ROS版本, ~/.bashrc 必须只能 source 你当前使用版本所对应的 setup.bash。 

如果你只想改变当前终端下的环境变量，可以执行以下命令： 
	source /opt/ros/jade/setup.bash
1.7 安装 rosinstall

rosinstall 是ROS中一个独立分开的常用命令行工具，它可以方便让你通过一条命令就可以给某个ROS软件包下载很多源码树。 

要在ubuntu上安装这个工具，请运行： 


	sudo apt-get install python-rosinstall
![](http://yotuku.cn/link?url=4y7_BQ2xz&tk_plan=free&tk_storage=tietuku&tk_vuid=d6e09a87-a4bd-4886-a056-1eb59c23faff&tk_time=2016110922)
2.是否安装成功


 
 

重启后在命令行输入：  

	$roscore

![](http://yotuku.cn/link?url=4J5mL73ef&tk_plan=free&tk_storage=tietuku&tk_vuid=d6e09a87-a4bd-4886-a056-1eb59c23faff&tk_time=2016110922)