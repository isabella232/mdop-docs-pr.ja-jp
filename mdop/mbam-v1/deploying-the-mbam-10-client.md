---
title: MBAM 1.0 クライアントの展開
description: MBAM 1.0 クライアントの展開
author: dansimp
ms.assetid: f7ca233f-5035-4ff9-ab3a-f2453b4929d1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dee8c2f4a9b398c9f0797ada35e4c36610c755b1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822904"
---
# MBAM 1.0 クライアントの展開


Microsoft BitLocker 管理と監視 (MBAM) クライアントを使うと、管理者は企業内のコンピューター上の BitLocker ドライブ暗号化を強制および監視することができます。 BitLocker クライアントを組織に統合するには、Active Directory ドメインサービスなどのツールを使用してクライアントを展開するか、または最初のイメージングプロセスの一部としてクライアントコンピューターを直接暗号化します。

MBAM クライアントを展開するタイミングに応じて、組織内のコンピューター上で、またはエンドユーザーがコンピューターを受信した後に BitLocker 暗号化を有効にすることができます。 このタイミングを制御するには、グループポリシーを構成し、エンタープライズソフトウェア展開システムを使用して MBAM クライアントソフトウェアを展開します。

組織では、これらの方法のいずれかまたは両方を使用できます。 両方の方法を使用すると、コンプライアンス、レポート、キー回復のサポートが改善されます。

## デスクトップまたはノート pc に MBAM クライアントを展開する


グループポリシーを構成した後で、MBAM クライアントインストールの Windows インストーラーファイルをターゲットコンピューターに展開することができます。 これは、Microsoft System Center 2012 構成マネージャーまたは Active Directory ドメインサービスなどのエンタープライズソフトウェア展開システム製品を使用して行うことができます。 使用できる MBAM クライアントインストール用の2つの Windows インストーラーファイルは、MBAMClient-64bit.msi と MBAMClient-32bit.msi です。 これらのファイルは、MBAM ソフトウェアで提供されます。 MBAM グループポリシーオブジェクトの展開方法の詳細については、「 [mbam 1.0 グループポリシーオブジェクトの展開](deploying-mbam-10-group-policy-objects.md)」を参照してください。

[MBAM クライアントをデスクトップまたはノート PC に展開する方法](how-to-deploy-the-mbam-client-to-desktop-or-laptop-computers-mbam-1.md)

## Windows 展開の一部として MBAM クライアントを展開する


組織によっては、新しいコンピューターを1か所で受信して構成する場合があります。 この状況では、管理者は MBAM クライアントをインストールして、ユーザーデータがコンピューターに書き込まれる前に、各コンピューター上の BitLocker 暗号化を管理することができます。 この方法では、管理者がエンドユーザーの操作に依存せずに操作を実行するため、コンピューターが適切に暗号化されていることを確認することができます。 このシナリオを前提としているのは、組織のポリシーによって、コンピューターがユーザーに配信される前に企業の Windows イメージをインストールすることです。

[Windows 展開の一部として MBAM クライアントを展開する方法](how-to-deploy-the-mbam-client-as-part-of-a-windows-deployment-mbam-1.md)

## MBAM クライアントを展開するためのその他のリソース


[MBAM 1.0 の展開](deploying-mbam-10.md)

[MBAM 1.0 クライアントの展開計画](planning-for-mbam-10-client-deployment.md)

 

 





