# Tracing MySQL Project

基本上這個專案就是我用來存放我 trace MySQL 原始碼的一些筆記。

- Trace 的方式：[MySQL Internal Manual](http://dev.mysql.com/doc/internals/en)
- Trace 的版本：5.6.21

## Directories

### The Major Directories

以下介紹主要的資料夾內容：

- mysys => MySQL 常用的 functions
- sql => MySQL 上層處理 SQL 指令的部分
- storage => MySQL 下層的各式各樣 Storage Engine
- vio => Virtual IO，MySQL 與網路的對接口
- ... 待補


### The Open-Source Directories

其實並不是所有 code 都是 MySQL 團隊撰寫的，部分是從其他 open source project 挖來的。

- dbug => Fred Fish 的 debug 用 library
- pstack => 顯示 process stack 用的
- regex => 處理 regular expression 用的
- strings => 跟字串處理有關
- zlib => 與 Lempel-Ziv 壓縮相關

## Flow

一個 SQL 指令從使用者送出之後的路程如下：

1. 使用者使用 client 來下達指令 (此部分由 client 處理)

2. 接著指令透過某種方式 (通常是網路)，傳送到了 server。(此部分由 vio 處理)

3. Server 收到指令之後，會解析出指令的意義與內容。(由 sql 處理)

4. 指令解析出的資訊會轉交給 storage engine 來執行。(由 storage 處理)

5. 最後再傳回給使用者。(vio, client)
