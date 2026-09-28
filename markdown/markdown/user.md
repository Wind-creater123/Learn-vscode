# 真正的登录注册

## 代码小解

1. EncryptUtil通过static自动加载配置文件,获取算法
2. 注册时(checkName检查重复名字)检查需传递name,password(加密后存储),role
3. 登录时通过name和password查找对应user,返回token及用户信息
4. getById,通过id查找(intercepter校验token),token中获取role判断是否成功

## 运行

![1](./1.png)
![2](./2.png)
![3](./3.png)
![4](./4.png)
![5](./5.png)
![6](./6.png)