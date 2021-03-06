![placeholder](https://raw.githubusercontent.com/gameknife/gameknife.github.io/master/images/gkengine_logo.png "logo")
========

| OSX | WIN |
| --- | --- |
|[![Build Status](https://travis-ci.org/gameknife/gkEngine.svg?branch=master)](https://travis-ci.org/gameknife/gkEngine)|![https://ci.appveyor.com/api/projects/status/32r7s2skrgm9ubva?svg=true](https://ci.appveyor.com/api/projects/status/github/gameknife/gkengine?branch=master&svg=true)|

<br>

部署，编译等问题请先在[wiki](https://github.com/gameknife/gkEngine/wiki)和[issue  |   question](https://github.com/gameknife/gkEngine/labels/question)中查阅。

欢迎加入gkENGINE贡献者交流QQ群: [289525937](http://jq.qq.com/?_wv=1027&k=fSv16p)

<br>

gkENGINE's runtime Quick Start
---

1. 你需要安装git, cmake控制台环境, windows安装有visual studio, mac安装有xcode, 拥有良好的github网络访问环境
1. 拉取submodule
```
git submodule update --init
```
3. 构筑基础引擎环境
```
.\auto_make_env.bat (windows) | sh ./auto_make_env.sh (mac)
```
4. 通过cmake，生成你本机的编译环境
```
.\auto_cmake.bat -win64(windows) | sh ./auto_cmake.sh --osx(mac) | sh ./auto_cmake.sh --ios(mac build for ios)
```
5. 工程生成在build-win64/build_osx/build_ios下面

<br>

gkENGINE's editor Quick Start
---

1. 你需要安装nodejs环境, 并已经构建runtime环境
1. 进入引擎的editor目录, 运行npm install 或 cnpm install, 下载nodejs所需环境
1. 运行npm run nconfig, 部署node-gyp，准备构建node api库
1. 运行npm run nbuild, 构建node api库
1. 运行npm start, 启动编辑器

<br>

gkENGINE的技术特性
---

##### 渲染

* 延迟光照 & 延迟着色管线
* 准·基于物理的着色技术
* shader条件编译系统
* 现代后处理技术：HDR, SSAO, DOF, GODRAY, COLORGRADING
* 多线程渲染：渲染提交在单独线程，与其他事务并行
* 多渲染API：支持DX9，GL3，GLES2渲染api并灵活切换
* 多LOD层级地形系统
* TIME OF DAY：全天候环境参数插值
* 内建的实时gpu profiler.

##### 系统

* 跨平台开发：底层基础库通过部分操作系统特例化，实现完全的平台无关开发
* 多种操作系统支持: windows, macosx, ios, android
* TASK和TASK分发系统：可将任何独立事务包装为TASK供分发器进行多线程执行
* PAK文件系统：将文件进行lzma压缩打包，pak系统提供接管文件系统，做到无缝切换
* gameobject系统：将对象抽象为gameobject，组合gameobjectlayer实现灵活的功能组装和扩展
* 强大的profiler，提供对场景渲染量级，帧/步骤耗时，内存占用的精确统计和展示

##### 物理&动画

* 物理模块通过接口抽象，已剥离第三方组件。暂未自主开发实现
* 骨骼动画模块通过接口抽象，已剥离第三方组件，后续提供自写实现
* 内建trackbus动画模块，用于驱动各类gameobject，实现cutscene等功能

##### 工具链

* gmf模型格式：对obj进行二进制优化，拥有绝佳的加载速度及与obj文件互转的能力
* gkMaxPort：插件与脚本结合的3dsmax工具包，可快速整理模型，处理纹理及材质，导出到引擎，直接测试
* 资源编译器：针对多种运行平台，对纹理，材质，模型文件进行特定生成和处理
* 各类辅助的事务处理脚本：方便进行打包，垃圾清理，设备部署，跨平台调试等工作

##### 编辑器

* 已废弃原有MFC实现编辑器，开始使用electron框架研究编辑器实现

gkENGINE截图
---

![placeholder](https://raw.githubusercontent.com/gameknife/gameknife.github.io/master/images/out1.jpg "gkEngine室外截图1")
![placeholder](https://raw.githubusercontent.com/gameknife/gameknife.github.io/master/images/indoor2.jpg "gkEngine室内截图2")
![placeholder](https://raw.githubusercontent.com/gameknife/gameknife.github.io/master/images/indoor3.jpg "gkEngine室内截图3")
