# ingest

## 功能

处理 `inbox/` 中的原始素材，提取摘要、关键概念和元信息，生成来源笔记存入 `sources/`。

## 输入

- `inbox/` 中任意未处理的笔记（不含 `sources` frontmatter 引用）

## 处理流程

1. 读取 inbox 笔记内容
2. 提取标题、来源 URL、作者、发布日期
3. 撰写 3-5 句中文摘要
4. 提取 3-8 个关键概念，尽量与已有 wiki 概念关联
5. 识别值得深挖的方向

## 输出格式

在 `sources/《素材标题》.md` 创建文件，填入 `素材摘要卡` 模板结构，frontmatter 字段：

```yaml
title: "原标题"
type: 素材摘要卡
status: 想法
created: YYYY-MM-DD
updated: YYYY-MM-DD
sources: ["[[原inbox笔记名]]"]
tags: ["关键词1", "关键词2"]
```

## 规则引用

- 关键词分类参考 [[keyword-registry]]
- 多来源判断参考 [[2-source-quality]]
