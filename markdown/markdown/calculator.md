# 附加题:计算器

## 计算器

1.循环&(保留两位小数)除法:

``` java

import java.util.Scanner;

public class Practice {
    public static void main(String[] args) {
        Scanner sz=new Scanner(System.in);
        System.out.println("是否开始计算:(true/false):");
        boolean a= sz.nextBoolean();
        while (a) {
            //获取第一个整数
            System.out.println("请输入第一个整数:");
            long num1 = sz.nextLong();
            //获取第二个整数
            System.out.println("请输入第二个整数:");
            long num2 = sz.nextLong();
            //获取运算符
            System.out.println("请输入运算符+ or - or * or /:");
            char c = sz.next().charAt(0);
            switch (c) {
                case '+':
                    System.out.println("结果为:" + (num2 + num1));
                    break;
                case '-':
                    System.out.println("结果为:" + (num1 - num2));
                    break;
                case '*':
                    System.out.println("结果为:" + (num2 * num1));
                    break;
                case '/':
                    if (num2 != 0) {
                        double final1 = (double) num1 / (double) num2;
                        System.out.println("结果为:" + String.format("%.2f", final1));
                        break;
                    }
                    else {
                        System.out.println("分母不能为0!!!");
                        break;
                    }
                default:
                    System.out.println("运算符非法,请重新输入");
                    break;
            }
            System.out.println("是否继续(true/false):");
            a= sz.nextBoolean();
        }
    }
}

```

![计算器](../markdown/1.png)

写在结尾:发现越写越多,在此停下,true和false未转化为yes or no,未提示循环的输入值输入错误(即不填true或false导致错误),且有些小bug,暂且如此.

## 要素展开

1. java计算

```java

public class Practice2 {
    public static void main(String[] args) {
        double a=0.01*100;
        double b=0;
        for(int i = 0; i < 100; i++){
            b+=0.01;
        }
        System.out.println("100*0.01的结果:"+a);
        System.out.println("100个0.01相加的结果:"+b);
    }

}

```

![double](../markdown/3.png)

1. ==输出结果不相同==
2. 原因:100*0.01为1,但100个0.01相加不为1但接近1,<u>计算机转化浮点数为二进制储存并计算时不能精确储存浮点数,只能存储近似</u>
3. 小数结果存储误差.
