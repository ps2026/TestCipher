# TestCipher
简单的文件加密解密程序，主要用于解释文件加解密的原理流程；

##文件加解密的流程及原理
1、加密方法：存储文件时，从输入流中截取文件的字节数组，对字节数组进行加密，至于加密的方式和算法就可以视需求而定了，然后把加密后的字节数组写入到文件中，最后生成加密后的文件；

2、解密方法：同加密方法一样，只不过是对字节数据进行解密，最后生成明文文件；

3、加密算法：android系统本身引入了javax包的Cipher类，这个类里提供了各种各样的通用的加密方式，如AES对称加密等；该程序中有个CipherUtil工具类，里面有一些简单的使用Cipher进行AES加解密的方法；当然最好还是好好学习一下Cipher类的使用；

4、注意事项：
		
			a、如何判断一个文件是加密后的文件，最简单的方法就是对加密后的文件统一增加一个后缀名，
			然后在解密之后将这个后缀名去除，还原回原有文件格式；
			
			如：密文文件的统一后缀名为“.cipher”，明文文件名为"测试.txt"，加密后的密文文件应该为“测试.txt.cipher”;
			
			b、加密文件时还有一个重要的注意事项，就是加密后的密文和明文的长度是否相同，
			如果文件时一次读取出所有字节数组进行加密的话不用担心这个问题，
			但是当对文件分次读取加密或分段加密的话，就不得不考虑这个问题了，最方便的方法就是保证明文和加密后的密文长度相同；
			如果长度不同，由于是分段加密的，密文是由一段一段子密文拼接成的，解密时会找不到每段子密文，因为不知道每段子密文的长度是多少；

##截图
![image1](https://github.com/ZhangSir/TestCipher/blob/master/Screenshot_2016-07-08-14-24-43.jpeg)
