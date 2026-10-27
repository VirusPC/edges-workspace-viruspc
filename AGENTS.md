# edges-workspace-viruspc

peng cheng 的默认工作区：工作区根以三个顶层 git submodule 挂载框架仓、公开脑与私密脑。安装并加载本入口后，以本仓作为工作区根，默认内容写入对应内容子模块，本仓 harness 作工作区级索引。

## 内容子模块

工作区根的这三个目录是普通 git submodule。新克隆本仓后，在工作区根执行 `git submodule update --init` 检出。

| 路径 | 角色 | 远程 |
| --- | --- | --- |
| `edges/` | Edges 框架仓：CLI、skills、extensions、ADR。改框架能力时写这里。 | https://github.com/VirusPC/edges.git |
| `edges-brain-viruspc/` | 公开个人大脑：默认写跨项目公开判断、笔记、任务。 | https://github.com/VirusPC/edges-brain-viruspc.git |
| `edges-brain-viruspc-private/` | 私密个人大脑：只写敏感或私密内容。 | https://github.com/VirusPC/edges-brain-viruspc-private.git |

## 默认工作区与会话入口

- **本仓是默认 workspace。** 以本文件所在目录的绝对路径作为工作区根，随实际安装位置解析，不硬编码路径。应用提供的默认 cwd、下载目录或沙箱根目录不改变这个选择。用户明确指定其他项目或输出位置时，按用户指定执行。
- **开始工作先定位根，再选择目标。** 加载本文件后，读取 `.edges/README.md`，按任务选择本仓或上表中的内容子模块，并读取目标目录的 `README.md` 与 `AGENTS.md`。笔记、任务、记忆、技能和项目的规则以该目录自己的文档为准。将命令的工作目录显式设为目标目录；不要依赖前一条命令的 `cd` 在后续调用中继续有效。
- **Edges 命令显式选择 scope。** 工作区级操作使用 `edges --scope <工作区根> ...`；操作内容子模块时使用该子模块的绝对路径作为 scope。不能因为应用启动在其他目录，就在那里初始化新的 harness 或保存工作区内容。
- **新文件默认归入本工作区。** 笔记、调研、项目材料、任务及其 Markdown、HTML、PDF 等交付物写入对应内容子模块，并遵循该子模块 `README.md` 与 `AGENTS.md` 的组织约定。同一任务的源文件与导出文件应有可追溯的归属。修改现有项目代码时，在该项目目录内完成。
- **临时工作也有固定落点。** 尚未归档的交付物、构建脚本、截图、预览与发布包默认放在 `<工作区根>/.work/<任务名>/`。`.work/` 是已忽略的本地暂存区，不是持久归档或跨设备同步位置；需要长期保留的内容应归入目标内容子模块。工具强制在应用目录生成文件时，在交付前复制到目标子模块或本暂存区，并返回实际文件链接。
- **子模块未就绪时保持归属。** 目标子模块未检出时，在工作区根运行 `git submodule update --init -- <路径>`。鉴权或网络受阻时，先在 `.work/<任务名>/` 暂存并说明待归档目标。不要把缺失子模块的普通目录当作已检出的仓库，也不要把私密内容改存公开脑。
- **安装需要接通应用入口。** 应用应直接打开本仓作为 workspace；如果应用固定使用其他 cwd，则应在它支持的启动指令或全局指令中引用本文件。安装流程需建立这一入口。仅克隆仓库或安装技能，不保证应用会自动发现、加载本文件；本文件也不会自行改变应用的 workspace 配置。

<!-- edges:start -->
<!-- edges-constraints:start -->
## 本层硬约束

- 本仓工作区根挂载三个内容 git submodule：`edges/`（框架）、`edges-brain-viruspc/`（公开脑）、`edges-brain-viruspc-private/`（私密脑）。检出用 `git submodule update --init`。这三份不写入 `.edges/compose/README.md`。
- 默认业务内容写入对应内容子模块，不在本仓根堆笔记/任务正文。
- 本仓已 `edges init`（memory / skills / notes / projects）；tasks 未默认初始化。跨项目公开判断写公开脑，敏感内容写私密脑。
- 默认优先写公开脑；敏感/私密内容只写私密脑。
- 内容子模块里的组织规则以该目录的 `README.md` 和 `AGENTS.md` 为准。
<!-- edges-constraints:end -->

<!-- edges-local:start -->
## 本层系统维护信息

下面这些是索引，不是正文。按条目说明挑要读的，再打开对应内容。

- [本层 harness 材料索引](.edges/README.md) — 本层 harness 材料的组织清单。各材料只在这里登记。
<!-- edges-local:end -->
<!-- edges:end -->
