# Matlab
study resources
 
  function [输出变量] = 函数名(输入变量)
 
1、画图有plot和cftool两种，前者简单图，后者可得各种参数；
   cftool ： R-square参数  R^2值，越趋近1越好，通常要求>0.95 
   x=1:100
   plot(x,'x.^2+3*x+9','k.')
   axis([xmin],[xmax],[ymin],[ymax]);% inf无穷
   加入格线set(gca,'ytick',[2,3,4,5,6   or '例子1','fa']);
   subplot(m,n,p)
   希腊字母如 pi  写法是 \pi
2、矩阵构建
   （1）、excel导入
   （2）、直接法： d=[1, 2, 3, 4; 1, 5, 2, 5]

                   d =

                       1     2     3     4
                       1     5     2     5

3、插值-->>  课程中心
   使曲线圆滑，spline函数
   x=[1,,3,5,6,9];
   y=[11,13,16,20,82]
   x1=0:0.1:9;
   y1=spline(x,y,x1);
   plot(x1,y1)

4、积分 
   求f(x)的在（a到b）的定积分
   *****命令开始*****
   syms x
   int(  f(x)  , a, b  )
   *****命令结束******
   命令中的f(x)自己指定
   a为积分下限，b为积分上限。

5、拉格朗日乘数法 优化
   http://www.ilovematlab.cn/thread-44166-1-1.html

6、双对数坐标
   loglog(x,y)

7、整数规划   intlinprog(f,incon,A,b,Aeq,beq,lb,ub)
   f：目标函数的系数向量
   incon：正数决策变量的号数
   A，b：不等式规划    形式：A*x <= b
.  Aeq,beq : 等式规划   形式：Aeq*x = beq
   lb,ub :规划上下限

8、线性规划   linprog(f,A,b,Aeq,beq,lb,ub)
   用法同整数规划

9、取整函数
   floor(x):不超过x 的最大整数

10、绘制柱状图
   hist(x,n)   %n直方的个数
   bar   bar(x,y) ex:bar(a(:,1),a(:,2))
   rose(x)  极坐标上的直方图

11、假设检验
   t检验 ttest
   z检验 ztest
   卡方检验 vartest

12、自定义方程拟合
   fittype('x + a*exp(b*y)','independent',{'x','y'},'denpendent','z')

13、神经网络工具箱
   nnstart

14、定义函数变量
   syms x y                 %方法一（直接定义）
   fun1=x^2+2*y+1
   subs(fun1,{x,y},{1,2})   %求函数值
   
   fun2=inline('x^2+2*y+1')  %方法二 (内联函数)
   fun2(1,1)
 
   fun3=@(x,y)x^2+2*x+1     %方法三（匿名函数）
   fun3(1,1)

15、定义抽象函数
   z=sym('f(x,y)')
   z=inline('f(x,y)')   %未来版本将删除
   z=@(x,y)f(x,y)       %推荐使用

16、输出函数
   disp(x)   %类似于c的printf("hello world");

17、弧度与角度
   sin cos tan 是以弧度为单位
   sind cosd tand 以角度为单位

18、repmat扩充矩阵
   a=(1:3);
   b=repmat(a,1,4)

19、等比，等差数列
   linspace(0,1,5)   %(起始值，终止值，个数)
   logspace(0,4,5)

20、求导
   diff(f(x),x，n)            % n是阶数%不可求inline内联函数


