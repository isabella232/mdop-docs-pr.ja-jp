---
title: MBAM 2.5 クライアントの展開
description: MBAM 2.5 クライアントの展開
author: dansimp
ms.assetid: 0a96a0ee-f280-49d9-a244-88f4147fe9fd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 375af8966c8e66a58baec5065d065891187899fc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826277"
---
# MBAM 2.5 クライアントの展開


Microsoft BitLocker 管理と監視 (MBAM) クライアントソフトウェアを使用すると、管理者は企業内のコンピューターで BitLocker ドライブ暗号化を適用および監視することができます。 Active Directory ドメインサービスなどの電子ソフトウェア配布システムを通じてクライアントを展開するか、最初のイメージングプロセスの一部としてクライアントコンピューターを直接暗号化することによって、BitLocker クライアントを組織に統合することができます。

Microsoft BitLocker の管理と監視クライアントソフトウェアを展開するときには、組織内のコンピューターで BitLocker ドライブの暗号化を有効にすることができます。これは、エンドユーザーがコンピューターを受け取る前に、またはエンタープライズソフトウェア展開システムを使用して、グループポリシーを構成して、MBAM クライアントソフトウェアを展開することです。

## デスクトップまたはノート pc に MBAM クライアントを展開する


グループポリシー設定を構成したら、MicrosoftSystemCenter2012 ConfigurationManager や Active Directory ドメインサービスなどのエンタープライズソフトウェア展開システム製品を使用して、MBAM クライアントインストールの Windows インストーラーファイルをターゲットコンピューターに展開することができます。 MBAM クライアントソフトウェアで提供される、32ビットまたは64ビットの MbamClientSetup.exe ファイル、または32ビットまたは64ビットの MBAMClient.msi ファイルを使うことができます。 MBAM グループポリシー設定の展開の詳細については、「 [mbam 2.5 グループポリシーオブジェクトの展開](deploying-mbam-25-group-policy-objects.md)」を参照してください。

**注** MBAM 2.5 SP1 以降、MBAM 製品には別の MSI が含まれなくなりました。 ただし、製品に含まれている実行可能ファイル (.exe) から MSI を抽出することはできます。

 

[MBAM クライアントをデスクトップまたはノート PC に展開する方法](how-to-deploy-the-mbam-client-to-desktop-or-laptop-computers-mbam-25.md)

## Windows 展開の一部として MBAM クライアントを展開する


コンピューターが送受信され、集中して構成されている組織では、ユーザーデータが書き込まれる前に、各コンピューター上の BitLocker ドライブ暗号化を管理するために MBAM クライアントをインストールできます。 このプロセスの利点は、すべてのコンピューターが BitLocker ドライブ暗号化に準拠していることです。 この方法では、管理者がコンピューターを既に暗号化しているため、ユーザー操作に依存することはありません。 このシナリオを前提としているのは、組織のポリシーによって、コンピューターがユーザーに配信される前に企業の Windows イメージをインストールすることです。 グループポリシー設定が PIN を要求するように構成されている場合、ユーザーはポリシーを受信した後に PIN を設定するように求められます。

[Windows 展開の一部として MBAM を使用して BitLocker を有効にする方法](how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25.md)

## コマンドラインを使用して MBAM クライアントを展開する方法


このセクションでは、コマンドラインを使用して MBAM クライアントをインストールする方法について説明します。

[コマンド ラインを使用して MBAM クライアントを展開する方法](how-to-deploy-the-mbam-client-by-using-a-command-line.md)

## MBAM クライアントを展開するためのその他のリソース


[MBAM 2.5 の展開](deploying-mbam-25.md)



## 関連トピック


[MBAM 2.5 の展開](deploying-mbam-25.md)

[MBAM 2.5 の計画](planning-for-mbam-25.md)

 
## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。
 





