---
title: MBAM 1.0 の展開計画
description: MBAM 1.0 の展開計画
author: dansimp
ms.assetid: 30ad4304-45c6-427d-8e33-ebe8053c7871
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c2ff25e705717db5086150ed08a5640335bbacb8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823187"
---
# MBAM 1.0 の展開計画


Microsoft BitLocker の管理と監視 (MBAM) 1.0 展開計画を作成する前に、さまざまな展開構成と前提条件について検討する必要があります。 このセクションには、お客様のビジネス要件を満たす展開計画を策定するために必要な情報を収集するために役立つ情報が記載されています。

## MBAM 1.0 でサポートされている構成を確認する


MBAM クライアントとサーバー機能のインストールのためにコンピューティング環境を準備したら、mbam のサポートされている構成情報を確認して、MBAM をインストールするコンピューターがハードウェアとオペレーティングシステムの最小要件を満たしていることを確認してください。 MBAM の展開の前提条件の詳細については、「 [mbam 1.0 の展開の前提条件](mbam-10-deployment-prerequisites.md)」を参照してください。

[MBAM 1.0 がサポートされる構成](mbam-10-supported-configurations.md)

## MBAM 1.0 サーバーとクライアントの展開を計画する


MBAM サーバーインフラストラクチャは、企業の要件に基づいて1つまたは複数のサーバーコンピューターにインストールできるサーバー機能のセットによって異なります。 これらの機能は1台のサーバーにインストールすることも、複数のサーバーに分散することもできます。

MBAM クライアントでは、管理者が企業内のコンピューター上の BitLocker ドライブ暗号化を強制および監視することができます。 BitLocker クライアントを組織に統合するには、Active Directory ドメインサービスなどのツールを使用してクライアントを展開するか、または最初のイメージングプロセスの一部としてクライアントコンピューターを直接暗号化します。

MBAM では、エンドユーザーがコンピューターを受け取る前または後にグループポリシーを使って、組織内のコンピューターを暗号化することができます。 組織内の一方または両方の方法を使用することができます。 両方の方法を選択すると、コンプライアンス、レポート、キー回復のサポートが改善されます。

[MBAM 1.0 サーバーの展開計画](planning-for-mbam-10-server-deployment.md)

[MBAM 1.0 クライアントの展開計画](planning-for-mbam-10-client-deployment.md)

## <a href="" id="other-resources-for-mbam-planning-"></a>MBAM の計画に関するその他のリソース


-   [MBAM 1.0 の計画](planning-for-mbam-10.md)

 

 





