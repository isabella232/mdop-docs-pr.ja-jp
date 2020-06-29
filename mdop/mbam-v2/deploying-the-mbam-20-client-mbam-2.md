---
title: MBAM 2.0 クライアントの展開
description: MBAM 2.0 クライアントの展開
author: dansimp
ms.assetid: 3dd584fe-2a54-40f0-9bab-13ea74040b01
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa42c8ab3adc273f0e00ba56a59f487deba89c6f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823447"
---
# MBAM 2.0 クライアントの展開


Microsoft BitLocker 管理と監視 (MBAM) クライアントを使うと、管理者は企業内のコンピューター上の BitLocker ドライブ暗号化を強制および監視することができます。 Active Directory ドメインサービスなどの電子ソフトウェア配布システムを通じてクライアントを展開するか、最初のイメージングプロセスの一部としてクライアントコンピューターを直接暗号化することによって、BitLocker クライアントを組織に統合することができます。

Microsoft BitLocker の管理と監視クライアントを展開するときには、組織内のコンピューターで BitLocker 暗号化を有効にするには、エンドユーザーがコンピューターを受信する前に、またはグループポリシーを構成し、エンタープライズソフトウェア展開システムを使って MBAM クライアントソフトウェアを展開する必要があります。

## デスクトップまたはノート Pc に MBAM クライアントを展開する


グループポリシーを構成した後、Microsoft System Center Configuration Manager 2012 または Active Directory ドメインサービスなどのエンタープライズソフトウェア展開システム製品を使用して、MBAM クライアントインストールの Windows インストーラーファイルをターゲットコンピューターに展開することができます。 クライアントを展開するには、32ビット版または64ビット版の MbamClientSetup.exe ファイル、または MBAM ソフトウェアで提供されている32ビットまたは64ビットの MBAMClient.msi ファイルを使用します。 MBAM グループポリシーオブジェクトの展開の詳細については、「 [mbam 2.0 グループポリシーオブジェクトの展開](deploying-mbam-20-group-policy-objects-mbam-2.md)」を参照してください。

[MBAM クライアントをデスクトップまたはノート PC に展開する方法](how-to-deploy-the-mbam-client-to-desktop-or-laptop-computers-mbam-2.md)

## Windows 展開の一部として MBAM クライアントを展開する


コンピューターが受信され、構成されている組織では、ユーザーデータが書き込まれる前に、各コンピューター上の BitLocker 暗号化を管理するために MBAM クライアントをインストールできます。 このプロセスの利点は、すべてのコンピューターが BitLocker 暗号化に準拠していることです。 この方法では、管理者がコンピューターを既に暗号化しているため、ユーザー操作に依存することはありません。 このシナリオを前提としているのは、組織のポリシーによって、コンピューターがユーザーに配信される前に企業の Windows イメージをインストールすることです。 グループポリシーが PIN を要求するように構成されている場合、ユーザーはグループポリシーを受信した後に PIN を設定するように求められます。

[Windows 展開の一部として MBAM クライアントを展開する方法](how-to-deploy-the-mbam-client-as-part-of-a-windows-deployment-mbam-2.md)

## コマンド ラインを使用して MBAM クライアントをインストールする方法


このセクションでは、コマンドラインを使用して MBAM クライアントをインストールする方法について説明します。

[コマンド ラインを使用して MBAM クライアントをインストールする方法](how-to-use-a-command-line-to-install-the-mbam-client.md)

## MBAM クライアントを展開するためのその他のリソース


[Mbam 2.0 を展開](deploying-mbam-20-mbam-2.md)[する Mbam 2.0 クライアント展開の計画](planning-for-mbam-20-client-deployment-mbam-2.md)

 

 





