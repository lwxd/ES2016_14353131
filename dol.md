##Lab3-DOL实例分析&编程   
 &ensp; 任务：  
 &ensp; &ensp;  &ensp;  &ensp;  1.修改example2,让三个square模块变成两个。   
 &ensp; 做法：修改example2.xml中N的值，如下图所示。
![](http://yotuku.cn/link?url=4yGgyV3gG&tk_plan=free&tk_storage=tietuku&tk_vuid=d6e09a87-a4bd-4886-a056-1eb59c23faff&tk_time=2016110923)
	
 &ensp; 结果：	
	
![](http://yotuku.cn/link?url=Nka0CX2eG&tk_plan=free&tk_storage=tietuku&tk_vuid=d6e09a87-a4bd-4886-a056-1eb59c23faff&tk_time=2016110923)	
	

 &ensp; &ensp;  &ensp;  &ensp;  2.修改example1,使其输出3次方数。   
 &ensp; 做法：修改square.c中的代码，如下。
![](http://yotuku.cn/link?url=NkQi073xG&tk_plan=free&tk_storage=tietuku&tk_vuid=d6e09a87-a4bd-4886-a056-1eb59c23faff&tk_time=2016110923)
	
 &ensp; 结果：	
	
![](http://yotuku.cn/link?url=NkM6A72gz&tk_plan=free&tk_storage=tietuku&tk_vuid=d6e09a87-a4bd-4886-a056-1eb59c23faff&tk_time=2016110923)	

 &ensp; 实验感想： 这次的实验比较简单，TA也讲得很详细，问题是，当我修改了代码（无论只改代码，还是把example1或example2中所有代码删除），然后编译、运行，运行结果都不变。后来发现，不知道为什么，在build/bin/main中生成的example1\example2文件都显示是只读文件，无法删除无法更新。最终是每次更改权限手动删除才解决的，不知道该怎么能避免生成的是只读文件。
  
  