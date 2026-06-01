# geo-content-writer

一个用于「生成式引擎优化（GEO）」的 Claude Agent Skill。给它一段内容，它会按 GEO 改写/优化，让内容更容易被 ChatGPT、Perplexity、Google AI 概览、Gemini 等 AI 搜索/生成式引擎引用。基于 Princeton/KDD 2024 的 GEO 研究（arXiv:2311.09735），并结合 2025–2026 现代引擎的检索机制。

## 它做什么

- 优先用**真实、具体的证据**武装内容：统计数据、直接引文、可信来源引用。
- 提升**流畅度与可抽取性**（先给答案、句子可独立成立、标注日期）。
- 避开无效手法：关键词堆砌、生僻词堆砌、纯权威语气。
- 守住**真实性红线**：不编造数据/来源，无法确认的标 `[待核实]`，不用模糊归因。
- 默认挑两个互补策略（首选 流畅度 + 统计数据），按领域调整，不全堆。

> 想做整站/整业务的 GEO 规划（而非单段改写）？见配套 skill **geo-matrix-builder**。

## 何时触发

用户提到 GEO、AI 搜索优化、想让内容被 AI 引用、为生成式引擎/AI 概览写内容、或粘贴一段内容要求"针对 AI 搜索优化"时。

## 安装方式

Skill 不跨平台同步，按你使用 Claude 的环境分别安装。

### Claude.ai（网页 / App）
在 **Settings → Features** 上传 `geo-content-writer.skill`（本仓库已附，本质是 zip；若上传框只认 `.zip` 后缀，改名即可）。需 Pro/Max/Team/Enterprise 套餐并开启代码执行。自定义 Skill 按用户个人维度，团队成员需各自上传。

### Claude Code
```bash
cp -r geo-content-writer ~/.claude/skills/      # 个人级
# 或放进项目内的 .claude/skills/
```

### API / Agent SDK
将 `geo-content-writer/` 目录或 `.skill`（zip）通过 Skills API 上传（需 `skills-2025-10-02` beta 头），再在请求中以 skill_id 引用。

## 安全提示

Skill 会为 Claude 注入指令。安装前请阅读 `geo-content-writer/SKILL.md` 确认内容，只安装来自可信来源的 Skill。

## 许可

（未指定。可按需添加 LICENSE，例如 MIT。）
