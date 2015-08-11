# CodeUtils

代码工具,编译时(BufferKnife等框架属于运行时)工具
原理是根据功能需要生成代码文本,然后利用FileIO流写入到文件中

最终生成的代码和手写基本一模一样,因此基本上无任何学习成本

注意:
由于是通过文件流的方式直接修改,所以eclipse等编译工具无法进行撤回操作
切记一定要配合github或者svn等代码管理工具一起使用


# 已有核心功能包括

AndroidUtils:

1.自动遍历layout布局文件,生成findViewById的代码

2.自动根据item的布局生成一个最基础的BaseAdapter适配器类

3.提供2个颜色和圆角半径,自动生成圆角矩形的两个shape形状,并生成对应的selector

4.自动遍历文件中#RGB颜色,或DP/SP的大小,将其抽取到dimens.xml和colors.xml文件中


FileUtils:

1.遍历路径下全部文件

2.自动删除项目中无用文件(没有任何一个文件用使用过该文件)

3.获取项目代码行数(统计全部.xml和.java文件)


其他:

1.自动根据服务器返回的json字符串生成对应的类文件

等等...



# 使用方法

以最常用的两个功能为例

自动遍历layout布局文件,生成findViewById的代码
步骤:
1.布局文件xml部分自己手动编码
2.新建一个Activity的.java文件
3.分别右键两个文件->properties,然后复制Location文件地址
4.在代码工具的Main类的main方法中,使用方法AndroidUtils.autoFindViewById
5.参数分别传入之前复制的布局文件地址和Activity类文件地址,最后一个参数为是否解析布局里include标签中包含的控件内容
6.run运行代码工具类(run as Java Application)

然后打开Activity文件刷新一下就可以看到自动生成的代码了