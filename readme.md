##Description
		
The distributed operation layer (DOL) is a framework that enables the (semi-) automatic mapping of applications onto the multiprocessor SHAPES architecture platform. The DOL consists of basically three parts:

DOL Application Programming Interface: The DOL defines a set of computation and communication routines that enable the programming of distributed, parallel applications for the SHAPES platform. Using these routines, application programmers can write programs without having detailed knowledge about the underlying architecture. In fact, these routines are subject to further refinement in the hardware dependent software (HdS) layer.

DOL Functional Simulation: To provide programmers a possibility to test their applications, a functional simulation framework has been developed. Besides functional verification of applications, this framework is used to obtain performance parameters at the application level.

DOL Mapping Optimization: The goal of the DOL mapping optimization is to compute a set of optimal mappings of an application onto the SHAPES architecture platform. In a first step, XML based specification formats have been defined that allow to describe the application and the architecture at an abstract level. Still, all the information necessary to obtain accurate performance estimates is contained.

##How to install
base on:

1. install VMware ubuntu

2.  `$	sudo apt-get update`

	`$	sudo apt-get install ant`

    `$ sudo apt-get install openjdk-7-jdk`

    `$ sudo apt-get install unzip`

download dol_ethz.zip and systemc-2.3.1.tgz:

 1. `sudo wget http://www.accellera.org/images/downloads/standards/systemc/systemc-2.3.1.tgz`
 `sudo wget http://www.tik.ee.ethz.ch/~shapes/downloads/dol_ethz.zip`
 2. `$	mkdir dol`
 
    `$	unzip dol_ethz.zip -d dol`

	`$	tar -zxvf systemc-2.3.1.tgz`

compiler systemc:

 1. `$	cd systemc-2.3.1`

	`$	mkdir objdir`

	`$	cd objdir`

    `$	../configure CXX=g++ --disable-async-updates`

	result:![](http://i1.piimg.com/567571/8f2f44ba1eb712f4.png)

     `$	sudo make install`
     `$ cd .. '  '$ ls`

	result:![](http://i1.piimg.com/567571/94f2fe2aad0e7af6.png)

	`$	pwd`![](http://i1.piimg.com/567571/f764cae2723aa1b3.png)
	the path is:/home/lwx/Desktop/DOLdownload/systemc-2.3.1

compiler DOL:

 1. change build_zip.xml with which YYY=the path above as follow
 
`<property name="systemc.inc" value="YYY/include"/>`
`<property name="systemc.lib" value="YYY/lib-linux/libsystemc.a"/>`

 2. `$	ant -f build_zip.xml all` with "build successful"
 3. `$	cd build/bin/main``$	ant -f runexample.xml -Dnumber=1`
 	result:![](http://i1.piimg.com/567571/60b736dcf059b26c.png)

##Experimental experience

对于我来说，实验最难在于虚拟机的安装和ubuntu的网络配置，网络配置是使用的虚拟机设置是默认的，但是在windows系统下VMnet1和VMnet8都是未识别的网络，可参考[百度知道解决](http://zhidao.baidu.com/link?url=D8kKnPDyfVfUbp7FlkM6PZdMLkULz692GJN4b6v5VNjnDewzWPUGu1UD5NQRPMKL40B9ZHt2gVa5s7YVuEt0hVtlFTNtEwXik62ISvKgFdq)更改注册表有关设置。除此之外编译的时候遇到“C++ cannot create executable”的问题，可在终端执行`sudo apt-get build-essential`。

