---
title: MBAM 1.0 の高可用性
description: MBAM 1.0 の高可用性
author: dansimp
ms.assetid: 5869ecf8-1056-4c32-aecb-838a37e05d39
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 1227967d647cbfbc16967b5936066fd73d2412e2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825364"
---
# MBAM 1.0 の高可用性


このトピックでは、Microsoft BitLocker の管理と監視 (MBAM) の可用性の高いインストールを構成する方法について説明します。

## MBAM の高可用性シナリオ


Microsoft BitLocker の管理と監視 (MBAM) は、フォールトトレラントとして設計されています。 サーバーが利用できなくなった場合は、ユーザーに悪影響を与えないようにしてください。 たとえば、MBAM エージェントが MBAM web サーバーに接続できない場合、ユーザーに操作の確認を求めるメッセージは表示されません。

MBAM のインストールを計画する場合は、MBAM サービスの可用性に影響を与える可能性のある次の事項を考慮してください。

-   ドライブの暗号化と回復パスワード–回復パスワードを預託たりできない場合、クライアントコンピューターでは暗号化が開始されません。

-   コンプライアンスステータスデータアップロード–コンプライアンスステータスレポートサービスをホストしているサーバーが利用できない場合は、コンプライアンスデータは最新のままになりません。

-   ヘルプデスク回復キーアクセス-ヘルプデスクが MBAM データベース情報にアクセスできない場合、ユーザーに回復キーを提供することはできません。

-   レポートの可用性–コンプライアンスと監査レポートをホストしているサーバーが使用できない場合、レポートは使用できません。

MBAM 高可用性の主な懸念は、BitLocker キー復元の可用性です。 ヘルプデスクが回復キーを提供できない場合、ロックされているユーザーはコンピューターのロックを解除できません。 この問題を回避するには、高可用性を確保するために、冗長な web サーバーとデータベースを実装することを検討してください。

MBAM スケーラビリティと高可用性の詳細については、「 [Mbam スケーラビリティーのホワイトペーパー](https://go.microsoft.com/fwlink/p/?LinkId=229025) (」を参照してください https://go.microsoft.com/fwlink/p/?LinkId=229025) 。

Microsoft SQL Server の高可用性の一般的なガイダンスについては、「[高可用性](https://go.microsoft.com/fwlink/p/?LinkId=221504)()」を参照してください https://go.microsoft.com/fwlink/p/?LinkId=221504) 。

Web サーバーの可用性とスケーラビリティに関する一般的なガイダンスについては、「[可用性とスケーラビリティ](https://go.microsoft.com/fwlink/p/?LinkId=221503)(」を参照してください https://go.microsoft.com/fwlink/p/?LinkId=221503) 。

## 関連トピック


[MBAM 1.0 の保守](maintaining-mbam-10.md)

 

 





