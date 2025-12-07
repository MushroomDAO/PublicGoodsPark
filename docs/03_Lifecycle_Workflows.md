# 03. Lifecycle Workflows (全生命周期流程)

本文档通过流程图详细说明了创作者和用户在生态中的关键交互过程。

## 🛠️ 创作者旅程 (Creator Journey)

从一个 Idea 到成为 Park 签约项目的全过程。

```mermaid
sequenceDiagram
    participant C as Creator (Github/Any Platform)
    participant P as Park Platform (AI System)
    participant U as Users (Angels)

    Note over C, P: 阶段一：准入与集成 (Onboarding)
    C->>P: 登录并签署《共创协议》
    B->>B: 添加 park.json 和 LICENSE_PARK.md
    B->>B: 集成 @park/sdk (验票 & 计费)
    B->>P: 部署上线 (Level 1 - Free Builder)

    Note over B, P: 阶段二：筛选与晋升 (Audition)
    P->>P: AI "星探算法" 监测数据
    P-->>B: 发送 "Ranger" 签约邀请 (表现优异)
    B->>P: 签署 Grant 协议 (承诺稳定性)

    Note over B, U: 阶段三：加速与反馈 (Acceleration)
    P->>B: 注入 Grant 资源 (Credits, API)
    P->>U: 匹配 "首百天使" 用户
    U->>B: 试用并反馈
    P->>B: AI 汇总产品改进建议 (Issue/Report)

    Note over B, P: 阶段四：商业化与分润 (Money)
    U->>B: 支付增量服务费
    B->>P: T+N 自动结算分润
```

## 🎫 用户旅程 (User Journey)

游客如何入园、消费及退出的流程。

```mermaid
graph LR
    subgraph "Entry (入园)"
        A[访问官网] --> B{购买门票?}
        B -- Yes --> C[支付押金/年费]
        C --> D[获得 Park ID/一票通]
    end

    subgraph "Usage (游玩)"
        D --> E[使用 App A /免费额度内]
        D --> F[使用 App B /增量高级功能]
        F --> G{确认支付?}
        G -- Yes --> H[扣除余额]
        G -- No --> E
    end

    subgraph "Exit (退园)"
        I[申请退票] --> J{计算退款}
        J --> K[初始费 - 已用管理费 - 未结清算 - 手续费]
        K --> L[退还剩余资金]
    end
```

## ⚖️ 治理与退出 (Governance & Succession)

针对项目烂尾或创作者退出的应急机制。

1.  **主动退出**：开发者在 `park.json` 标记 `deprecated`。平台给予 30 天缓冲期通知用户。
2.  **社区接管 (针对签约项目)**：
    *   触发条件：主要维护者失联或严重违反 SLA，且应用仍有大量活跃用户。
    *   执行：DAO 启动代码分叉或接管程序（基于 Grant 协议中的托管条款）。
    *   权益：原作者保留部分永久荣誉分润，管理权移交新维护者。
