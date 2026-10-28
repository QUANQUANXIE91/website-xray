# 官网X光 · Website X-Ray

**输入一个客户官网 URL，一分钟产出"他做什么生意 → 他缺哪块 → 你从哪儿切进去"的三问报告。**

为 B2B 外贸开发信、寄样、深度追问提供**有出处的个性化弹药** —— 每条判断都挂在客户网站的具体页面上，找不到就写"未查到"，绝不编造。**品类无关**：任何外贸行业（机械/电子/食品/纺织/化工…）开箱即用。

```text
输入:  https://www.example-appliances.com  +  我方产品/认证  +  对方称呼
输出:  ┌ 商业基因三判定（身份 × 定位 × 采购节奏）
       ├ 四维透视（市场 / 客户 / 产品 / 终端消费者）
       ├ 供应链缺口体检（交期/MOQ/认证/产能/价格带/售后 → ✓/?/✗）
       ├ 缺口排序 P1-P3（每条 = 缺口 + 切入句 + 出处）
       ├ 切入动作（核心方向 + 3款样品套件 + 低阻力推进 + 4个双语追问）
       └ 复制即用四件套（开场句 / 追问 / 样品 / 邮件P1段）
```

## 为什么需要它

开发信死于两件事：**研究不足**（模板腔，客户一眼假）和**研究过头**（20 分钟读完官网，还是不知道该聊什么）。

官网X光把"读官网"变成一条 6 步流水线，卡在两个刚好的位置：

- **一分钟级**：并行抓取 + 角落信号清单，不逐页精读
- **结论级**：不停在"他家卖什么"，而是给出"他缺什么、凭什么进、寄哪三款、问哪四句"

## 报告长什么样（节选 · 通用占位示例）

> **供应链缺口体检**：交期 ✗（官网无交期声明）｜ MOQ ✗（无批发门槛说明）｜ 认证 ✓（footer 有认证墙）
>
> **P1（唯一主攻）**：技术栈空白 —— 他做全套方案，唯独缺 `<我方品类>` 这一环
> —— 切入：*"你们的项目里，`<我方品类>` 是绕不开的环节 —— `<我方产品>` 让你的方案从 A 升级到 A+B"* ↳ 出处：官网新闻页
>
> **复制即用四件套**：【① 开场句】【② 追问×4 中英双语】【③ 样品3款】【④ 邮件P1段】—— 一键复制直接开发

完整示例见 [`examples/`](examples/)（两份实战报告，客户侧已脱敏、我方产品位已占位符化）。

## 安装（多平台）

本仓库符合 **Agent Skills 开放标准**（[agentskills.io](https://agentskills.io)：`SKILL.md` + YAML frontmatter），同一份技能可直接装进 26+ 兼容平台，无需修改。

| 平台 | 安装方式 |
|------|---------|
| **Hermes Agent** | `git clone https://github.com/QUANQUANXIE91/website-xray.git ~/.hermes/skills/customer-development/website-xray` |
| **Codex CLI** | `git clone https://github.com/QUANQUANXIE91/website-xray.git ~/.codex/skills/website-xray`（项目级放 `.codex/skills/`；已附 `agents/openai.yaml` 元数据） |
| **Claude Code** | clone 到 `~/.claude/skills/website-xray` |
| **Gemini CLI** | clone 到 `~/.gemini/skills/website-xray` |
| **Cursor / 其他** | 项目级 `.cursor/skills/website-xray`；完整兼容列表见 agentskills.io |
| **Accio Work** | 技能页 → 「安装本地技能」→ 选择本文件夹；或用 `技能页 → 上传` 导入 `website-xray.zip` |
| **WorkBuddy** | 无需单独安装 —— WorkBuddy 的 AI 引擎经 Hermes 调用技能，Hermes 装好即自动可用 |

**通用三连（有哪个装哪个）：**

```bash
git clone https://github.com/QUANQUANXIE91/website-xray.git
cp -r website-xray ~/.codex/skills/       # Codex CLI
cp -r website-xray ~/.claude/skills/      # Claude Code
cp -r website-xray ~/.gemini/skills/      # Gemini CLI
```

**独立使用（不依赖任何框架）：** 把 `SKILL.md` 当作给任意 LLM Agent 的 Prompt 规范即可 —— 它只需要两个能力：抓网页、搜网页。

**装好后怎么唤起：** 「官网透视 https://xxx.com」「透视这个客户」「分析官网」「这个客户缺什么」「寄什么样品」

## 使用流程

```text
输入客户官网链接 → 填写我方产品信息 → 一键生成透视报告 → 复制四件套 / 归档到分析历史
```

- **复制四件套**：开场句、追问、样品、邮件段独立成块，直接贴进开发信
- **分析历史**：报告自动归档 `reports/` + `INDEX.md`，同客户下次透视走增量，不从零重跑

## 仓库结构

```text
website-xray/
├── SKILL.md                          # 执行规范（6 步流水线 + 质量红线）
├── README.md
├── templates/
│   └── report.md                     # 三问报告模板（含体检表 + 四件套）
├── references/
│   ├── commercial-dna-playbook.md    # 商业基因判定信号库 + 缺口类型库 + 追问句式库
│   └── mcpc-due-diligence.md         # 四维背调方法论（M/C/P/U）
├── examples/
│   ├── example-system-integrator.md  # 示例1：系统集成商（脱敏 + 占位符）
│   └── example-distributor.md        # 示例2：全渠道分销集团（脱敏 + 占位符）
├── reports/                          # 你的透视报告归档（分析历史）
├── CHANGELOG.md
└── LICENSE                           # MIT
```

## 与发信流水线的集成（可选）

本技能在实战中被拆成两档接入每日发信 Cron：

| 档位 | 用法 | 预算 |
|------|------|------|
| 深研档（高价值客户专档） | 每家跑完整 6 步，要素化进邮件（≥4 个个性化元素） | ≤2 分钟/家 |
| 轻量档（次级客户前 8 名） | 只做：一句话基因 + P1 + 1 个追问 | ≤1 分钟/家 |

接入方式：在 Cron Prompt 的深研步骤写一句「按 website-xray 报告结构产出，超时降级快研保发送量」。

## 质量红线（技能内置）

1. **有出处才算数** —— 每条判断挂来源页，搜不到写"未查到"
2. **P1 只能有一个** —— 排三个 P1 等于没有 P1
3. **追问句必须含他的事实** —— 出现 `[贵司]` 占位符就重写
4. **样品 3 款封顶** —— 日常 / 旺季 / 竞品替换，三类用途刚好
5. **不评判客户改变不了的事** —— 缺口必须是我方能接住的

## FAQ

**Q: 抓不到页面怎么办（JS 单页 / 403 反爬）？**
退回搜索快照 + LinkedIn/社媒侧写，报告标注"侧面数据"。不硬刚，不编造。

**Q: 和普通"背调"有什么区别？**
背调回答"他是谁"；官网X光回答"**我从哪儿切进去**" —— 输出直接是寄样方案和可复制的追问句。

**Q: 什么品类都能用吗？**
能 —— 技能不含任何行业假设，`我方产品/认证/品类` 全是输入参数；示例中的我方产品位即占位符。

**Q: 中文客户也能用吗？**
追问句强制中英双语输出；多语站优先读当地语言的 about/news 页（原文措辞才是他真正的调子）。

## License

MIT © QUANQUANXIE91
