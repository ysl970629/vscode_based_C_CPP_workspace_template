# 基于VSCode的C/C++单文件与多文件编译执行调试环境的搭建

所有内容都是我借鉴博客或者文章，加上自己的一点点修改做的，经过很多次测试，并且把每个仓库的功能和无法实现的部分，以及配置和使用方法全部在相应的`README`中做出了说明。

我已经配置好了绝大部分内容，只需要你安装一下需要的环境即可，基本上算是开箱即用了。

多文件编译对我来说实在有点难，所以无法在`cmake_clang_clang++`仓库里调试单个文件。如果你知道怎么弄，请issue或pull request。或者对于不完善的部分（比如只能在`include`文件夹里放自己的头文件）

本仓库提供了三种配置方案，这三种方案互相冲突，请根据需要选择一种使用：

| 文件夹                | 说明                                                         | 使用方法                              |
| --------------------- | ------------------------------------------------------------ | ------------------------------------- |
| `gcc_g++`             | 以`gcc/g++`作为编译器的工作区模板                            | [README](./doc/README-gcc.md)         |
| `clang_clang++`       | 以`clang/clang++`作为编译器的工作区模板                      | [README](./doc/README-clang.md)       |
| `cmake_clang_clang++` | 以`clang/clang++`作为编译器，通过CMake同时构建多个文件的工作区模板 | [README](./doc/README-clang-cmake.md) |
| `global`              | 我的全局配置文件，与VSCode的界面设置相关，这个不是必须要用的 | [README](./doc/README-global.md)      |

三种方案的优劣点：

| 文件夹                | 可以做到                                          | 无法做到                   |
| --------------------- | ------------------------------------------------- | -------------------------- |
| `gcc_g++`             | 文件单个编译运行调试，控制台支持中文              |                            |
| `clang_clang++`       | 文件单个编译运行调试，代码提示和性能比gcc/g++友好 | 控制台中文乱码，这个无解   |
| `cmake_clang_clang++` | 多文件工程同时编译调试和运行，单文件编译和运行    | 单文件调试，控制台中文乱码 |

这个仓库对于想要用VSCode写C/C++的新手朋友们（比如我）来说，是够用的，当你学会怎么搞之后，你都可以自己写配置文件了，肯定就不需要这个仓库了。总之，祝编程愉快