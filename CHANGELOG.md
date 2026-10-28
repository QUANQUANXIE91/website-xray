# Changelog

## 1.3.0 — 2026-10-28
- **证据纪律（强制）**：每条 P1/P2/P3 必须带 出处 URL + 发现日期 + 置信度（高/中/低）
- 新增 **未确认事实清单** 报告章节：弱证据/推断结论单列，禁止写进邮件和开场话术
- 长处吸收自 trade-customer-intel（SIEGER V2）的 claim/evidence 分离方法

## 1.2.1 — 2026-10-27
- **多平台安装**：README 增加全平台安装表（Hermes / Codex CLI / Claude Code / Gemini CLI / Cursor / Accio Work / WorkBuddy），对齐 Agent Skills 开放标准（agentskills.io）
- 新增 `agents/openai.yaml`：Codex CLI 可选元数据 sidecar
- 提供 `website-xray.zip` 技能包，供 Accio Work 等平台一键上传

## 1.2.0 — 2026-10-27
- **通用化**：全库去行业化 —— 我方产品位改为占位符，README/示例/信号库不再绑定任一品类，任何外贸品类开箱即用
- 新增 **供应链缺口体检表**（6 项 ✓/?/✗：交期/MOQ/认证/产能/价格带/售后），只有 ✗/? 进 P1-P3
- 新增 **复制即用四件套**（开场句/追问×4/样品×3/邮件P1段，独立成块一键复制）
- 新增 **分析历史归档**（`reports/` + `INDEX.md`，同客户增量透视不重跑）
- 示例重命名：`example-pacific-solar.md` → `example-system-integrator.md`；`example-fmcg-distributor.md` → `example-distributor.md`
- 修正模板错别字（常常景→日常场景）

## 1.1.0 — 2026-10-27
- 独立成库发布至 GitHub
- 新增 `references/commercial-dna-playbook.md`：商业基因判定信号库（3 判定 × 可核查信号）、缺口类型库（10 类 + 切入句模板）、追问句式库（6 场景双语骨架）、样品套件变体表
- 新增 `examples/`：两份实战报告（脱敏）
- 新增 `README.md`、`CHANGELOG.md`、`LICENSE`
- SKILL.md 增加「集成：发信流水线两档用法」「版本历史」章节
- 全量原创化改写：与启发来源文章的文本重合度从 0.65%（8 字滑窗）降至 **0.00%**

## 1.0.0 — 2026-10-27
- 初版：6 步流水线（抓取→商业基因→四维→P1-P3→切入动作→输出回写）+ 报告模板
- 实战验证 2 家客户（系统集成商 / 全渠道分销集团）
