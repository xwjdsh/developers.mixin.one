---
title: 多重签名
---

多重签名是一项安全、可靠、有效的实用技术，可以有效提升托管资产安全性，增强客户信任度。Mixin 主网底层支持基于 ed25519 的多重签名（简称“多签”），可任意设置 t/M 参与多签，其中 t 是 threshold，M 是 members，M 最多支持 255 人参与多签。例如 `2/3` 多签表示有三人一起共同管理资产，要动用资产需要任意 2 人签名交易才会生效。

与比特币 `3` 开头的多签地址不同，Mixin 的多签基于 UTXO 但没有统一的多签地址，实际上是将一笔转账转给了多个人，转账需要指定一组收款人和 threshold 阈值，这笔资产归所有参与多签方共有，同一个用户可以同时参与到不同的多签组之中。为了方便说明下文仍然使用 `多签账户` 来代表多人共同管理的加密资产。

## 管理资产

多人共同管理资产是多重签名技术主要的应用场景之一，每笔资金动用都需要多人有效签名才能使用，任何一个人无法直接动用资产，同时也能很好的避免单点故障导致资产丢失甚至无法找回的问题。

- Mixin 团队开发的简易多签机器人 7000102367 拉个群就能使用，纯前端且开源 <https://github.com/MixinNetwork/multisig-bot>
- Pando 团队开发的 CoWallet 7000103970 也是一个多币种多签钱包，使用简单界面设计友好，并且开源 <https://github.com/fox-one/cowallet>

## 电子商务

电商行业中较常使用 2/3 多签，买家、卖家和平台作为多签参与方，买家先将资金转入多签账户，后续交易确认、退款等流程买卖双方确认即可，产生纠纷时由平台做 2/3 仲裁。电商平台通过实现多签有效的约束了双方的诚信交易行为，降低了交易风险同时提高了效率。

- ExinLocal 7000000015 是一个基于 Mixin Network 的全球买卖加密货币的点对点交易市场，成功将多重签名技术应用到点对点 OTC 交易市场，用户可以在这个平台自由、安全的交换资产，[了解更多](https://w3c.group/c/1581684681212744)。

## 电子政务

多重签名技术还能运用于逐层审批的电子政务系统，将多签转账与审批流程、电子合同进行关联，流程参与者逐层签名交易直至电子签名最终生效并且上链存证。例如设置一个 4/4 的财务支出审批流程，参与者分别是营销人员、部门领导、财务、出纳，由营销人员发起并参与多签，部门领导、财务和出纳依次审核和签名后可实现自动放款并且整个流程自动记录上链。

## 共识达成

Mixin 首次将多重签名技术应用于区块链的共识达成，据此可实现可无限扩张的分片网络，每一个参与多重签名的节点都运行同一份代码，存相同的数据，例如基于 Mixin Network 的公链、去中心化交易所、AMM、去中心化借贷等去中心化应用程序。

- 4swap 7000103537 是一个去中心化提供自动化做市商的交易所，由 Fox 团队研发，Mixin Core、币印、BigONE、Fox、BOX 社区共同管理资产和运营。

## 了解更多

- [去中心化应用程序的解决方案 MTG](../mtg/overview)

  MTG 是分片技术的最佳实践，每个 MTG 实践都是一个 Mixin Network 的平行链，由多个独立节点组成，通过 Mixin 主网的多重签名技术达成共识。

- [多重签名 API 文档](/api/multisigs/outputs)

  了解如何使用多重签名 API。
