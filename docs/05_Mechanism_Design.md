# 05. Mechanism Design (机制设计)

本文档详细定义了 Public Good Garden (Park) 生态运行的“硬规则”和技术标准。

## 💎 1. Governance Token (GT) Definition

**Critical**: GToken，无投资回报，它是一种 **协议认可和加入的凭证**，此凭证可以获得协议成员的相应权利，遵守相应的规则，可以理解为门票、VIP Card等。

*   **Nature**: Governance Token.
*   **Function**:
    *   **Access**: 持有 GT 是使用 Park 内 Infra 服务的必要条件 (Visa)。
    *   **Commitment**: 购买并质押 GT 代表对生态长期价值的承诺。
    *   **Redemption**: GT 可用于抵扣增值服务的费用 (Burn)。
*   **Non-Transferability**: 在早期阶段，GT 只能通过官方合约购买或回售，后期计划提供流动性pool，实现自由交易。

## 🏦 2. The Vault (Regulation Hub)

**Critical**: Vault，它是 **调节枢纽 (Regulation Hub)**。

*   **Logic**:
    *   **Input**: Ticket Burns, Exit Fees.
    *   **Output**: Infra Mining Rewards.
*   **Safety Valve**:（待定）
    *   当 Vault 水位 < 10% 时，触发“紧缩模式”，降低 Mining 产出。
    *   当 Vault 水位 > 60% 时，触发“扩张模式”，增加 Builder Grant。

## 📄 3. Protocol Specification

### `park.json`
`park.json` 是应用的“身份证”和“价目表”，必须位于 Repository 根目录。

```json
{
  "name": "Super Translator",
  "version": "1.0.0",
  "type": "ai-tool",
  "config": {
    "free_tier": {
      "limit": "10 requests/day",  // 门票包含的免费额度
      "desc": "Basic translation model"
    },
    "premium_tier": {
      "price": "0.5 GT",           // 增量服务价格
      "desc": "GPT-4 Level translation with context"
    }
  }
}
```

### `LICENSE_PARK.md`
这是一个针对数字公共物品设计的双重许可协议：
1.  **保留著作权 (Copyright Reserved)**：代码和品牌归原作者所有。
2.  **社区运营授权 (Operation Grant)**：
    *   授予 Park DAO 及其分销网络商业运营权。
    *   授予 Park DAO 在特定条件下的“接管权”（见下文）。
    *   禁止创建封闭的“围墙花园”（即必须允许通过 Park ID 访问）。

---

## 🛡️ 2. 防公地悲剧机制 (Anti-Tragedy Mechanisms)

### 防搭便车 (Anti-Free-Rider)
*   **门票 (Ticket/SBT)**：门票不是为了收费，而是为了筛选。只有支付了押金/年费的用户才能调用 API。这天然过滤了绝大多数恶意爬虫和无效流量。
*   **速率限制 (Rate Limiting)**：即使是免费用户，通过 `park.json` 中的 `free_tier.limit` 强制执行每日配额。

### 防滥用 (Anti-Abuse)
*   **增量付费 (Incremental Cost)**：对于消耗高算力的请求，强制要求 G Token 支付。用户在发起请求时必须进行签名确认。

---

## 🤝 3. 创作者保障与抗退出 (Creator & Anti-Exit)

针对 Level 2 签约创作者 (Pro Ranger) 的特别机制。

### The Grant Agreement (Grant 协议)
*   **资源置换**：平台提供 Cloud Credits、天使流量、技术 Mentor。
*   **服务等级协议 (SLA)**：创作者承诺 99.x% 的可用性。
*   **反退出条款 (Non-Exit Clause)**：
    *   如果应用达到一定规模（如 >1000 DAU），创作者不得单方面关停服务。
    *   **数据遗产 (Data Heritage)**：如果创作者决定放弃项目，必须允许 DAO Fork 代码并在保留原作者分润权的前提下继续运营。

---

## 💰 4. 争议解决与仲裁 (Dispute Resolution)

### 自动化仲裁 (Level 1)
*   **触发条件**：API 返回 5xx 错误码。
*   **执行**：智能合约自动原路退回该笔交易的 G Token。

### 社区仲裁庭 (Level 2)
*   **触发条件**：用户认为结果质量差（如“AI生成的图不对版”），但 API 调用成功。
*   **流程**：
    1.  用户质押少量 G Token 发起申诉。
    2.  系统随机抽取 5 位高信誉用户 (Jury)。
    3.  Jury 查看脱敏后的 Input/Output 记录并投票。
    4.  **胜诉**：退款 + 奖励申诉费；**败诉**：没收质押金给 Jury 分红。

### `LICENSE_PARK.md` & `Grant Agreement`
这是 Park 生态的核心法律/代码契约，包含双重许可与责任承诺：

#### 1. 双重许可 (Dual Licensing)
*   **Copyright Reserved (保留著作权)**：代码的所有权归原作者所有。
*   **Operation Grant (运营授权)**：授予 Park DAO 在平台内进行商业运营、分销及代币化管理的权利。

#### 2. Grant 协议承诺 (The Ranger's Promise)
针对 **Level 2 签约创作者 (Rangers)**，必须签署链上 Grant 协议，包含以下条款：

*   **反“避园”承诺 (Non-Exit / Data Heritage)**
    *   **禁止围墙化**：核心服务不得在获得 Park 流量后突然转为封闭私有。
    *   **数据遗产继承**：若项目被判定为“烂尾”或“恶意关停”，DAO 有权启动托管程序，基于开源代码分叉维护，保障用户数据资产不丢失。
*   **SLA 服务保障 (Service Level Agreement)**
    *   承诺 API 可用性 (如 >99%)。
    *   严重 Bug 需在 48 小时内响应。
*   **优先权 (Priority)**
    *   在同等条件下，应用需优先支持 Park ID 登录和 GT 支付。

## 🛡️ 4. Dispute Resolution (争议解决)

*   **Level 1 (Automated)**: 
    *   SDK 自动捕获 HTTP 5xx 错误。
    *   触发智能合约秒级退款。
*   **Level 2 (Community Jury)**: 
    *   针对“结果质量差”等主观争议。
    *   由持票用户组成的随机仲裁庭 (Jury) 投票裁决。
    *   胜诉方获得 Token 奖励，败诉方扣除信用分。

