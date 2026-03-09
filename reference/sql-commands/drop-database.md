# DROP DATABASE

DROP DATABASE — 移除資料庫

### 語法

```
DROP DATABASE [ IF EXISTS ] name
```

### 說明

`DROP DATABASE` 用於刪除資料庫。它會移除該資料庫的系統目錄（catalog）項目，並刪除包含資料的目錄。此指令只能由資料庫擁有者執行。此外，當你或其他任何人仍連線到目標資料庫時，不能執行此指令。（請先連線到 `postgres` 或其他資料庫再執行此指令。）

`DROP DATABASE` 無法復原，請謹慎使用！

### 參數

`IF EXISTS`

若資料庫不存在則不拋出錯誤；在此情況下會發出一則通知（notice）。

_`name`_

要移除的資料庫名稱。

### 注意事項

`DROP DATABASE` 不能在交易區塊（transaction block）中執行。

當連線到目標資料庫時，無法執行此指令。因此，使用程式 [dropdb](https://www.postgresql.org/docs/10/static/app-dropdb.html) 可能更方便；它是此指令的包裝（wrapper）。

### 相容性

SQL 標準中沒有 `DROP DATABASE` 指令。

### 另請參閱

[CREATE DATABASE](https://www.postgresql.org/docs/10/static/sql-createdatabase.html)

