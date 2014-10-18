# SQL

## Files

### Parser 相關

- `sql_lex.cc` Lexer
- `sql_yacc.yy` Parser
- ...

這部分的程式碼會負責解析 SQL 指令，並從中把所有需要的資訊萃取出來。


### Handler 相關

- `ha_*` 皆為 handler 檔案

handler 主要在決定要把這些解析出來的資訊交給哪一個 storage engine 來處理。

注意：[Internal Manual 上的資訊](http://dev.mysql.com/doc/internals/en/guided-tour-majordir-sql.html) 與 5.6.21 版的程式碼有點不太一樣。


### Statement 相關

- `sql_delete.cc` SQL 的 `delete ...` 指令
- `sql_do.cc` SQL 的 `do ...` 指令
- `sql_help.cc` SQL 的 `help ...` 指令
- `sql_insert.cc` SQL 的 `insert ...` 指令
- `sql_select.cc` SQL 的 `select ...` 指令
- `sql_show.cc` SQL 的 `show ...` 指令
- `sql_update.cc` SQL 的 `update ...` 指令
- ...

這些檔案主要是在處理 SQL 內各式各樣的 statements，檔案開頭跟 parser 都一樣都是 `sql_*`。


### Statement 的 functions

- `sql_string.cc` 字串
- `sql_olap.cc` rollup
- `sql_udf.cc` 使用者自訂的 functions (User-defined functions)
- `sql_union.cc` unions

這邊主要在存放一些給 statements 用的 functions。
