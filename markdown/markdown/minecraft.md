# Minecraft

## 运行结果

![1](../markdown/1.png)
![2](../markdown/2.png)

## 打包jar

![3](../markdown/3.png)

## 不可在增强for循环内部使用remove

1. ***原因***
增强for循环底层实现使用迭代器遍历
集合内部有一个计数器
迭代器内部也有计数器
使用remove方法后导致集合内部计数器++
而迭代器计数器!=集合计数器
报错

2. 解决

- 使用普通for
- 使用迭代器内部的remove