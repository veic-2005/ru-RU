---
title: "导入word"
description: "openrussian"
date: 2026-02-02T08:08:08+08:00
---
- VS2022

# [Dictionary](https://en.openrussian.org/dictionary)
进入 [TogetherDB online database](https://app.togetherdb.com/db/fwoedz5fvtwvq03v/openrussian_public/words)
过滤条件:
```
level!=null
```
点击“words” export table.

## db table
- words2
```
CREATE TABLE `words2` (
  `id` int(11) NOT NULL,
  `position` varchar(11) DEFAULT NULL,
  `bare` varchar(64) NOT NULL,
  `key101` varchar(256) DEFAULT '',
  `accented` varchar(64) DEFAULT NULL,
  `derived_from_word_id` varchar(11) DEFAULT NULL,
  `rank` varchar(11) DEFAULT NULL,
  `disabled` varchar(1) DEFAULT NULL,
  `audio` varchar(128) DEFAULT NULL,
  `usage_en` text,
  `usage_de` text,
  `number_value` varchar(11) DEFAULT NULL,
  `type` varchar(16) DEFAULT NULL,
  `level` varchar(8) DEFAULT NULL,
  `created_at` date DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;
```
### import
在phpMyAdmin中点“Import”:
- File to import    
openrussian_public-words.csv
- Format    
csv

# [App](https://github.com/veic-2005/export-vocab)
点击 "Code table" 按钮后，
```
Debug->output
```
## 手工处理
removed:
```
Ln1282: pf_11jlbnm,заходить
Ln5301: tcnm,есть
```
从
```
Ln5201: fuf,ага
```
开始，
除了
```
Ln5204: pfvjr,замок
Ln5224: k_10urbq,лёгкий
Ln5235: dthnjk_10n,вертолёт
Ln5237: jwtybnm,оценить
```
到
```
Ln5292: jwtybnm,оценить
```
全部删除。

# Ref
- [how-to-initialize-a-dictionary-with-a-collection-initializer](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/how-to-initialize-a-dictionary-with-a-collection-initializer)
- [Persistent hashcode for strings](https://stackoverflow.com/questions/36845430/persistent-hashcode-for-strings)
