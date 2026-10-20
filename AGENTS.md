# edges-workspace-viruspc

peng cheng 的 Compose 工作区根：通过 `edges compose` 挂载公开脑与私密脑。本仓以 Compose 挂载两脑为主；默认内容写入 composed 子仓，本仓 harness 仅作工作区级索引。

<!-- project-harness:start -->
<!-- project-harness-constraints:start -->
## 本层硬约束

- 本仓是 Compose workspace 根：挂载公开脑与私密脑；默认业务内容写入 composed 子仓，不在本仓根堆笔记/任务正文。
- 本仓已 `edges init`（memory / skills / notes / projects）；tasks 未默认初始化。跨项目公开判断写公开脑，敏感内容写私密脑。
- 默认优先写公开脑；敏感/私密内容只写私密脑。
<!-- project-harness-constraints:end -->

<!-- project-harness-compose:start -->
## 组合

- [edges\-brain\-viruspc](<.harness/compose/edges-brain-viruspc>) — 公开个人大脑：默认写跨项目公开判断、笔记、任务；敏感内容不写这里 remote: https://github.com/VirusPC/edges\-brain\-viruspc.git
- [edges\-brain\-viruspc\-private](<.harness/compose/edges-brain-viruspc-private>) — 私密个人大脑：只写敏感/私密内容；默认优先写公开脑 remote: https://github.com/VirusPC/edges\-brain\-viruspc\-private.git
<!-- project-harness-compose:end -->

<!-- project-harness-local:start -->
## 本层系统维护信息

下面这些是索引，不是正文。按条目说明挑要读的，再打开对应内容。

- [本层 harness 材料索引](.harness/README.md) — 本层 harness 材料的组织清单。各材料只在这里登记。
<!-- project-harness-local:end -->
<!-- project-harness:end -->
