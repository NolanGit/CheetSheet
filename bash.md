# bash

## 别名

- alias gpull='git pull'临时设置别名，unalias gpull删除别名

## 指令

- ctrl+u从游标向前删除指令，ctrl+k从游标向后删除指令；ctrl+a将游标移动到指令的最前面，ctrl+e将游标移动到指令的最后面

## 变量

### 常用命令

- ${var}变量的获取；var=123变量的设定；unset var变量取消设定；read [-pt] variable读取键盘输入，-p接提示信息，-t接n秒内获取不到则退出

- "var=lang is ${LANG}"双引号内的变量仍然保持变量的特性，所以var的值为"lang is zh_CN. UTF-8"；'var=lang is ${LANG}'单引号内的变量不保持变量的特性，所以var的值为"lang is ${LANG}"；

- 使用"\"转义字符来转义空格、$、'、回车；

- "$()"的指令会被首先执行，例如version=$(uname -r)，此时version的值为"5.4.51-v7+"

- export var设置环境变量

- 扩增变量内容var=${var}234，即为var变量后添加234

### 变量类型的声明

- declara [-aixr] variable，-a数组，-i整型，-x将后边的variable变成环境变量，-r将后边的variable设置为只读；注意：数组类型index从1开始

### 变量的删除、取待和替换

## 其他

- history查历史命令

-
