# 中文技术文档写作风格

一个用于起草、改写、润色和审校中文技术文档的 Agent Skill，依据 yikeke 的《中文技术文档写作风格指南》整理，适用于 README、开发者指南、安装部署说明、API 文档、产品帮助和技术教程。

技能采用“核心规则＋按需参考”的组织方式，保留原指南中“必须”“建议”和“可选”的区别。用户要求与项目已有规范优先；修改表达时保持技术事实、命令、配置、标识符和原始日志不变。

## 规则范围

| 内容 | 参考文件 |
| --- | --- |
| 语气、用词、标题、段落、目录、命名与语法 | [语言与结构](references/language-and-structure.md) |
| 空格、列表、表格、图片、提示、代码与链接 | [内容元素与排版](references/content-elements.md) |
| 缩略语、数字、倍数、单位、标点与中英文混排 | [数字、单位与标点](references/numbers-and-punctuation.md) |
| 原文版本、章节对应关系和改编边界 | [来源与改编说明](references/source.md) |

完整入口见 [SKILL.md](SKILL.md)。

## 安装到 Codex

将仓库克隆到用户技能目录，使目录结构为 `~/.agents/skills/zh-tech-writing-style/SKILL.md`。

### Windows PowerShell

```powershell
New-Item -ItemType Directory -Force "$HOME/.agents/skills" | Out-Null
git clone https://github.com/Fei-xianmao/zh-tech-writing-style.git "$HOME/.agents/skills/zh-tech-writing-style"
```

### macOS 或 Linux

```bash
mkdir -p "$HOME/.agents/skills"
git clone https://github.com/Fei-xianmao/zh-tech-writing-style.git "$HOME/.agents/skills/zh-tech-writing-style"
```

也可以把本仓库目录放在项目的 `.agents/skills/zh-tech-writing-style/` 下，供该项目使用。已有同名技能时，更新原安装目录即可，避免重复安装。

Codex 会自动发现技能变更；如果技能没有出现，重启 Codex。安装位置和调用方式参见 [OpenAI 官方技能文档](https://developers.openai.com/codex/skills/)。

## 使用

在 Codex 中输入技能名称及任务：

```text
使用 $zh-tech-writing-style 改写下面的部署说明，保留技术事实、命令和参数。
```

```text
使用 $zh-tech-writing-style 审校 README.md，指出表达歧义、术语不一致和排版问题，并直接修改文件。
```

```text
使用 $zh-tech-writing-style，根据以下已确认的信息起草安装指南。缺失信息单独列出，不要补造。
```

任务与技能描述匹配时，Codex 也可以自动选择该技能。其他支持 Agent Skills 的工具可读取本仓库的 `SKILL.md`；安装目录和调用语法按对应工具的文档处理。

## 改写示例

原文：

> 本次优化使性能大幅提升，延迟从100ms降低到20ms，减少了5倍。

改写：

> 本次优化将延迟从 100 ms 降至 20 ms，降低了 80%。

如果原文只说“吞吐量增加两倍”，技能会提示确认是“增加了 2 倍”还是“增加到原来的 2 倍”，不会自行选择含义。

## 来源与许可

原指南：[yikeke/zh-style-guide](https://github.com/yikeke/zh-style-guide)。本技能依据版本 0.1、封面日期为 2025 年 1 月 6 日的 [PDF](https://zh-style-guide.readthedocs.io/_/downloads/zh-cn/latest/pdf/) 整理。

本仓库采用 [MIT 许可证](LICENSE.txt)，保留原作者 Keke Yi 的版权及许可声明。详细来源、PDF 指纹与整理时采用的约定见[来源与改编说明](references/source.md)。
