<div align="center">

# anti-ai-foolish-zcode

**反AI傻味 · ZCode 插件版**

🇨🇳 **简体中文** | 🇬🇧 [English](README.en.md)

</div>

---

[anti-ai-foolish](https://github.com/forrestneo/anti-ai-foolish) 的 **ZCode 插件封装**——同一个经朱雀实测语料验证的去AI味终检（1108条规则A/B测试、AI段召回97%、手术后文本实测进入人工特征区间），打包成可通过 Plugin Marketplace 安装的本地插件。

与纯 skill 版内容一致，只是分发形态不同：插件版走 marketplace 安装、随插件管理启停；纯 skill 版复制即用。二选一即可，**不要同时装**（功能相同）。

## 安装

### 方式一：从 GitHub 安装（对外推荐）

```
ZCode → Plugin Marketplace → Add → Add Plugin Marketplace
→ 粘贴 https://github.com/forrestneo/anti-ai-foolish-zcode
→ Personal → anti-ai-foolish-market → anti-ai-foolish-zcode → Install
```

ZCode 会把该仓库作为 marketplace 源，读取根目录的 `marketplace.json` 完成安装。GitHub 访问不稳时可在代理环境下操作，或改用方式二。

### 方式二：clone 到本地再 Add

```bash
git clone https://github.com/forrestneo/anti-ai-foolish-zcode.git
```

```
Plugin Marketplace → Add → 粘贴 clone 下来的本地目录
```

### 方式二：如果你在用纯 skill 版

直接用 [anti-ai-foolish](https://github.com/forrestneo/anti-ai-foolish)，无需本插件。

## 安装后使用

新开对话，输入（或从 composer 技能选择器选 anti-ai-foolish-zcode）：

```
帮我终检这篇文章 C:\path\to\draft.md
```

它会跑四步工作流：①机械筛（六硬门+Z分）→ ②人工判据三问 → ③七刀手术 → ④复检+平台实测建议。

## 结构

```
anti-ai-foolish-zcode/
├── .zcode-plugin/plugin.json        # ZCode 插件清单
├── marketplace.json                 # 本地市场清单
└── skills/anti-ai-foolish-zcode/    # 完整skill（标准格式）
    ├── SKILL.md                     # 工作流+铁律+边界
    ├── scripts/                     # preflight / scanner / abtest
    ├── rules/                       # 1108条规则（13分库，五态标注）
    ├── validation/                  # A/B重验框架+结果
    └── references/                  # 方法论/评测报告/路线图
```

依赖：Python 3.8+（纯标准库），离线运行，不上传任何文本。

## 它能做什么

- **发文前终检**：六硬门（冒号/破折号/直引号/概念引用腔/疑问句密度/无小节标题）+ Z分 → 可发 / 改后复检 / 停下手术
- **全规则扫描**：1108条规则命中分层报告，每条带修法与豁免提示
- **七刀手术指引**：从冒号（最强AI信号 r=+0.43）到换骨架（骨架-燃料定律）的修复顺序
- **语料再验证**：新检测报告放进 `validation/corpus/` 重跑 `scripts/abtest.py`，全部规则状态自动重估

方法论的完整说明（三条被推翻的流行常识、骨架-燃料定律、52片段验证）见 [anti-ai-foolish 主仓库](https://github.com/forrestneo/anti-ai-foolish)。

## License

MIT
