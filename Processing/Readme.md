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
  size(600,600);//2.小坑，有自写函数，size必须放在setup中
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