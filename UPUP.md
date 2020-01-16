
## 1
//统计输入中每个值出现了多少次
```cpp
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
因为之前结束输入的结束符是ctrl+z,结束符的值为0,所以此时val存储的是0。要用currval，这样输入结束符给val是对currval没什么影响的。 
