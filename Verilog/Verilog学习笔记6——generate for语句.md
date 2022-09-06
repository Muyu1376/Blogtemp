# Verilog学习笔记6——generate for语句

##  for循环

for循环只能在always 语句块内使用，本质上来说，for循环在verilog中是并行执行的，不像是在c语言中顺序执行

语法与c语言中for相同

## generate for

generate for 的作用和for 语句是一样的，但是语法规则上有所不同

generate for使用规则如下
~~~verilog
genvar i;//循环变量必须用genvar定义
generate for(i=0;i<1;i++)
	begin

	end
endgenerate


~~~
