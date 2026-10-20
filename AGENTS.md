# edges-workspace-viruspc

peng cheng 的 Compose 工作区根：通过 `edges compose` 挂载公开脑与私密脑。本仓本身不承载笔记、任务或项目记忆；内容写入各 composed 子仓。

<!-- project-harness:start -->
<!-- project-harness-constraints:start -->
## 本层硬约束

- 本仓是 thin Compose workspace：只维护 AGENTS.md Compose 区块与 git submodule。
- 不要在本仓根目录跑完整 `edges init` 生成 memory/tasks；写内容时进入对应 brain 子仓。
- 默认优先写公开脑；敏感/私密内容只写私密脑。
<!-- project-harness-constraints:end -->

<!-- project-harness-compose:start -->
## 组合

<!-- project-harness-compose:end -->
<!-- project-harness:end -->
