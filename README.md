# ListingGood 国内版 MCP

> 让亚马逊的 AI 主动推荐你的商品。Get recommended by Amazon's AI.

ListingGood 是国内面向亚马逊卖家的 AI 推荐引擎。本仓库是**国内版 MCP 服务**的接入说明，端点部署在国内（`listinggood.cn`，ICP 备案号 `沪ICP备2022034611号-2`），数据合规留境内。

## 一句话定位

卖家把商品信息交给 ListingGood，它会告诉你：你的 Listing 会不会被亚马逊的 AI 购物助手（Rufus / COSMO）推荐，哪里踩了合规红线，并帮你一键生成高转化文案、写申诉信、分析差评。

## 接入端点（国内版）

```
https://listinggood.cn/mcp
```

- 协议：MCP `streamable-http`（远程，粘贴即用）
- 鉴权：免费工具免 Key；付费工具使用在 [listinggood.cn/connect](https://listinggood.cn/connect) 获取的 API Key 作为 Bearer Token
- 官网：[https://listinggood.cn](https://listinggood.cn)　接入页：[https://listinggood.cn/connect](https://listinggood.cn/connect)

## 8 个工具

| 工具 | 计费 | 说明 |
|---|---|---|
| `ai_readiness_check` | 免费 | AI 推荐就绪度评分：Rufus / COSMO 会不会推荐你的商品 |
| `agent_ready_check` | 免费 | Agent-Ready 评分：任意平台（亚马逊 / Shopify / Walmart / TikTok）商品能否被 AI 购物代理读取、信任并下单 |
| `compliance_check` | 免费 | 发布前红线词 / 类目 / 知识产权风险快检 |
| `fill_from_sentence` | 免费 | 一句话口语化描述 → 结构化 Listing 字段 |
| `compliance_scan` | 2 星 | 15 年知识库深度合规审计（GPSR / 知识产权 / 类目） |
| `generate_listing` | 1 星 / 站点 | 多站点高转化标题 + 五点 + 描述（A9 / A10 算法） |
| `analyze_review` | 2 星 | 差评根因分析 + 品牌口吻回复 |
| `generate_poa` | 4 星 | 亚马逊违规通知 → 可直接提交的 POA 申诉信 |

> 计费单位「星」：注册即送 10 星入永久钱包；主生成 1 星，合规深度扫描 / 差评分析 2 星，POA 申诉 4 星。

## 使用示例

**示例 1（免费）**

调用 `ai_readiness_check`，传入标题「真无线蓝牙耳机 40 小时续航 IPX7 防水」→ 返回 `score 94 / grade A` + 中文优化建议。

**示例 2（付费）**

调用 `generate_listing`（marketplace=US）→ 返回美国站标题 + 五点 + 描述。

## 接入步骤

1. 打开 [listinggood.cn/connect](https://listinggood.cn/connect)，按平台（千问办公 / WorkBuddy / 豆包 / Claude / Cursor）复制对应接入方式。
2. 在客户端里填入端点 `https://listinggood.cn/mcp` 与你的 API Key（免费工具无需 Key）。
3. 直接对话式调用 8 个工具即可。

## 红线

- 国内平台统一使用 `listinggood.cn/mcp`，不切换 `.com`。
- 工具描述与计费口径全平台一致，详见《ListingGood 国内推广执行流程 · 渠道作战图》。

© ListingGood · 上海得服科技有限公司（国内运营主体）
