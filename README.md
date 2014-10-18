# Tracing MySQL Project

基本上這個專案就是我用來存放我 trace MySQL 原始碼的一些筆記。

- Trace 的方式：[MySQL Internal Manual](http://dev.mysql.com/doc/internals/en)
- Trace 的版本：5.6.21

## Directories

以下介紹主要的資料夾內容：

- mysys => MySQL 常用的 functions
- sql => MySQL 上層處理 SQL 指令的部分
- storage => MySQL 下層的各式各樣 Storage Engine
- vio => Virtual IO，MySQL 與網路的對接口
- ... 待補
