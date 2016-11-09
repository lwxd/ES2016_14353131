##Lab4:死锁

 &ensp; 任务：	

 &ensp; 1.运行java文件产生死锁，截图如下：	

![](http://yotuku.cn/link?url=E1oq1E2gG&tk_plan=free&tk_storage=tietuku&tk_vuid=d6e09a87-a4bd-4886-a056-1eb59c23faff&tk_time=2016110923)


 &ensp; 2.产生死锁的几个必要条件：	

&ensp; &ensp; &ensp; <1>资源互斥	

&ensp; &ensp; &ensp; <2>占有且等待	

&ensp; &ensp; &ensp; <3>不可剥夺性	

&ensp; &ensp; &ensp; <4>循环等待

&ensp; 3.对上述程序产生死锁的解释：		

&ensp; 首先class A， class B， 都各自只有一个实例a，b，只能被一个程序调用，形成资源互斥；其次，a.methodA(b)和b.methodB(a)程序都是占有a(或b)资源，等待b(a)资源，形成占有且等待条件；并没有做出“剥夺”的处理，所以不可剥夺；a.methodA(b)和b.methodB(a)程序都是占有自身资源，等待对方资源，所以在某个时刻两者同时运行，形成循环等待的局面，造成死锁。