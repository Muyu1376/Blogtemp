 

## Verilog学习笔记5——位拆分与运算

### 题目

现在输入了一个压缩的16位数据，其实际上包含了四个数据\[3:0]\[7:4]\[11:8]\[15:12],

按照sel选择输出四个数据的相加结果,并输出valid_out信号（在不输出时候拉低）

0:  **不输出且只有此时的输入有效** 

1：输出[3:0]+[7:4]

2：输出[3:0]+[11:8]

3：输出[3:0]+[15:12]

![](https://uploadfiles.nowcoder.com/images/20220315/110_1647324367041/4A059B7D0CE23BE806749CB7347973DE)

![](https://uploadfiles.nowcoder.com/images/20220315/110_1647324392924/C99F5E49906B9082CAE3EE6B236EE6D9)

### 题目分析

本题类似于第四题，拆分运算直接使用`[]`表示，题目中当`sel=0`时输入有效意味着需要对输入变量d做寄存，在接下来的选项中利用寄存的d进行运算。代码结构与第四题基本类似。

### 代码

~~~verilog
`timescale 1ns/1ns

module data_cal(
input clk,
input rst,
input [15:0]d,
input [1:0]sel,

output [4:0]out,
output validout
);
//*************code***********//
    reg  [15:0]   temp;
    reg out;
    reg validout;
    always@(posedge clk or negedge rst)begin
        if(!rst)begin
            temp <= 0;
            out <=0;
            validout<=0;
        end
        else begin
            case(sel)
                2'b00:begin
                    validout<=0;
                    temp <=d;
                    out<=0;
                end
                2'b01:begin
                    out <= temp[3:0]+temp[7:4];
                    validout<=1;
                end
                2'b10:begin
                    out <= temp[3:0]+temp[11:8];
                    validout<=1;
                end
                2'b11:begin
                    out <= temp[3:0]+temp[15:12];
                    validout<=1;
                end
            endcase
        end
                           
    end

//*************code***********//
endmodule
~~~

