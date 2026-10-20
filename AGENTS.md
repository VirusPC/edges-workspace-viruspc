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

- [edges\-brain\-viruspc](<.harness/compose/edges-brain-viruspc>) — 公开个人大脑：默认写跨项目公开判断、笔记、任务；敏感内容不写这里 remote: https://github.com/VirusPC/edges\-brain\-viruspc.git
- [edges\-brain\-viruspc\-private](<.harness/compose/edges-brain-viruspc-private>) — 私密个人大脑：只写敏感/私密内容；默认优先写公开脑 remote: https://github.com/VirusPC/edges\-brain\-viruspc\-private.git
<!-- project-harness-compose:end -->
<!-- project-harness:end -->
