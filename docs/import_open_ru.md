---
title: "导入word"
description: "openrussian"
date: 2026-02-09T08:08:08+08:00
---
- [fx 4.5+](https://learn.microsoft.com/en-us/dotnet/framework/install/versions-and-dependencies?source=recommendations#remarks-for-version-45-and-later)

.NET Framework 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 4.7.1, 4.7.2, and 4.8 are in-place updates to .NET Framework 4.5.

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
复制输出信息，保存为一个文本文件。
## 手工处理
从
```
Ln5201: fuf,ага
```
开始，到
```
Ln5292: gjdjl,повод
```
全部删除（包含Ln5201和Ln5292）；然后另存为新的文件。
### 新文件处理
在Ln5200后，添加：
```
pfvjr,замок
k_10urbq,лёгкий
dthnjk_10n,вертолёт
jwtybnm,оценить
```
#### 再 removed
```
Ln5213: tcnm,есть
Ln1282: pf_11jlbnm,заходить
```

# Ref
- [how-to-initialize-a-dictionary-with-a-collection-initializer](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/how-to-initialize-a-dictionary-with-a-collection-initializer)
- [Persistent hashcode for strings](https://stackoverflow.com/questions/36845430/persistent-hashcode-for-strings)
