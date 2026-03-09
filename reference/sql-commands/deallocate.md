# DEALLOCATE

DEALLOCATE — 釋放（解除配置）預備語句

### 語法

```
DEALLOCATE [ PREPARE ] { name | ALL }
```

### 說明

`DEALLOCATE` 用於釋放先前已準備（prepared）的 SQL 語句。如果你沒有明確釋放預備語句，它會在工作階段結束時自動被釋放。

關於預備語句的更多資訊，請參閱 [PREPARE](https://www.postgresql.org/docs/13/sql-prepare.html)。

### 參數

`PREPARE`

此關鍵字會被忽略。

_`name`_

要釋放的預備語句名稱。

`ALL`

釋放所有預備語句。

### 相容性

SQL 標準包含 `DEALLOCATE` 指令，但它僅供嵌入式 SQL（embedded SQL）使用。

### 另請參閱

[EXECUTE](https://www.postgresql.org/docs/13/sql-execute.html), [PREPARE](https://www.postgresql.org/docs/13/sql-prepare.html)

