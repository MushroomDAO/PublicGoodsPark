# 04. Execution Roadmap (执行路线图)

从概念验证到生态繁荣的分阶段执行计划。

## 📅 Phase 1: MVP - The Foundation (基建与原型)

**目标**：跑通“支付-使用-分润”的最小闭环，验证商业模式。

- [ ] **Infrastructure Setup**
    - [ ] **统一身份中心 (Auth)**：Get MySBT, is Park ID.
    - [ ] **计费网关 (Billing Gateway)**：发送加密账单到Validator验证和上链，实时/延迟结算。
- [ ] **SDK Development (v0.1)**
    - [ ] 实现 `verifySBT()` (验票) 和 `chargeUser()` (扣费) 接口。
    - [ ] 发布 Node.js 版本 SDK。
- [ ] **First Apps (标杆应用)**
    - [ ] **App A**: AI 翻译工具 (高频刚需，测试并发)。
    - [ ] **App B**: AI 图片生成 (测试增量高额付费)。
    - [ ] **App C**: 简单的 API Wrapper (测试极简接入)。

## 📅 Phase 2: Automation & Grant (自动化与孵化)

**目标**：引入 AI 自动化运营，启动创作者签约计划。

- [ ] **AI Operations System**
    - [ ] **"星探"算法**：定义数据 Schema，自动抓取 Github/应用数据，识别潜力股。
    - [ ] **首百天使匹配**：根据用户标签 (Tags) 自动分发试用邀请。
- [ ] **Grant Program Launch**
    - [ ] 起草并部署链上《共创协议》和《Grant 协议》。
    - [ ] 接入云服务商 API，实现 Credits 自动发放。
- [ ] **Community Growth**
    - [ ] 招募第一批 10 位 Level 2 创作者 (Rangers)。
    - [ ] 举办第一次线上 Demo Day。

## 📅 Phase 3: Decentralization & Scale (去中心化与规模化)

**目标**：向 DAO 治理过渡，实现真正的“公共物品花园=公园Park”。

- [ ] **DAO Governance**
    - [ ] 启动社区投票系统（用于仲裁纠纷和下架决策）。
    - [ ] 开放财务面板，实时公示门票池和分润数据。
- [ ] **Tokenomics**
    - [ ] 设计 G Token 模型（治理权益 + 支付流通）。
    - [ ] 为创作者提供一键发币/积分的模版。

## 🚀 Immediate Next Steps (当前行动项)

1.  **定义数据结构**：设计“星探算法”所需的用户画像 Tags 和应用元数据 Schema。
2.  **开发 SDK 原型**：优先完成 Node.js 版本的 `verifySBT` 中间件。
3.  **招募首位开发者**：寻找一个愿意尝试的开源作者进行 1v1 访谈和测试。
