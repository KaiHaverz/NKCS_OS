# Lab03_CompileLinux

| **姓名** | **李懋**                       |
| -------- | ------------------------------ |
| **学号** | **2213189**                    |
| **邮箱** | **2213189@mail.nankai.edu.cn** |



## 1 实验题目

- 下载并编译最新的 Linux 内核



## 2 实验目的

1. 下载最新的Linux内核
2. 配置最新的Linux内核
3. 编译最新的Linux内核
4. 用最新的Linux内核驱动Ubuntu



## 3 实验原理

1. 更换当前Ubuntu系统的Linux内核为最新版本
   1. 基本的原理方法就是先准备好需要用的软件包；从官网下载最新的内核（压缩包）并解压缩；
   2. 把解压后的文件夹移动到/usr/src/linux文件夹下；
   3. 进行相应的配置；
   4. 接着进行编译；
   5. 编译成功后即可安装最新的Linux内核；
   6. 安装成功后重启，发现Ubuntu的驱动内核已经是最新版本。



## 4 实验具体步骤

1. 更新

![image-20241110174335859](E:\TyporaPictures\image-20241110174335859.png)

![image-20241110175034187](E:\TyporaPictures\image-20241110175034187.png)

![image-20241110175110241](E:\TyporaPictures\image-20241110175110241.png)

2. 安装相应软件包

![image-20241110175447616](E:\TyporaPictures\image-20241110175447616.png)

3. 查看当前 linux内核版本

![image-20241110175819403](E:\TyporaPictures\image-20241110175819403.png)

4. 下载最新的Linux内核（上次下载好了，在 /home/limao2213189/Downloads 中）

![image-20241110175957636](E:\TyporaPictures\image-20241110175957636.png)

5. 解压内核，并移动到 /usr/src/linux 下

![image-20241110180149849](E:\TyporaPictures\image-20241110180149849.png)

6. 检查剩余空间

![image-20241110182432144](E:\TyporaPictures\image-20241110182432144.png)

7. 配置最新的 Linux 内核

![image-20241110184950627](E:\TyporaPictures\image-20241110184950627.png)



- 命令行输入 make oldconfig，选择N，回车即可

![image-20241110185042565](E:\TyporaPictures\image-20241110185042565.png)

- make gconfig，进入图形化界面



7. 编译内核

```
make -j4
```

![image-20241110224858800](E:\TyporaPictures\image-20241110224858800.png)

- 如上图所示，编译成功

```sh
make
```

- 再执行一遍 make

![image-20241110225235352](E:\TyporaPictures\image-20241110225235352.png)



8. 安装内核

```
sudo make modules_install
sudo make install
```

![image-20241110225812572](E:\TyporaPictures\image-20241110225812572.png)

![image-20241110225840121](E:\TyporaPictures\image-20241110225840121.png)

- Done !



9. 重启查看内核

![image-20241110230012930](E:\TyporaPictures\image-20241110230012930.png)

- 成功！



## 5 实验总结

1. 编译之前的配置非常重要，如果配置出错了编译的步骤很可能出错；如果配置出错但是编译能成功，也有可能导致安装失败。
2. 我尝试了很多次，花了很多时间才配置编译成功，所以还是要耐心，细心