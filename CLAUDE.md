# CLAUDE.md — JC-manju-skills

## 这是什么

短剧+短故事创作 Skill 集合。9 个 Skill，覆盖「创作 → 视觉资产 → 分镜 → 养护」：

- **创作层**：短剧世界模型 + 短故事引擎（从零到成稿）
- **资产层**：角色/场景/道具提示词（Pinterest 参考图 → 生图 JSON）
- **分镜层**：剧本转分镜（导演工作本）+ 分镜转大图（导演节拍卷轴）
- **养护层**：记忆压缩（归档）+ 一致性巡检（质检）

## 目录结构

```
JC-manju-skills/
├── JC-短剧-世界模型/       # 从零创作短剧，原型激发+三角引擎+逐场写作
├── JC-短故事/              # 从零创作知乎短篇，第一人称，9阶段管线
├── JC-角色设计提示词/       # Pinterest 搜参考图 → 角色设定图 JSON
├── JC-场景提示词/          # Pinterest 搜参考图 → 场景设定图 JSON
├── JC-道具提示词/          # Pinterest 搜参考图 → 道具设定图 JSON
├── JC-剧本转分镜/          # 导演式分镜：锁定导演→提取节奏档案→A/B/C/D→导演工作本
├── JC-分镜转分镜大图/       # 导演工作本 → GPT Image 2 导演节拍卷轴
├── JC-Wiki-记忆压缩/       # 养库：通用摄入+小说催化提取+Obsidian集成
├── JC-Wiki-一致性/         # 质检：全库巡检，抓穿帮/矛盾/断链
├── SKILL-DESIGN.md         # 设计经验沉淀（原型挪移法/节拍索引法/三角引擎等）
├── README.md
├── LICENSE                 # CC BY-NC 4.0
└── CLAUDE.md               # 本文件
```

## 管线数据流

```
世界模型（创作） → wiki/角色/*.md, wiki/世界观/*.md
                        ↓
角色/场景/道具提示词 → wiki/**/*.design.json（视觉资产）
                        ↓
剧本转分镜 → analysis/shot-design.md（导演工作本）
                        ↓
分镜转大图 → GPT Image 2 导演节拍卷轴

记忆压缩 ←→ 一致性巡检（养护循环，贯穿全程）
```

## Skill 规范

每个 Skill 目录结构：
```
Skill名/
├── SKILL.md          # 必须：YAML frontmatter (name/description/triggers) + Markdown 正文
├── references/       # 可选：参考资料
└── scripts/          # 可选：执行脚本
```

## 开发规则

1. **每个 Skill 独立可触发**：用户可单独调用任意 Skill
2. **SKILL.md 优先中文**：面向国内用户，description 和正文都中文
3. **命名规则**：`JC-中文描述` 格式
4. **新增 Skill**：先更新本文目录结构，再更新 README.md
5. **许可证**：CC BY-NC 4.0，商用需授权
