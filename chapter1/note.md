- switch
```c++
switch(num){
    case 1:
        do something;
        break;
    case 2: 
        do sth;
        break;
    default:
        do sth;
        break;
}

switch(character){
    case 'a': case 'A':
    case 'e': case 'E':
    .....
    case 'u': case 'U':
    ++vowel_cnt;
    break;
}
```

- array数组初始化
```c++
//1.先声明大小，以后再赋值
int arr[18];

//2. 声明大小，并赋值
int arr[3] = {1,2,3};

//3. 不声明大小，系统计算大小
int arr[] = {1,2,3};
```

- vector容器初始化
```c++
//1. 先声明大小，以后赋值
vector<int> seq(18);

//2. 直接赋值
vector<int> seq = {1,2,3};

//3. 利用array来进行赋值
vector<int> seq(arr, arr+3);

//4. 使用vector来赋值，也就是复制一个
vector<int> seq2(seq1);
```

- 对于vector容器的指针
```c++
//指针
vector<int> * p = &fibonacci;

//指针数组
vector<int> * pointer_arr[] = {
    &fibonacci,
    &fibonacci2,
    &fibonacci3
}

//指针的vector容器
vector<vector<int> *> pointer_vector(pointer_arr, pointer_arr+3);

//指针的几个相关运算符
* & -> .
```

- 随机
```c++
srand(int_num) //选择seed
int k = rand() //范围 ： 0~INT_MAX
k = k % 10 //范围 : 0~9
```

- 输出
```c++
cout //需要经过缓冲区，endl会添加一个换行符，并且清空缓冲区
cerr //不需要经过缓冲区
```
- File
```c++
//头文件
#include<fstream>

//输出
ofstream outfile("./dir/temp.txt"); //有就使用，没有就创建

//注意到这里使用了斜杠（/），斜杠作用：表路径，反斜杠（\）作用：表特殊符号\n

ofstream outfile("temp.txt", ios_base::app); //在尾部添加

ofstream << "hello world"<<  endl;

//输入
ifstream infile("temp.txt"); //如果没有，那么infile == false == 0
//如果有，那么infile在开头

infile >> a; //每次运行这个句子，读到空格或者换行为止
//读到末尾了，infile就变为false

infile.seekg(0); //又从头开始

//输入兼输出
fstream file("temp.txt", ios_base::in | ios_base::app);
//书上这么写，而且句柄定义在文件末尾，要用seekg(0)，读会遵照句柄，写会添加在末尾

//我这么写
fstream file("temp.txt", ios_base::in | ios_base::out | ios_base::app);
```

- 对于命名空间的理解
    - 命名空间是设计用来解决命名冲突的问题
    - 每个标准头文件包含了一部分std，std还可以扩充（自定义扩充），所有的部分std组成了整体std
- namespace的写法
```c++
namespace std{
    int num = 5;
}
```