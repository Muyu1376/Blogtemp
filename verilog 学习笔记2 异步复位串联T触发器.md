## verilog 学习笔记2 异步复位串联T触发器

### 题目

题目描述：用verilog实现两个串联的异步复位的T触发器的逻辑，时序图如下

![](http://tva1.sinaimg.cn/large/0067yegSly1h4a9w2zampj317407s421.jpg)



### 题目分析

#### T触发器

输入为1，输出取反

输入为0，输出保持



#### 异步复位

异步复位指的是不根据时钟信号进行复位，即当复位按键按下时，不论时钟信号处在上升沿或下降沿，都进行复位。通常代码形式如下

~~~verilog
always@(posedge clk or negedge rst)
~~~

与异步复位相对的是**同步复位**，同步复位需要考虑时钟是否触发。  

当时钟未曾触发的时候，即使出现复位信号，也不会进行复位操作。通常代码形式如下

~~~verilog
always@(posedge clk)
    begin
        if(!rst)begin
        
        end        
    end

~~~

可以发现异步复位是当检测到`clk`信号时，执行`always`语句块内的操作



回到题目分析，由于是两个串联的T触发器，因此需要定义一个reg型变量`temp`。

同时根据时序图，复位为低电平复位。有关复位的具体问题可以详细阅读一位大神的文章

<https://blog.csdn.net/DengFengLai123/article/details/113749534>



### 代码

~~~verilog
`timescale 1ns/1ns
module Tff_2(
	input	wire	data,clk,rst,
    output	reg		q 
);
reg temp;
    always@(posedge clk or negedge rst)begin
        if(!rst)begin
            q<=0;
            temp<=0;
        end
        else begin
            if(data==0)begin
                temp<=temp;
            end
            else begin
                temp<=!temp;
            end
            if(temp==0)begin
                q<=q;
            end
            else
                q<=!q;
        end
    end
endmodule
~~~

