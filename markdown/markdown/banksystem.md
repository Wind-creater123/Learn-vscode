# 简单银行系统

```java

import java.util.Scanner;

public class BankSystem {
    public static void main(String[] args) {
        //账户
        long account=0;
        boolean e=true;
        while (e) {
            //打印菜单
            menu();
            //选择
            Scanner sc = new Scanner(System.in);
            int ch = sc.nextInt();
            if(ch<5&&ch>0) {
                switch (ch) {
                    case 1 -> {
                        //存款
                        account = save(account);
                        System.out.println();
                    }
                    case 2 -> {
                        //取款
                        account = get(account);
                    }
                    case 3 -> {
                        //查询余额
                        check(account);
                    }
                    case 4 -> {
                        //退出
                        e = false;
                        System.out.println("谢谢使用");
                    }
                }
            }
            else {
                System.out.println("输入错误");
            }
        }
    }

    private static void check(long account) {
        System.out.println("当前账户余额:"+account);
    }

    private static long get(long account) {
        System.out.print("请输入取款金额:");
        Scanner sc=new Scanner(System.in);
        long g= sc.nextLong();
        if(account>=g){
            account-=g;
            System.out.println("取款成功,账户余额:"+account);
        }
        else if (account<g) {
            System.out.println("余额不足,剩余余额:"+account);
        }
        return account;
    }

    private static long save(long account) {
        System.out.print("请输入存款金额:");
        Scanner sc=new Scanner(System.in);
        long s=sc.nextLong();
        account=s+account;
        System.out.print("当前余额:"+account);
        return account;
    }

    public static void menu() {
        System.out.println("-----欢迎进入银行系统-----");
        System.out.println("--------1.存款----------");
        System.out.println("--------2.取款----------");
        System.out.println("--------3.查询余额-------");
        System.out.println("--------4.退出----------");
    }
}

```

## 代码结果

![系统](../markdown/1.png)
