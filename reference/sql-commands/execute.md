# EXECUTE

EXECUTE — 執行預備語句

### 語法

```
EXECUTE name [ ( parameter [, ...] ) ]
```

### 說明

`EXECUTE` 用於執行先前已準備（prepared）的語句。由於預備語句只在工作階段（session）期間存在，因此該預備語句必須是在目前工作階段中較早之前透過 `PREPARE` 所建立。

如果建立該語句的 `PREPARE` 指定了某些參數，則必須在 `EXECUTE` 中傳入一組相容的參數，否則會回報錯誤。請注意（不同於函式），預備語句不會依參數型別或數量進行多載；預備語句名稱在同一個資料庫工作階段內必須是唯一的。

關於預備語句的建立與使用方式，請參閱 [PREPARE](https://www.postgresql.org/docs/10/static/sql-prepare.html)。

### 參數

_`name`_

要執行的預備語句名稱。

_`parameter`_

預備語句某個參數的實際值。它必須是一個可產生與該參數資料型別相容之值的運算式，而該參數型別是在建立預備語句時決定的。

### 輸出

`EXECUTE` 回傳的命令標籤（command tag）會是該預備語句本身的命令標籤，而不是 `EXECUTE`。

### 範例

範例請見 [PREPARE](https://www.postgresql.org/docs/10/static/sql-prepare.html) 文件中的 [Examples](https://www.postgresql.org/docs/10/static/sql-prepare.html#SQL-PREPARE-EXAMPLES) 小節。

### 相容性

SQL 標準包含 `EXECUTE` 指令，但它僅供嵌入式 SQL（embedded SQL）使用。此處的 `EXECUTE` 指令版本也採用了稍有不同的語法。

### 另請參閱

[DEALLOCATE](https://www.postgresql.org/docs/10/static/sql-deallocate.html), [PREPARE](https://www.postgresql.org/docs/10/static/sql-prepare.html)

