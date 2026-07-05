# 🎬 影视 Skills

AI 影视工作流 Skill 合集。包含从前期策划、角色/场景/道具资产提取、分镜设计，到 Banana/Veo/LTX/Grok 等多模型生图生视频提示词组装，再到后期解说、合成配音的全链路 Skill。

这些 Skill 遵循 [SKILL.md 规范](https://docs.anthropic.com/en/docs/agents-and-tools/agent-skills)，可用于 **韭菜盒子 Studio**、**Claude Code**、**OpenCode** 等支持 Skill 的 AI 工具。

---

## 📦 安装

### 韭菜盒子 Studio

将本仓库克隆到 Skill 目录：

```bash
git clone https://github.com/liuyunlong2021-wq/yingshi-skills.git ~/.agents/skills/yingshi-skills
```

然后在韭菜盒子的 Skill 管理面板中刷新即可看到所有 Skill。

### Claude Code / OpenCode

```bash
git clone https://github.com/liuyunlong2021-wq/yingshi-skills.git ~/.agents/skills/yingshi-skills
```

在对话中通过 `/skill` 或 Skill 选择器加载使用。

### 手动下载

直接在 [Releases](https://github.com/liuyunlong2021-wq/yingshi-skills/releases) 下载 ZIP，解压到你的 Skill 目录即可。

---

## 🗂️ Skill 清单（24 个）

### 🎬 影视前期

| Skill | 说明 |
|-------|------|
| `film-type-analysis` | 新项目启动时的风格分析。决定画幅比例、风格设计、节奏设计，融合灯光设计到统一输出中 |
| `film-engineering-book` | 将剧本转化为素材工程手册。把面向观众的剧本翻译为面向生产的可复用素材单元（对白覆盖、动作链、揭示、插入、重置、反应） |
| `film-character-asset` | 剧本角色分析，输出双层资产规格：精简 control_table（供下游自动化） + 轻量 production_bible（供人工查阅复用） |
| `film-prop-asset` | 剧本道具分析，输出双层道具资产规格，足够 detail-hungry 的下游图像模型使用 |
| `film-scene-asset` | 将剧本场景转化为最终空镜主镜头场景资产。继承风格分析的风格和灯光，锁定可复用摄影机真值，穷举主镜头所有可见元素 |

### 🎞️ 分镜设计

| Skill | 说明 |
|-------|------|
| `film-shot-design` | 将剧本内容和工程手册素材单元转化为可执行的分镜设计。继承节奏、尊重工程手册，只输出下游有用的镜控数据 |

### 🍌 Nano Banana 生图提示词

| Skill | 说明 |
|-------|------|
| `banana-character-prompt` | 角色分析 → Banana JSON 提示词转换。强调显式细节、参考表布局、强力负向约束 |
| `banana-scene-prompt` | 场景分析 → Banana JSON 提示词转换。以一句决定性叙事身份句开头，然后分层场景控制 |
| `banana-prop-prompt` | 道具分析 → Banana JSON 提示词转换。保留可见结构、布局块、多视角细节、生成关键标记 |
| `banana-grid-shot-prompt` | 分镜设计 → Banana 3×3 故事板宫格 JSON 提示词。写简短自然语言电影节拍，非刚性关键词链 |
| `banana-storyboard-edit-prompt` | 单张故事板面板图片 → Nano Banana Pro 图像编辑提示词。对面板级角色/场景/道具/融合修复写结构化中文编辑提示词 |

### 🎥 视频生成提示词

| Skill | 说明 |
|-------|------|
| `veo-video-prompt` | 分镜设计 → Veo 图生视频/首尾帧生视频提示词。纯组装阶段，严格遵守端点约束 |
| `grok-video-prompt` | 分镜设计/故事板首帧 → Grok 图生视频提示词。强制使用经过验证的中文分段时间线格式 |
| `ltx-video-action` | 分镜设计 → LTX 2.3 图生视频提示词。只读紧凑下游字段，从对白长度计算最终视频时长 |
| `voice-bound-shot-video` | 语音绑定单镜头生成。从首帧 + 动作标签 + 干净语音音频 + 对白文本，生成口型同步镜头 |

### 🎬 视频后期

| Skill | 说明 |
|-------|------|
| `video-composer` | 视频合成工具，拼接视频片段并添加字幕 |

### 📝 内容创作

| Skill | 说明 |
|-------|------|
| `novel-writing` | 小说创作全流程专家。从灵感到成稿复盘 9 大阶段：灵感策划、市场分析、核心梗、角色设计、大纲、章纲、文案包装、正文写作、复盘分析 |
| `manhua-script-agent` | 漫剧/短剧剧本智能生成器。基于「世界观+极致角色+催化剂→故事自然涌现」核心机制，驱动压力值和蝴蝶效应自动推进剧情 |
| `narrato-docu` | 影视解说文案工坊。支持粘贴 SRT 字幕或描述内容，输出带时间戳的结构化解说 JSON |
| `narrato-short` | 短剧解说工坊。精通黄金开场、爽点放大、个性吐槽、悬念预埋等短剧解说核心技巧 |

### 🎨 其他生成

| Skill | 说明 |
|-------|------|
| `gpt-image-2-prompts` | GPT Image 2 图像生成提示词专家。搜索 Reference Gallery 分类图库匹配最佳提示词模板 |
| `qwen-tts-voice-design` | 将剧本文字/对白/角色信息转化为 Qwen TTS 语音设计提示词，推断合适的声音身份、情绪基调、说话节奏 |
| `runninghub` | RunningHub API 全能力（170+ 端点）。文生图、图生视频、文生语音、音乐生成、3D 建模、图像放大、AI 应用等 |

### 🔧 工具

| Skill | 说明 |
|-------|------|
| `skill-builder` | 将用户提供的文本或 Markdown 素材整理为标准 Skill 包草稿 |

---

## 📁 目录结构

```
yingshi-skills/
├── README.md
├── film-type-analysis/        # 影视风格分析
├── film-engineering-book/     # 素材工程手册
├── film-character-asset/      # 角色资产提取
├── film-prop-asset/           # 道具资产提取
├── film-scene-asset/          # 场景资产提取
├── film-shot-design/          # 分镜设计
├── banana-character-prompt/   # Banana 角色提示词
├── banana-scene-prompt/       # Banana 场景提示词
├── banana-prop-prompt/        # Banana 道具提示词
├── banana-grid-shot-prompt/   # Banana 故事板宫格提示词
├── banana-storyboard-edit-prompt/  # Banana 故事板编辑提示词
├── veo-video-prompt/          # Veo 视频提示词
├── grok-video-prompt/         # Grok 视频提示词
├── ltx-video-action/          # LTX 视频动作
├── voice-bound-shot-video/    # 语音绑定单镜头
├── video-composer/            # 视频合成
├── gpt-image-2-prompts/       # GPT 图像提示词
├── qwen-tts-voice-design/     # Qwen 语音设计
├── runninghub/                # RunningHub 全能力
├── novel-writing/             # 小说创作
├── manhua-script-agent/       # 漫剧剧本
├── narrato-docu/              # 影视解说
├── narrato-short/             # 短剧解说
└── skill-builder/             # Skill 构建器
```

---

## 🔄 工作流示意

```
剧本/创意
    │
    ├─→ film-type-analysis ──→ 风格/比例/灯光方案
    │
    ├─→ film-engineering-book ──→ 素材工程手册
    │
    ├─→ film-character-asset ──→ 角色资产
    ├─→ film-prop-asset ──→ 道具资产
    └─→ film-scene-asset ──→ 场景资产
              │
              ▼
       film-shot-design ──→ 分镜设计 JSON
              │
    ┌─────────┼─────────┬──────────────┐
    ▼         ▼         ▼              ▼
  banana-*  veo-*    grok-*        ltx-*
  提示词    提示词    提示词         提示词
    │         │         │              │
    └─────────┴─────────┴──────────────┘
              │
              ▼
       video-composer ──→ 最终成片
              │
              ▼
       narrato-* ──→ 解说配音
```

---

## 📄 许可

本仓库中的 Skill 均为原创内容，采用 [MIT License](LICENSE) 开源。

---

## 🤝 贡献

欢迎提交 Issue 和 Pull Request。

如果你有好的影视 Skill 想分享，请确保：
1. 包含完整的 `SKILL.md`（含 `name` 和 `description` frontmatter）
2. 如有脚本/参考文件，放入 `scripts/`、`references/` 子目录
3. 在 PR 描述中说明 Skill 的用途和使用场景
