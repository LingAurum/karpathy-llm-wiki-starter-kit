# compile

## 功能

将 `sources/` 中多个来源笔记的同类概念合并，生成 `wiki/` 中的永久概念页。

## 触发条件

当 `sources/` 中有 2 个以上不同来源涉及同一概念，且满足 `2-source-quality` 规则时触发。

## 处理流程

1. 检索 sources/ 中涉及目标概念的所有笔记
2. 交叉验证：两个来源必须共享具体的 claim 或框架（不只是宽泛主题）
3. 合并摘要，消除冗余
4. 发现与其他 wiki 概念的关联
5. 生成永久概念页

## 输出格式

在 `wiki/《概念名》.md` 创建文件，使用 `概念卡` 模板，frontmatter：

```yaml
title: "概念名"
type: 概念卡
status: 草稿
created: YYYY-MM-DD
updated: YYYY-MM-DD
sources: ["[[来源1]]", "[[来源2]]"]
tags: ["领域标签"]
```

## 规则引用

- 必须满足 [[2-source-quality]] 才可 compile
- 关键词标记参考 [[keyword-registry]]
