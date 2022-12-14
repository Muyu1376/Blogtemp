## Verilog学习笔记3，奇偶校验

### 奇偶校验的定义

奇偶校验(Parity Check)是一种校验代码传输正确性的方法。根据被传输的一组二进制代码的数位中“1”的个数是奇数或偶数来进行校验。采用奇数的称为奇校验，反之，称为偶校验。


采用何种校验是事先规定好的。通常专门设置一个奇偶校验位，用它使这组代码中“1”的个数为奇数或偶数。若用奇校验，则当接收端收到这组代码时，校验“1”的个数是否为奇数，从而确定传输代码的正确性。



**奇校验：原始码+校验位总共有奇数个1,即原始码中1的数目为偶数，则校验位为1；原始码中1的数目为奇数，则校验位为0。**

**偶校验：原始码+校验位总共有偶数个1。**

### Verilog运算符

#### 位运算符(~,|,^,&,^~)

**双目运算符**：两个操作数

**单目运算符**：一个操作数（通常是多位的数字），运算的结果是1位数

单目运算符在使用时指的是这个多位数中的每一个位相与（相或，异或等）

```verilog
a = &d;		//按位与，检测是否全为1
a = ^d;		//按位异或。奇偶校验，即检测1的个数是奇数还是偶数，奇数个1则为1，偶数个1则为0
a = |d;		//按位或，检测是否全为0
```

注：`~`为按位取反，`！`为逻辑取反

### 题目

现在需要对输入的32位数据进行奇偶校验,根据sel输出校验结果（1输出奇校验，0输出偶校验）

![](https://uploadfiles.nowcoder.com/images/20220315/110_1647318183585/42CD08E9562FE1299E66878122EABE6E)

### 代码

```verilog
`timescale 1ns/1ns
module odd_sel(
input [31:0] bus,
input sel,
output check
);
//*************code***********//
wire temp;//assign语句需要使用wire型变量
    assign temp=^bus;//进行奇偶校验
    assign check=sel?temp:!temp;//如果是sel为1，输出奇校验，0输出偶校验

//*************code***********//
endmodule
```

