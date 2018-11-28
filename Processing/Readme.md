# **Processing** 
1.  rect()画方 （x,y,a,b）xy是初始坐标 ab是宽和高 还可以加r是四个角倒圆角的半径 还可以加左上 右上 右下 左下四个圆角半径 
2. 从左上角往右是x正向 往下是y正向
3. size（）窗口尺寸
4. ellips（）（x,y,a,b）xy是圆心坐标 ab是宽高 ab相等是正圆不等是椭圆 
5. 结束以"；"分号收尾

### 自写函数 定义函数，函数调用
1. 有自写函数其他要放在steup 或 draw 外面 

```java
float a,b; /*1.ab是全局变量，放在最外，声明变量，注意作用域的问题*/
void setup(){
  size(600,600);//2.有自写函数，size必须放在setup中
  a = width/4;//3.再赋值，如果放在外面，会用默认的100
  b = 0.2*a;  
  jiu(0,0);
  jiu(0,1);
  jiu(1,0);
  jiu(1,1);

}

void jiu(int x, int y){
  rect(x * a,y * a,a,a);
  ellipse(c(x),c(y),r(1),r(1));
  ellipse(c(x),c(y),r(2),r(2));
  ellipse(c(x),c(y),r(3),r(3));
}
float c(int n){
 return n * a + a / 2;//4.只有一行的函数可以直接return
}
float r(float n){
  return a-n*b;
}  
```

  ### 流程控制
  1. 循环就重复某事情

### for
### 语法是for(初始化值；条件；自增）｛一些操作｝

自增
draw是个循环
这个t
就是循环内自增，每一次执行到t++
他就加一
t++相当于t = t + 1

然后条件就是终止循环跳出循环的条件 (应该是继续下去的条件不满足就会跳出循环）

初始化值是说从几开始算

下面我来写一个循环

这个打印出来0到99
因为我是从0开始算

但是我从1开始最后也没有输出100是因为我的条件是小于而不是小于等

然后这个就输出了1到100的等差数列

还有自增可以不是增1也可以是别的

写作
i += 某个数

比如i += 10；

这样就画出来一串

循环可以重叠也就是说for循环里还可以加for循环，就有点像树型数据了

```java
void setup(){
  size(600,600);
  dang(6,7,20);
}
void dang(int x, int y, int d){//xyd分别是行数列数和距四边边距
float rectW = width / x- 2 * d / x; //计算x方向的格子宽
float rectH = height / y-2 * d / y;//计算y方向的格子高
  for(int i = d; i <=  width - d; i += rectW){
    for(int j = d; j <=  height - d; j += rectH){
    rect(i,j,rectW,rectH);
  }
 }
}
```