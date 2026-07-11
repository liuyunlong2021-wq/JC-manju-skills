# JC-manju-skills

短剧创作 Skill 集合 —— 从零创作到分镜大图，8 个 Skill 覆盖「创作 → 视觉资产 → 分镜 → 养护」。

## 许可

Creative Commons BY-NC 4.0 — 个人学习、非商业使用免费。**商用必须事先获得授权**。

## 安装

```bash
git clone https://github.com/liuyunlong2021-wq/JC-manju-skills.git ~/.agents/skills/JC-manju-skills
```

## Skill 清单

| 阶段 | Skill | 说明 |
|------|-------|------|
| ✍️ 创作 | `JC-短剧-世界模型` | 从零创作短剧，原型激发+三角引擎+逐场写作 |
| ✍️ 创作 | `JC-短故事` | 从零创作知乎短篇，第一人称，9阶段管线 |
| 👤 资产 | `JC-角色设计提示词` | Pinterest 搜参考图 → 提取视觉DNA → 角色设定图 JSON |
| 🏠 资产 | `JC-场景提示词` | Pinterest 搜参考图 → 提取视觉DNA → 场景设定图 JSON |
| 🔧 资产 | `JC-道具提示词` | Pinterest 搜参考图 → 提取视觉DNA → 道具设定图 JSON |
| 🎞️ 分镜 | `JC-剧本转分镜` | 锁定导演→提取节奏档案→A/B/C/D 镜数选项→导演工作本 |
| 🖼️ 分镜 | `JC-分镜转分镜大图` | 导演工作本 → GPT Image 2 导演节拍卷轴 |
| 📦 养护 | `JC-Wiki-记忆压缩` | raw/ → wiki/ 归档，补双链，刷新 hot.md 热缓存 |
| 🔍 养护 | `JC-Wiki-一致性` | 全库巡检，抓穿帮/矛盾/断链/伏笔未收 |

## 数据流

```
世界模型（创作）→ wiki/角色/*.md, wiki/世界观/*.md
       ↓
角色/场景/道具提示词 → wiki/**/*.design.json
       ↓
剧本转分镜 → analysis/shot-design.md
       ↓
分镜转大图 → GPT Image 2 导演节拍卷轴

记忆压缩 ←→ 一致性巡检（养护循环）
```

## 使用

每个 Skill 独立可触发，也可以按管线串联使用：

```
# 从零创作短剧
用短剧世界模型帮我开一个新剧本

# 设计视觉资产
帮我设计主角的角色设定图

# 导演分镜
把这个剧本转成导演式分镜

# 分镜大图
把分镜转成导演节拍卷轴

# 养护
帮我整理一下知识库 / 做一次全库巡检
```

