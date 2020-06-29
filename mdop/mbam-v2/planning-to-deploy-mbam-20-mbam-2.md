---
title: MBAM 2.0 の展開計画
description: MBAM 2.0 の展開計画
author: dansimp
ms.assetid: 2dc05fcd-aed9-4315-aeaf-92aaa9e0e955
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c7f065e52655212261dfe8b6b3f081f697142473
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825634"
---
# MBAM 2.0 の展開計画


Microsoft BitLocker の管理と監視 (MBAM) の展開計画を作成する前に、さまざまな展開構成と前提条件について検討する必要があります。 このセクションには、お客様のビジネス要件に最適な展開計画を策定するために必要な情報を収集するために役立つ情報が記載されています。 Configuration Manager トポロジを使用して MBAM をインストールする場合は、「 [Configuration manager で MBAM を展開する](planning-to-deploy-mbam-with-configuration-manager-2.md)場合の計画」を参照してください。

## MBAM 2.0 でサポートされている構成を確認する


MBAM サーバーとクライアントの機能をインストールするためのコンピューティング環境を準備したら、MBAM をインストールするコンピューターがハードウェアとオペレーティングシステムの最小要件を満たしていることを確認してください。 MBAM の展開の前提条件の詳細については、「 [mbam 2.0 の展開の前提条件](mbam-20-deployment-prerequisites-mbam-2.md)」を参照してください。

[MBAM 2.0 がサポートされる構成](mbam-20-supported-configurations-mbam-2.md)

## MBAM 2.0 サーバーとクライアントの展開を計画する


MBAM サーバーインフラストラクチャは、企業の要件に基づいて1つまたは複数のサーバーコンピューターにインストールできるサーバー機能のセットによって異なります。 これらの機能は、複数のサーバー間で分散された構成でインストールできます。

**注** 1つのサーバーに MBAM をインストールするのは、ラボ環境の場合のみにすることをお勧めします。

 

MBAM クライアントを使うと、管理者は企業内のコンピューター上の BitLocker ドライブ暗号化を強制および監視することができます。 エンタープライズソフトウェア配信システムを通じてクライアントを展開するか、最初のイメージングプロセスの一部としてクライアントコンピューターにクライアントエージェントをインストールすることによって、BitLocker クライアントを組織に統合することができます。

MBAM では、エンドユーザーがコンピューターを受け取る前、またはグループポリシーを使用する前に、組織内のコンピューターを暗号化することができます。

[MBAM 2.0 サーバーの展開計画](planning-for-mbam-20-server-deployment-mbam-2.md)

[MBAM 2.0 クライアントの展開計画](planning-for-mbam-20-client-deployment-mbam-2.md)

## <a href="" id="other-resources-for-mbam-planning-"></a>MBAM の計画に関するその他のリソース


[MBAM 2.0 の計画](planning-for-mbam-20-mbam-2.md)

 

 





