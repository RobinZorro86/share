# 设计方案 — Google vs Meta：珠宝独立站先投谁（学习版）

来源：Gemini 4 Neon 深度研究《美区饰品DTC广告渠道对比》（Google Docs，约2.9万字、3张表），全文存档 ~/workspace/docs/gemini4neon-google-vs-meta-jewelry-full.txt

## 任务定位
- 读者：Robin（非投手出身，要学懂、能拍板）
- 任务：把2.9万字研究报告压成一节45分钟能读完的课；读完能回答「ARIELLE.R（AOV约$180）先投谁、预算怎么分、什么数字算及格」
- 语言：中文讲解（Robin定版偏好），术语首次出现给人话翻译

## 内容结构（六课 + 附录）
0. 一页结论（先给答案）
1. 先分清两种生意：人找货 vs 货找人（底层逻辑）
2. 2026年变了什么：四大变量（Amazon退出Shopping / Meta CPM四年新高+Reels便宜 / Andromeda创意为王 / 像素限流+GMC封号红线）
3. 算账课：三档客单价盈亏平衡模拟表做成可视化横条——同档位 Google Shopping CPA vs Meta CPA vs 盈亏线，一眼看出谁在水上谁在水下；配交互计算器（AOV+毛利率滑杆→BE CPA/BE ROAS，并标注ARIELLE.R $180档落点）
4. 别人怎么打赢的：Mejuri/Ana Luisa（Meta创意序列）、The Art of Jewels/NYC Luxury（Google收割）、House of Harlow/UM（小预算扭亏）、Brilliant Earth反面教材
5. 别被后台ROAS骗了：光环效应 + 三层仪表盘（MER/CM3 → NC-ROAS → 平台内指标）
6. 落地路线图：上线前14天清单 + 三档预算配比表 + 全年四大节点日历 + 对ARIELLE.R的一页裁定
附录：名词速查（人话版）+ 原文要点索引/来源说明 + 口径提醒（模拟测算≠实测、代理商案例为成功样本）

## 视觉系统
- 延续 fb-ads-study 的 ARIELLE.R 世界（读者已熟悉，降低学习成本）：深海军蓝 #0F2340 / 珍珠白 #FAF7F2 / 香槟金 #C6A15B；Google 用蓝 #2B6CB0、Meta 用紫蓝 #7C5CFC 作渠道色，全页一致编码
- 字体：标题 Noto Serif SC（衬线）、正文 Noto Sans SC；数字 tabular
- 记忆点：第三课的「水位图」——每档一条盈亏线，渠道CPA做横条，线左边赚钱右边亏钱；纯CSS/JS实现，移动端横条全宽堆叠
- 配图：hero 珍珠静物（深蓝绸缎）、内文真人叠戴图（Reels种草语境）；其余靠图表，不堆装饰图
- 布局：单栏阅读流 max-width 760px，课与课之间用渠道色细线分隔；移动端表格转卡片堆叠、计算器滑杆全宽

## 自查
- 构建后 CDP 截 390 / 1280 全页图逐段看，重点查：水位图标签不折行溢出、表格卡片化、计算器滑杆可用
- 发布 share.qidi.jp/google-vs-meta-jewelry/ + 首页索引置顶加 NEW（摘掉 fb-ads-study 的 NEW）+ og.jpg 1200×630
- 交付时请 Robin 0–5 评分并登记评分表
