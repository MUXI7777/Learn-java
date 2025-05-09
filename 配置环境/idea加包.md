# 教学网址：https://blog.csdn.net/qq_31696297/article/details/145183440
# 结果


![联想截图_20250509155827](https://github.com/user-attachments/assets/f8f89d06-efbf-488c-a3f0-87ca5aa99bed)

# 内容
近期，本人在学习过程中接触到了JavaFX相关内容。但是，自从 JDK 11 开始，JavaFX 不再包含在大多数 OpenJDK 发行版中。

        下面，简单记录一下安装过程，以及其中可能遇到的问题。

一、下载 JavaFX-SDK
        点击下载链接：`JavaFX - Gluon`https://gluonhq.com/products/javafx/

        首先，根据自己的 JDK 版本，从 Roadmap 一览的表格中找到适合于自己 JDK 版本的 JavaFX 版本。例如：我使用的是 JDK20 ，就选择 JavaFX 21.0.5 版本。

![c792a9405f594fc790c796799a035d88](https://github.com/user-attachments/assets/21cbae2d-8ee7-4be1-ace0-fa8936082963)
        根据表格选择的 JavaFX 版本，这里以 21.0.5 版本为例，在 Downloads 页面按自己系统环境进行选择，选择完成后点击 Download 绿色按钮下载 JavaFX-JDK 包。下载完成后解压至任意目录。

![fa174648e10a4dd982a7c300d82e7daa](https://github.com/user-attachments/assets/e6d2ff1a-bf8f-4c0e-91ab-6662d05a839b)


二、IDEA中添加依赖包
2.1 打开项目结构（Project Structure）菜单

![e7ebc4b23c3e48198552c738ac8ff4f9](https://github.com/user-attachments/assets/ef0bf46e-0b6c-43f4-b91c-1b78313304f7)

2.2 添加库文件
        在 Project Settings 中选择 Libraries ，点击中间一栏的加号，添加新的库，并选择刚刚 JavaFX 的解压目录下的lib目录下的全部jar文件，添加入项目。
![ad266f3b680742189ea3ffc021516aa2](https://github.com/user-attachments/assets/a8aa8263-3fd8-47ee-8127-551d062737cd)



        添加完成后，JavaFX的代码便可以在 IDEA 中正常解析语法了。

2.3 添加虚拟机选项（VM Options）
        点击 IDEA 右上角的三点， 选择 Run with Parameters，或者直接修改当前配置。

![834b4bada3b9496b8892a0b41eb952ca](https://github.com/user-attachments/assets/34c34854-97e7-4772-82fc-d08c5a8a8a2d)


        在弹出的菜单中点击 Modify options，并选择添加虚拟机选项（Add VM Options）。


![9a500d6d0a1048f08c8bc9ab141d18f4](https://github.com/user-attachments/assets/ca1405c5-d89d-4941-a6cb-bb83013b6b70)


![0cc8a0d0e36740d4b1ea90f1e2036478](https://github.com/user-attachments/assets/2d360ba7-64f4-4312-98dc-7e00c6bd7a00)

![1906834b87af415b94eeb34b77573865](https://github.com/user-attachments/assets/25ceb231-3397-4639-8a81-c75ebd09b9dd)


        在 VM options 输入如下虚拟机参数：
```java
--module-path "E:\javafx-sdk-21.0.5\lib" --add-modules javafx.controls,javafx.fxml
```
 务必要根据自己的 JavaFX 目录，手动修改上述路径。
![dad09deda9e7461180dda5b0708483b9](https://github.com/user-attachments/assets/8d7864b3-1182-4b7e-99f2-1f0ccfe438ae)



        输入完成，点击运行（Run）或应用（Apply）保存配置，再次运行即可执行 JavaFX 代码。
————————————————

                            版权声明：本文为博主原创文章，遵循 CC 4.0 BY-SA 版权协议，转载请附上原文出处链接和本声明。
                        
原文链接：https://blog.csdn.net/qq_31696297/article/details/145183440
