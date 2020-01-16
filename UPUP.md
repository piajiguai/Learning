
## 1 
 
```cpp
//统计输入中每个值出现了多少次
#include<iostream>

int main()
{
	int currval = 0, val = 0;
	if (std::cin >> currval) {
		int cnt = 1;
		while (std::cin >> val) {
			if (val == currval)
				cnt += 1;
			else {
				std::cout << currval << " ocurrs " << cnt << " times " << std::endl;
				currval = val;
				cnt = 1;
			}
		}
		std::cout << currval << " ocurrs " << cnt << " times " << std::endl;  //*
	}
	return 0;
}
```

*号处输出不可用val  
因为之前结束输入的结束符是ctrl+z,结束符的值为0,所以此时val存储的是0。要用currval，这样输入结束符给val是对currval没什么影响。 

## 2  
### (关于git的基础操作)  
 
有工作区、暂存区(索引)、本地版本库  
  
git init   初始化一个空的git仓库。会创建一个.git文件，千万不能动它！ 
git status   查看状态 显示各个区域的文件状态(比如工作区的代码是否add进暂存区) 
git add <文件名>   将工作中的此文件放入暂存区 
git commit -m "一段牛逼的代码"   将add进暂存区的文件提交到版本库。要求注释。  
 
要提交了但还不知道你是谁呢，那么设置一下  
git config --global user.name "..."  
git config --global user.email "..."  
 
还能查看我们的commit history  
git log   按q可以退出此界面  

### 关于cat命令  
cat <文件名>   cat(concatenate and print files).可以查看一个文件中的内容。  
cat file1.txt file2.txt file3.txt   将多个文件的内容拼接在一起，并打印出来，如下： 
```
cat file1.txt file2.txt file3.txt
This is file1.txt
This is file2.txt
This is file3.txt
```

### 分区切换 
 
当将工作区的文件add进暂存区，然后又修改了工作区中的文件内容时  
又想丢弃掉工作区中的修改内容，回到暂存的代码 
git checkout -- <文件名> 
 
如果暂存区内容也不想要，想回到最近一次提交给版本库的内容 
git reset HEAD <文件名> 
注意这只是版本库与暂存区的交互，工作区还是未改变，想再改变工作区，那么 
git checkout -- <文件名> 

### 总结  
工作区            暂存区          本地版本库 
         ➡add           ➡commit 
       checkout⬅         reset⬅ 
要是忘了随时 git status ！ 
 











