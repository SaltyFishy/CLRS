<h1> Insertion Sort</h1>
<h2>What is Insertation Sort</h2>
Insertation Sort，中文名插入排序，本质上就是对一串数字进行排序。
<h2>How it works</h2>
Insertation Sort的工作过程，实际上就是从第i项（a[i - 1]，i>=1）开始，不断对前i-1项进行排序，最后再将第i项放入其中。<br>
局部过程
<img src="https://github.com/SaltyFishy/CLRS/blob/Sort/insertation_sort%20work1.png" alt="局部过程">
图像表示全局过程
<img src="https://github.com/SaltyFishy/CLRS/blob/Sort/insertation_sort%20work2.jpg" alt="全局过程">
<h2>Code</h2>

```
#include<iostream>
#include<iomanip>
using namespace std;
void insertation_sort(int* a, int len) {
	for (int i = 1; i < len; i++) {                    //insertation_sort的实现主体
		int key = a[i];
		int j = i - 1;
		while (j >= 0 && a[j] > key) {
			a[j + 1] = a[j];
			j--;
		}
		a[j + 1] = key;
	}
	for (int i = 0; i < len; i++) {                   //结果检查
		cout << a[i] << setfill(' ');
	}
}
int main() {
	int a[6] = { 5,2,4,6,1,3 };
	insertation_sort(a, 6);
}
```
<img src="https://github.com/SaltyFishy/CLRS/blob/Sort/insertation_sort_answer.jpg" alt="answer">



