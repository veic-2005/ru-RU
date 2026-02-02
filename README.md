# Two-dimensional array"
先执行"import_open_ru.md"操作，然后再执行下列操作。

- VS2022

### import vocab_ru
```
CREATE TABLE `vocab_ru` (
  `azString` varchar(256) NOT NULL,
  `word` varchar(64) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

ALTER TABLE `vocab_ru`
    ADD PRIMARY KEY (`azString`);
```
把处理完的csv格式导入到vocab_ru中。

### [App](https://github.com/veic-2005/export-vocab)
点击 "Two-dimensional array"，复制VS中output的内容到enu2ru.h中:
```
QString openrussian[5229][3] = {
        // Copy the 2D array here
    };
```
#### One last thing
在导出的文件中找到“has exited with code 0 (0x0).”行，并删除它。

### 关于 hashtable size
数据表(vocab_ru)的count值:
```
当前值为：5229
```

## Ref
- [Demo（MySQL Connector/Net 的简单使用）程序](https://tdtc-hrb.github.io/cnblogs/post/mysql.net)
