# 第一讲     
## 整数的乘法运算   
* 通常，高级语言中的两个n位整数相乘的结果也是n位整数，即结果只取2n位结果中的低n位     
> 例如在C语言中，参加相乘的两个操作数类型必须一致，如果不一致，需要转换为一致的类型后再运算     

* 在计算机内部，一定有x^2>=0 吗    
> - 若x是带符号整数，则不一定    
> - 若x是浮点数，则一定    
* 什么情况下，乘积是正确的呢  (x * y = z) 
> - 对于有符号整数，如果高n位是全0或者全1，并且与低n位的最高位相等，则正确，否则不正确     
> - 对于无符号整数，如果高n位是全0，则正确，否则不正确    
> 在高级语言中判断 ： !x||(z/x == y)为真    

* 硬件不判定是否溢出，仅保留2n位乘积，供软件使用    
> 如果程序不采用防止溢出的处理，且编译器也不生成用于溢出处理的代码，就会发生由于整数溢出而产生的错误      

* 乘法指令   
> - 无符号乘法指令   
> - 有符号乘法指令   
> 因为两种指令对于相同的两个操作数，乘积的低n位相同，但是高n位不同      

* 乘法指令不生成溢出标志，编译器根据2n位的乘积进行溢出判断    

## 变量与常数之间的乘法运算   
> * 整数乘法运算比整数加减法，移位运算所需的时间多，通常一次乘法操作需要多个时钟周期，而加法和移位操作只需要1个或少于1个时钟
周期，因此编译器在处理变量与常数之间的乘积运算时，通常以移位，加法和减法来代替乘法运算        
> > 比如x * 20 (20 = 16 + 4)可以用 (x << 4) + (x << 2) 来代替,这样一个乘法运算转化位两次移位和一次加法     
> * 不管是无符号整数还是有符号整数，如果相乘发生溢出，则采用移位和加法操作也发生溢出    

	
     



     



