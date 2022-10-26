

`CMakeLists.txt`相当于C++中的源文件，里面是需要执行的指令

如何执行该文件：
```

cmake -G "MinGW Makefiles" ..
make
.\hello_cmake.exe
```
cmake -G 指定生成的项目类型，这里使用MinGW编译，所以生成MinGW项目。最后指定CMakeLists.txt文件所在目录，这个目录就是${CMAKE_CURRENT_SOURCE_DIR}，而执行cmake的目录就是${CMAKE_BINARY_DIR}也就是生成项目的目录


变量、函数：
```
set(USER_NAME xxx)
${USER_NAME}
```
使用set定义变量，函数的参数用空格隔开