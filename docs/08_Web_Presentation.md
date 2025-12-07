# 08. Web Presentation (前端展示层)

本文档包含了 "Public Goods Garden Growth Roadmap" 的可视化组件代码。即使不懂代码，也可以将以下内容提供给前端工程师或 AI 辅助工具 (如 v0.dev) 直接生成页面。

## 🎨 Visual Component: GrowthRoadmap.tsx

这个组件可视化了三个阶段：**Soil (深耕)**, **Sprout (萌芽)**, **Bloom (盛开)**。

### Dependencies
*   React
*   Tailwind CSS
*   Lucide React (Icons)

### Source Code

```tsx
import React from 'react';
import { Leaf, Sprout, Flower, ShieldCheck, DollarSign, Users, ArrowRight, HeartHandshake } from 'lucide-react';

const GrowthRoadmap = () => {
  return (
    <div className="min-h-screen bg-neutral-900 text-neutral-100 font-sans selection:bg-emerald-500 selection:text-white">
      {/* Header / Manifesto */}
      <header className="max-w-4xl mx-auto px-6 pt-20 pb-12 text-center">
        <div className="inline-flex items-center justify-center p-3 bg-emerald-900/30 rounded-full mb-6 border border-emerald-800/50">
          <Leaf className="w-5 h-5 text-emerald-400 mr-2" />
          <span className="text-emerald-300 text-sm font-medium tracking-wide">PUBLIC GOODS GARDEN</span>
        </div>
        <h1 className="text-4xl md:text-6xl font-bold mb-6 bg-gradient-to-br from-white to-neutral-400 bg-clip-text text-transparent">
          A Journey to Sustainability
        </h1>
        <p className="text-xl text-neutral-400 max-w-2xl mx-auto leading-relaxed">
          这不仅是一次构建，更是一场关于“价值回归”的实验。
          <br />
          我们正在培育一个自我维持的去中心化公共物品生态。
        </p>
      </header>

      {/* Main Roadmap Container */}
      <main className="max-w-5xl mx-auto px-6 pb-24">
        <div className="relative">
          {/* Connecting Line (Desktop) */}
          <div className="hidden md:block absolute left-1/2 top-0 bottom-0 w-px bg-gradient-to-b from-emerald-900 via-emerald-500/50 to-neutral-800 -translate-x-1/2"></div>

          {/* STAGE 1 */}
          <div className="relative md:grid md:grid-cols-2 gap-12 mb-24 items-center">
            <div className="hidden md:block text-right pr-12">
               <div className="inline-block px-3 py-1 bg-neutral-800 rounded text-xs text-neutral-400 mb-2">2022 - 2025</div>
               <h2 className="text-3xl font-bold text-neutral-200">Stage 1: The Soil</h2>
               <p className="text-emerald-500 font-medium mt-1">深耕与奠基</p>
               <p className="text-neutral-400 mt-4 leading-relaxed">
                 Co-founders 开启“苦行僧模式”。无薪资，全职投入。
                 仅消耗极低成本用于服务器等硬支出。
                 专注于底层 Infra 构建，无融资，无营销。
               </p>
            </div>
            
            {/* Center Icon */}
            <div className="absolute left-0 md:left-1/2 w-12 h-12 -ml-0 md:-ml-6 flex items-center justify-center bg-neutral-800 border-2 border-emerald-600 rounded-full z-10 shadow-[0_0_15px_rgba(16,185,129,0.3)]">
              <ShieldCheck className="w-5 h-5 text-emerald-400" />
            </div>

            {/* Mobile Content */}
            <div className="pl-16 md:pl-12 md:hidden">
              <div className="inline-block px-3 py-1 bg-neutral-800 rounded text-xs text-neutral-400 mb-2">2022 - 2025 (Done)</div>
              <h2 className="text-2xl font-bold text-white">Stage 1: The Soil</h2>
              <p className="text-emerald-500 text-sm mb-3">深耕与奠基</p>
               <p className="text-neutral-400 text-sm leading-relaxed">
                 “苦行僧模式”。0 薪资。完成核心架构。
               </p>
            </div>
            
            <div className="hidden md:block pl-12">
              <div className="bg-neutral-800/50 p-6 rounded-xl border border-neutral-700/50">
                <ul className="space-y-3 text-sm text-neutral-300">
                  <li className="flex items-center"><span className="w-2 h-2 bg-emerald-500 rounded-full mr-3"></span>Monk Mode: $0 Salary</li>
                  <li className="flex items-center"><span className="w-2 h-2 bg-emerald-500 rounded-full mr-3"></span>Hard Cost Only</li>
                  <li className="flex items-center"><span className="w-2 h-2 bg-emerald-500 rounded-full mr-3"></span>Infra Core Completed</li>
                </ul>
              </div>
            </div>
          </div>

          {/* STAGE 2 (UPDATED) */}
          <div className="relative md:grid md:grid-cols-2 gap-12 mb-24 items-center">
             <div className="hidden md:block text-right pr-12">
              <div className="bg-emerald-900/10 p-6 rounded-xl border border-emerald-500/20">
                <ul className="space-y-3 text-sm text-neutral-300">
                  <li className="flex items-center justify-end font-semibold text-emerald-400">Beta Version Live <span className="w-2 h-2 bg-emerald-400 rounded-full ml-3 animate-pulse"></span></li>
                  <li className="flex items-center justify-end">Sponsorship: ~$2,500/mo <HeartHandshake className="w-4 h-4 ml-3 text-emerald-400" /></li>
                  <li className="flex items-center justify-end">Team: Ramen Profitability <DollarSign className="w-4 h-4 ml-3 text-emerald-400" /></li>
                </ul>
              </div>
            </div>

            {/* Center Icon */}
            <div className="absolute left-0 md:left-1/2 w-12 h-12 -ml-0 md:-ml-6 flex items-center justify-center bg-neutral-900 border-2 border-emerald-400 rounded-full z-10 shadow-[0_0_20px_rgba(52,211,153,0.4)]">
              <Sprout className="w-6 h-6 text-emerald-400" />
            </div>

             <div className="pl-16 md:pl-12">
               <div className="inline-flex items-center px-3 py-1 bg-emerald-900/30 border border-emerald-800 rounded text-xs text-emerald-300 mb-2">
                 <span className="relative flex h-2 w-2 mr-2">
                    <span className="animate-ping absolute inline-flex h-full w-full rounded-full bg-emerald-400 opacity-75"></span>
                    <span className="relative inline-flex rounded-full h-2 w-2 bg-emerald-500"></span>
                  </span>
                 Current Stage: 2026 Q1-Q2 (Alpha/Beta)
               </div>
               <h2 className="text-3xl font-bold text-white">Stage 2: The Sprout</h2>
               <p className="text-emerald-400 font-medium mt-1">萌芽与“拉面盈利”</p>
               <p className="text-neutral-400 mt-4 leading-relaxed">
                 <strong>闭环验证：</strong> Beta 版上线，跑通“Infra-Protocol-App”内循环。<br/>
                 <strong>早期赞助：</strong> 基于 Beta 版的价值，引入 Sponsorship/Investment，覆盖核心建设者 <strong>~$2,500/mo</strong> 的基础薪酬。<br/>
                 让团队从“为爱发电”转为“专注构建”，为开放做准备。
               </p>
            </div>
            
            {/* Mobile View for Stage 2 Details */}
            <div className="md:hidden pl-16 mt-4">
               <div className="bg-emerald-900/10 p-4 rounded-xl border border-emerald-500/20">
                <ul className="space-y-2 text-xs text-neutral-300">
                  <li className="flex items-center justify-between"><span>Beta Loop</span> <span className="text-emerald-400 font-bold">Live</span></li>
                  <li className="flex items-center justify-between"><span>Sponsorship Goal</span> <span className="text-emerald-400 font-bold">$2,500/mo</span></li>
                </ul>
              </div>
            </div>
          </div>

          {/* STAGE 3 */}
          <div className="relative md:grid md:grid-cols-2 gap-12 items-center">
             <div className="hidden md:block text-right pr-12">
               <div className="inline-block px-3 py-1 bg-neutral-800 rounded text-xs text-neutral-500 mb-2">Mid-2026 & Beyond</div>
               <h2 className="text-3xl font-bold text-neutral-200">Stage 3: The Bloom</h2>
               <p className="text-emerald-600 font-medium mt-1">盛开与开放 (Announcement)</p>
               <p className="text-neutral-400 mt-4 leading-relaxed">
                 正式 Announcement。开放 Token 销售（限额白名单）。
                 门票收入与 Infra 挖矿形成正向飞轮。
                 实现真正的 Sustainability，接纳更多公共物品建设者。
               </p>
            </div>

            {/* Center Icon */}
            <div className="absolute left-0 md:left-1/2 w-12 h-12 -ml-0 md:-ml-6 flex items-center justify-center bg-neutral-800 border-2 border-neutral-600 rounded-full z-10">
              <Flower className="w-5 h-5 text-neutral-400" />
            </div>

            <div className="pl-16 md:pl-12 md:hidden">
              <div className="inline-block px-3 py-1 bg-neutral-800 rounded text-xs text-neutral-500 mb-2">Future</div>
              <h2 className="text-2xl font-bold text-white">Stage 3: The Bloom</h2>
              <p className="text-emerald-600 text-sm mb-3">盛开与开放</p>
               <p className="text-neutral-400 text-sm leading-relaxed">
                 正式 Announcement。白名单销售。生态自我造血。
               </p>
            </div>
            
            <div className="hidden md:block pl-12">
               <div className="bg-neutral-800/30 p-6 rounded-xl border border-neutral-800 border-dashed">
                <ul className="space-y-3 text-sm text-neutral-400">
                  <li className="flex items-center"><Users className="w-4 h-4 mr-3 text-neutral-500"/> Public Whitelist Sale</li>
                  <li className="flex items-center"><DollarSign className="w-4 h-4 mr-3 text-neutral-500"/> Sustainability Achieved</li>
                  <li className="flex items-center"><ArrowRight className="w-4 h-4 mr-3 text-neutral-500"/> Full Governance</li>
                </ul>
              </div>
            </div>
          </div>
        </div>
      </main>

      {/* Footer / Manifesto Statement */}
      <footer className="max-w-3xl mx-auto px-6 pb-20 text-center">
        <div className="p-8 bg-gradient-to-b from-neutral-800/50 to-neutral-900 rounded-2xl border border-neutral-800">
          <h3 className="text-xl font-bold text-white mb-4">Why Wait?</h3>
          <p className="text-neutral-400 italic mb-6">
            "We are not in a rush to sell tokens. We are in a rush to prove value."<br/>
            Stage 2 is about proving the loop works. Join us as a Patron.
          </p>
          <div className="flex justify-center gap-4">
             <button className="px-6 py-3 bg-neutral-800 hover:bg-neutral-700 text-white font-medium rounded-lg transition-colors duration-200 border border-neutral-700">
              Become a Patron (Stage 2)
            </button>
            <button className="px-6 py-3 bg-emerald-600 hover:bg-emerald-500 text-white font-medium rounded-lg transition-colors duration-200">
              Waitlist for Stage 3
            </button>
          </div>
        </div>
        <p className="mt-8 text-neutral-600 text-sm">© 2025 Public Goods Garden. Growing patiently.</p>
      </footer>
    </div>
  );
};

export default GrowthRoadmap;
```
