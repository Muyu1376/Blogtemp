# FPGA学习笔记1--未使用引脚的状态及程序的固化

## 未使用引脚的状态

在FPGA开发板中，需要对没有使用的引脚状态进行定义，通常会设置为**三态输入**，即选项`As input tri-stated`.

设置方法为`Assigements-->Device-->Device and Pin Options-->Unused Pins`,在打开的界面中选择三态输入的选项。

在这个界面中`As input tri-stated weak pull-up`选项指的是弱上拉输入，意为**所有未被定义的引脚都可以作为输入引脚，并会附加弱上拉电阻**。`As output driving ground`选项是一个危险选项，意为**所有未被使用引脚都会被下拉到地**，当PCB外围电路被上拉到高电位时，引脚会产生强烈的灌电流输入

在定义完未被使用的引脚状态后需要重新编译。

## 程序的固化

由于SRAM的掉电易失特性，当给开发板断电并重新上电之后，需要重新下载程序，因此需要使用片外Flash存储网表。

选择`File-->Convert Programming Files...`

在打开的界面中`Programming file type:`选择输出文件的类型，此处选择`Configuration File(.jic)`.
`Configuration device`选项选择使用的Flash的型号，笔者使用的野火征途开发板，此处选择`EPCS16`。
`File name`选项选择输出位置

在下方的`Input files to convert`框中选择`Flash loader`,然后点击`Add device`，在弹出的对话框中选择使用的FPGA芯片的型号，征途开发板选择`EP4CE10`，点击ok
随后点击`Soft Data`后选择`Add files`按钮选择之前生成的`.sof`文件，之后点击`Generate`按钮生成`.jic`文件

在程序下载界面中选择`.jic`文件进行下载即可。
