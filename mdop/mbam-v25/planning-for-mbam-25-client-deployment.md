---
title: MBAM 2.5 クライアントの展開計画
description: MBAM 2.5 クライアントの展開計画
author: dansimp
ms.assetid: 23c89976-af24-4753-9412-ce0ea42d1964
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ff03b58da0985b2f57308c99a9bc15f4a0554623
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825994"
---
# MBAM 2.5 クライアントの展開計画


Microsoft BitLocker の管理と監視 (MBAM) クライアントソフトウェアを展開するときには、組織内のコンピューターで BitLocker ドライブの暗号化を有効にするには、エンドユーザーがコンピューターを受け取るか後で行う必要があります。 MBAM スタンドアロンと System Center Configuration Manager の統合トポロジのどちらの場合も、MBAM のグループポリシー設定を構成する必要があります。

MBAM スタンドアロントポロジを使用している場合は、エンタープライズソフトウェア展開システムを使用して、MBAM クライアントソフトウェアをエンドユーザーコンピューターに展開することをお勧めします。

Configuration Manager の統合トポロジで MBAM を展開する場合は、Configuration Manager を使用して、MBAM クライアントソフトウェアをエンドユーザーコンピューターに展開することができます。 Configuration Manager の MBAM インストールでは、MBAM で管理できるコンピューターのコレクションが作成されます。 このコレクションには、トラステッドプラットフォームモジュール (TPM) を持たないが、Windows 8、Windows 8.1、または Windows 10 を実行しているワークステーションとデバイスが含まれます。

**注** Configuration Manager 2007 を使用している場合、Configuration Manager 統合トポロジのインストールでは、Windows To Go はサポートされません。

 

## コンピューターの配布後のエンドユーザーへの BitLocker ドライブ暗号化を有効にするための MBAM クライアントの展開


グループポリシーを構成した後、Microsoft System Center Configuration Manager または Active Directory ドメインサービス (AD DS) などのエンタープライズソフトウェア展開システム製品を使用して、MBAM クライアントインストールの Windows Installer ファイルを展開して、コンピューターをターゲットにすることができます。 MBAM クライアントを展開するには、MBAM クライアントソフトウェアで提供される32ビットまたは64ビットの MbamClientSetup.exe ファイルまたは MBAMClient.msi ファイルのいずれかを使用できます。

**注** MBAM 2.5 SP1 以降、MBAM 製品には別の MSI が含まれなくなりました。 ただし、製品に含まれている実行可能ファイル (.exe) から MSI を抽出することはできます。

 

クライアントコンピューターにコンピューターを配布した後で MBAM クライアントを展開すると、エンドユーザーに対してコンピューターを暗号化するように求められます。 このアクションでは、MBAM がデータを収集できます。このデータには、PIN とパスワードが含まれます (ポリシーによって必要な場合)。その後、暗号化処理を開始します。

**注** この方法では、TPM チップを使用しているコンピューターを持つエンドユーザーは、チップがアクティブになっていない場合は、TPM チップをアクティブ化して初期化するように求められます。

 

## MBAM クライアントを使用して、コンピューターの配布がエンドユーザーになる前に BitLocker ドライブ暗号化を有効にする


コンピューターが受信され、構成されている組織で、コンピューターに準拠している TPM チップがある場合、MBAM クライアントを使用して、ユーザーデータが書き込まれる前に、各コンピューター上の BitLocker ドライブ暗号化を管理することができます。 このプロセスの利点は、すべてのコンピューターが準拠していることです。 この方法では、管理者がコンピューターを既に暗号化しているため、エンドユーザー操作に依存することはありません。 このシナリオの重要な前提として、組織のポリシーによって、コンピューターがエンドユーザーに配信される前に企業の Windows イメージがインストールされます。

組織で TPM チップを使用してコンピューターを暗号化する場合、管理者は、コンピューターのオペレーティングシステムボリュームを暗号化する TPM プロテクターを追加します。 組織で TPM チップと PIN の保護機能を使用する必要がある場合、管理者は TPM プロテクターを使ってオペレーティングシステムボリュームを暗号化した後、エンドユーザーが初めてログオンするときに PIN を選択します。 組織で PIN のプロテクターのみを使用することにした場合、管理者は最初にボリュームを暗号化する必要はありません。 エンドユーザーがログオンすると、Microsoft BitLocker の管理と監視で、PIN、または後でコンピューターを再起動するために使用する PIN とパスワードを入力するように求められます。

**注** TPM プロテクターオプションの場合、管理者は、コンピューターがエンドユーザーに配信される前に TPM をアクティブ化して初期化するために、BIOS プロンプトを受け入れる必要があります。

 

## 暗号化されたハードドライブ向け MBAM クライアントのサポート


MBAM は、Opal と IEEE 1667 標準の TCG 仕様要件を満たす、暗号化されたハードドライブ上の BitLocker をサポートしています。 これらのデバイスで BitLocker が有効になっている場合は、暗号化されたドライブでキーを生成し、管理機能を実行します。 詳細については、「[暗号化されたハードドライブ](https://technet.microsoft.com/library/hh831627.aspx)」を参照してください。


## 関連トピック


[MBAM 2.5 の展開計画](planning-to-deploy-mbam-25.md)

[MBAM 2.5 クライアントの展開](deploying-the-mbam-25-client.md)

 

 
## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。




