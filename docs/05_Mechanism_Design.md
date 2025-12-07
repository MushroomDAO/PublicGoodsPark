# 05. Mechanism Design (机制设计)

本文档详细定义了 Public Good Park 生态运行的“硬规则”和技术标准。这些机制通过代码 (Protocol) 和合约 (Contract) 强制执行，是生态信任的基石。

## 📄 1. Park Protocol Specification

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
      "price": "0.5 GT",           // 增量服务价格 (G Token)
      "strategy": "per_request",   // 计费策略: per_request / time / storage
      "desc": "GPT-4 Level translation with context"
    }
  },
  "endpoints": {
    "verify": "/api/park/verify",  // SDK 提供的验证接口
    "charge": "/api/park/charge"   // SDK 提供的扣费接口
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
