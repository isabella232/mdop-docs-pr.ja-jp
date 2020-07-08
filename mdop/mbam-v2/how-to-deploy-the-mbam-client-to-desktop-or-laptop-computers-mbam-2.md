---
title: MBAM クライアントをデスクトップまたはノート PC に展開する方法
description: MBAM クライアントをデスクトップまたはノート PC に展開する方法
author: dansimp
ms.assetid: 56744922-bfdd-48f6-ae01-645ff53b64a8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 49340ae970dafc9d263f5564e7981a402da40f19
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813010"
---
# MBAM クライアントをデスクトップまたはノート PC に展開する方法


Microsoft BitLocker 管理と監視 (MBAM) クライアントを使うと、管理者は企業内のコンピューター上の BitLocker ドライブ暗号化を強制および監視することができます。 Active Directory ドメインサービスや MicrosoftSystemCenterConfigurationManager などの電子ソフトウェア配布システムを使用してクライアントを展開することによって、BitLocker クライアントを組織に統合することができます。

**注** Microsoft BitLocker 管理およびクライアントシステム要件の監視については、「 [Mbam 2.0 でサポートされている構成](mbam-20-supported-configurations-mbam-2.md)」を参照してください。

 

**デスクトップまたはラップトップコンピューターに MBAM クライアントを展開するには**

1.  MBAM ソフトウェアに付属の MBAM クライアントインストールファイルを見つけます。

2.  Active Directory ドメインサービス、または MicrosoftSystemCenterConfigurationManager などのエンタープライズソフトウェア展開ツールを使用して、Windows インストーラーパッケージをターゲットコンピューターに展開します。

3.  MBAM クライアントインストールファイルを実行するように配布設定またはグループポリシーを構成します。 インストールが正常に完了すると、MBAM クライアントによって、ドメインコントローラーから受信したグループポリシー設定が適用され、BitLocker の暗号化と管理の機能が開始されます。 MBAM グループポリシー設定の詳細については、「 [mbam 2.0 グループポリシーの要件を計画する](planning-for-mbam-20-group-policy-requirements-mbam-2.md)」を参照してください。

    **重要** MBAM クライアントは、リモートデスクトッププロトコル接続がアクティブな場合は、BitLocker 暗号化アクションを開始しません。 BitLocker 暗号化を開始する前に、すべてのリモートコンソール接続を閉じる必要があります。

     

## 関連トピック


[MBAM 2.0 クライアントの展開](deploying-the-mbam-20-client-mbam-2.md)

 

 





