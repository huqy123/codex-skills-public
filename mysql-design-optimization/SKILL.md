---
name: mysql-design-optimization
description: Design or review MySQL schemas, constraints, indexes, slow queries, EXPLAIN plans, statistics SQL, and schema migrations across environments. Verify the actual version, structure, workload, and change risk before recommending executable SQL.
---

# MySQL 设计与优化

先确认真实版本、结构、数据规模和访问方式，再提出 DDL、索引或查询改写。语法能执行，不等于统计正确、性能更好或适合上线。

按用户授权区分只读调查、脚本交付和实际执行。使用当前环境已配置的安全连接方式，不要求某个私有连接技能。写入、DDL、索引创建删除和回填都要先确认目标、范围与执行授权。

## 最低证据

- 目标环境、数据库产品及精确版本；哪些环境需要分别执行，不能默认各环境相同。
- `SHOW CREATE TABLE`、`SHOW INDEX`，包括类型、字符集、排序规则和现有约束。
- 实际 SQL、代表性参数、数据规模、增长、读写比例和排序/分页方式。
- 变更时新旧应用是否并存；数据库、代码及任务的发布顺序。

缺少证据时可以给明确标注假设的草案，不称为已验证上线脚本。不要公开账号、密码、连接地址、客户记录或完整数据库快照。

## 按任务读取

- 表、字段、唯一性、空值和关联设计：读 [结构设计](references/schema-design.md)。
- 慢查询、索引、执行计划、分页和统计口径：读 [查询与索引](references/query-index.md)。
- DDL、重命名、回填、大表变更和多环境发版：读 [结构变更](references/schema-change.md)。

## 交付原则

- 索引依据来自完整查询、现有索引及真实计划，不能仅凭字段名给结论。
- 已核实环境、只执行一次的改动，优先直接 DDL/DML、必要注释与核验 SQL；确有重跑、多环境差异或迁移规范时再补相应机制，不默认增加存储过程和动态 SQL。
- 统计先统一样本、时间、去重单位、状态含义和分母，不能把不同批次算出的数字拼成一个比例。
- 根据风险给出兼容顺序、锁与资源影响、备份要求、停止/回退方式及验证标准；数据库执行成功与业务验收分开报告。

本技能不包含固定环境参数，不依赖其他技能或预装迁移框架。自动部署沿用项目已有工具。
