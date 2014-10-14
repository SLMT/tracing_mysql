# MyISAM Storage Engine

## Introduction

MyISAM 是 MySQL 下層的其中一種 Storage Engine。

## Files

`mi_*` 開頭的檔案就是 MyISAM 相關的重要檔案，`mi` 代表的就是 MyISAM。

MyISAM 大概可以分成三個 module ，分別是 File System，Record Row 與 Index Key 這三部分。

### File System 相關檔案

- `mi_open.c` 開啟檔案
- `mi_close.c` 關閉檔案
- `mi_rename.c` 重新命名檔案
- ...

### Record Row 相關檔案

- `mi_write.c` Insert Row
- `mi_update.c` Update Row
- `mi_delete.c` Delete Row
- `mi_delete_all.c` Delete All Row
- ...

### Index Key 相關檔案

- `mi_rkey.c` Random Key 搜尋
- `mi_rnext.c` Next-Key 搜尋
- `mi_key.c` 與 Key 管理相關
- ...
