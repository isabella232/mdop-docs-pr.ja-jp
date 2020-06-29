---
title: MBAM クライアントをデスクトップまたはノート PC に展開する方法
description: MBAM クライアントをデスクトップまたはノート PC に展開する方法
author: dansimp
ms.assetid: 3a7639e0-468e-4496-8be2-ed29b8e07c53
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6b67533a555da4dabec6654ed3f95f91ad8d37bf
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824477"
---
# MBAM クライアントをデスクトップまたはノート PC に展開する方法


このトピックでは、エンドユーザーのコンピューターに MBAM クライアントを展開する方法について説明します。 MBAM クライアントは、Active Directory ドメインサービスや MicrosoftSystemCenterConfiguration Manager などの電子ソフトウェア配布システムを通じて展開できます。

Windows 展開の一環として MBAM クライアントを展開する方法については、「 [Windows 展開の一部として MBAM を使用して BitLocker を有効にする方法](how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25.md)」を参照してください。

MBAM クライアントの展開を開始する前に、 [mbam 2.5 でサポートされている構成](mbam-25-supported-configurations.md)を確認してください。

**デスクトップまたはラップトップコンピューターに MBAM クライアントを展開するには**

1.  MBAM ソフトウェアに付属の MBAM クライアントインストールファイルを見つけます。

2.  Active Directory ドメインサービス、または MicrosoftSystemCenterConfiguration Manager などのエンタープライズソフトウェア展開ツールを使用して、Windows インストーラーパッケージをターゲットコンピューターに展開します。

3.  MBAM クライアントインストールファイルを実行するように、配布設定またはグループポリシー設定を構成します。

    インストールが正常に完了すると、MBAM クライアントは、BitLocker ドライブの暗号化と管理機能を開始するために、ドメインコントローラーから受信したグループポリシー設定を適用します。

    **重要** MBAM クライアントは、リモートデスクトッププロトコル接続がアクティブな場合は、BitLocker ドライブ暗号化アクションを開始しません。 すべてのリモートコンソール接続を閉じる必要があります。ユーザーは、BitLocker ドライブ暗号化が開始される前に、物理コンソールセッションにログオンしている必要があります。

     


## 関連トピック
[MBAM 2.5 クライアントの展開](deploying-the-mbam-25-client.md)

[MBAM 2.5 クライアントの展開計画](planning-for-mbam-25-client-deployment.md)

 

## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。 





