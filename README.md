# 说明

**为原版RTKLIB添加CMakeLists.txt管理**

在原项目的根目录下、src文件夹下、app/consapp下各添加一个CMakeLists.txt

文件夹结构如下：
```bash
# src文件夹结构如下
src
├── build
├── rcv
├── CMakeLists.txt
├── rtklib.h
├── convgpx.c
├── convkml.c
├── convrnx.c
├── postpos.c
├── ...


# app/consapp文件夹结构如下
app/consapp
├── clean_consapp.bat
├── CMakeLists.txt
├── convbin
├── install_consapp.bat
├── makefile
├── pos2kml
├── rnx2rtkp
├── rtklib_consapp.groupproj
├── rtklib_consapp.groupproj.local
├── rtkrcv
└── str2str
```
编译的命令如下：
```bash
mkdir build
cd build
cmake ..
make

# 如果要加快编译速度，使用命令
make -j8
```
编译完成后会
* 在 `bin` 目录下生成 `consapp` 的二进制可执行文件
* 在 `lib_rtk` 文件夹下生成源码编译好的静态库 `rtklib.a` 文件