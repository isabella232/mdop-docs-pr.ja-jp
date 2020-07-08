---
title: MBAM クライアントをデスクトップまたはノート PC に展開する方法
description: MBAM クライアントをデスクトップまたはノート PC に展開する方法
author: dansimp
ms.assetid: f32927a2-4c05-4da8-acca-1108d1dfdb7e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ce4f8597cc182c037983a89efd60c5ef935712ce
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825544"
---
# MBAM クライアントをデスクトップまたはノート PC に展開する方法


Microsoft BitLocker 管理と監視 (MBAM) クライアントを使うと、管理者は企業内のコンピューター上の BitLocker ドライブ暗号化を強制および監視することができます。 MBAM クライアントは、Active Directory ドメインサービスなどのツール、または MicrosoftSystemCenter2012 ConfigurationManager などのエンタープライズソフトウェア展開ツールなどのツールを使用してクライアントを展開することで、組織に統合することができます。

**注** MBAM クライアントシステム要件を確認するには、「 [mbam 1.0 でサポートされている構成](mbam-10-supported-configurations.md)」を参照してください。

 

**デスクトップまたはラップトップコンピューターに MBAM クライアントを展開するには**

1.  MBAM ソフトウェアに付属の MBAM クライアントインストールファイルを見つけます。

2.  Active Directory ドメインサービス、または MicrosoftSystemCenter2012 ConfigurationManager などのエンタープライズソフトウェア展開ツールを使用して、ターゲットコンピューターに Windows インストーラーパッケージを展開します。

    **注** グループポリシーを使って Windows インストーラーパッケージを展開しないでください。

     

3.  MBAM クライアントインストールファイルを実行するように配布設定またはグループポリシーを構成します。 インストールが正常に完了すると、MBAM クライアントによって、ドメインコントローラーから受信したグループポリシー設定が適用され、BitLocker の暗号化と管理の機能が開始されます。 MBAM グループポリシー設定の詳細については、「 [mbam 1.0 グループポリシーの要件を計画する](planning-for-mbam-10-group-policy-requirements.md)」を参照してください。

    **重要** MBAM クライアントは、リモートデスクトッププロトコル接続がアクティブな場合は、BitLocker 暗号化アクションを開始しません。 BitLocker 暗号化を開始する前に、すべてのリモートコンソール接続を閉じる必要があります。

     

## 関連トピック


[MBAM 1.0 クライアントの展開](deploying-the-mbam-10-client.md)

 

 





