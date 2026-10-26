# Codex Public Skills

这里放可跨项目复用的 Codex skills，内容已经做过脱敏，适合用于代码调查、开发协作、发布检查和会话交接。

## 技能列表

| 技能 | 用途 |
| --- | --- |
| [plain-chinese](plain-chinese/SKILL.md) | 用自然中文讲清原因、影响和操作方法。 |
| [task-efficiency](task-efficiency/SKILL.md) | 按风险选择调查、实现和验证范围，减少重复工作。 |
| [issue-code-trace](issue-code-trace/SKILL.md) | 核实问题的触发路径、原因、提交历史和版本状态，默认只调查。 |
| [release-candidate-review](release-candidate-review/SKILL.md) | 对明确的提测、合并或上线请求，检查完整候选和验证证据。 |
| [session-brief](session-brief/SKILL.md) | 手动整理会话和交接记录，不把摘要当成已经完成压缩。 |
| [personal-coding-standards](personal-coding-standards/SKILL.md) | 最小完整修改、分层、批量数据访问、精度、事务和契约兼容。 |
| [java-spring-maintenance](java-spring-maintenance/SKILL.md) | Java/Spring字段链路、并发资源、批量处理和JVM故障排查。 |
| [mysql-design-optimization](mysql-design-optimization/SKILL.md) | 按真实结构和执行计划设计表、优化查询并核对结构变更风险。 |
| [mail-log-analysis](mail-log-analysis/SKILL.md) | 读取指定系统日志邮件、归并异常并按授权保护邮件状态。 |

## 使用方式

每个目录都有一个 `SKILL.md`。将需要的完整目录（包括其中的 `references` 和 `agents`）复制到当前客户端支持的 skills 目录；具体安装方式以客户端说明为准。

可以只选择需要的技能，不要求同时安装整套。技能中提到的其他技能或框架是可选配合，不会自动安装或初始化。

`session-brief` 保持手动调用，其他技能按任务匹配。是否能执行原生会话压缩取决于宿主实际能力，不由技能文本保证。

技能不代表操作授权。调查不默认修改，修改不默认提交或推送；数据库写入、生产操作及其他外部变更仍遵守当前任务授权与环境限制。

## 脱敏范围

只保留跨项目可复用的方法，不包含公司项目代码、内部业务规则、真实订单和客户资料、数据库快照或连接配置、私有接口、凭据及个人绝对路径。

内部测试库和业务推进技能、具体邮箱配置和专用过滤规则，以及工作流框架安装包和原始会话记忆，不在本仓库发布范围内。MySQL参考资料是通用检查方法，不是可直接执行的生产变更脚本；邮件技能不内置账号、收信程序或定时任务。
