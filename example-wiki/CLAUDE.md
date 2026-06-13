# 本目录是一个 LLM Wiki。你(LLM)是它唯一的维护者。

## 主题范围

本 Wiki 聚焦 **AI + Python**:机器学习技术栈、深度学习基础、LLM 应用开发。
详见 [purpose.md](purpose.md)。

## 结构

- `raw/`        原始来源,**只读,永不修改**
- `wiki/`       你维护的知识层
  - `index.md`  全部页面的目录,每次操作后更新
  - `log.md`    操作日志,格式:`- YYYY-MM-DD [操作] 摘要`
  - `sources/`  每个来源一个摘要页,引用注明 raw/ 路径与小节
  - `concepts/` 概念页(理论、技术、方法)
  - `entities/` 实体页(库、框架、组织、人物)
  - `synthesis/` 跨来源综合分析页

## 约定

- 页面间引用一律用 `[[wikilink]]`;提到尚不存在的页面也先建链
- 每页 YAML frontmatter:`title` / `type` / `sources` / `updated`
- 引用原文时注明来源文件与小节,如 `(raw/02-transformer-attention.md §3)`
- 发现与已有内容矛盾时,**不要擅自取舍**,在相关页面用
  `> ⚠️ CONFLICT` 块标出双方说法及来源,等待人工裁决

## 操作

- **ingest `<file>`**:通读 → 建 `sources/` 摘要页 → 更新所有相关概念页/实体页
  (新建或补充,通常多页)→ 标记矛盾 → 更新 `index.md` 与 `log.md`
- **query `<问题>`**:只读 `wiki/` 作答并给引用;答案有沉淀价值时写成
  `synthesis/` 新页面并记入 log
- **lint**:全库体检,报告矛盾、死链、孤儿页、知识缺口,记入 log
