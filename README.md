# FBReaderJ4C
本项目是在 FBReader Android Studio移植版的基础上进行的调整（https://github.com/jaychou2012/FBReaderJ-Android-Studio.git）

因为之前的FBReader是用的MakeFile文件配置进编译行生成so动态库的，在C++层进行调试的时候很不方便，所以笔者将其采用比较方便进行调试的Cmake编译方式进行编译

本项目由对C++层的代码进行调整：
    在XHTMLReader.cpp有对图片处理的OnStart方法中注释部分内容，为了适配图片的不换行处理，如果不需要刻意自行取消掉注释。

#注意：
    #在编译的时候需要对于ndk的版本进行声明，暂时只对ndk版本在16和16之前的版本做了兼容，所以再高版本时可能会出现cmake报错的问题。

