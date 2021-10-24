# 什么是JDK，JRE

``` //一个源文件中最多只能有一个 public 类。 其它类的个数不限。 [演示]
//Dog 是一个类
//编译后， 每一个类， 都对于一个.class
class Dog {
    
//一个源文件中最多只能有一个 public 类。 其它类的个数不限， 也可以将 main 方法写在非 public 类中，
//然后指定运行非 public 类， 这样入口方法就是非 public 的 main 方法
    public static void main(String[] args) {
    	System.out.println("hello, 小狗狗~");
    }
} 

class Tiger { 
    public static void main(String[] args) {
		System.out.println("hello, 小老虎~");
}
}
```