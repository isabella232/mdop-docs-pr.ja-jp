---
title: Microsoft BitLocker Administration and Monitoring 2.5
description: Microsoft BitLocker Administration and Monitoring 2.5
author: dansimp
ms.assetid: fd81d7de-b166-47e8-b6c7-d984830762b6
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/19/2017
ms.openlocfilehash: 2e5243131853207f0ed3cbb6d0cd8fb8e3d56108
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10795696"
---
# Microsoft BitLocker Administration and Monitoring 2.5

Microsoft BitLocker の管理と監視 (MBAM) 2.5 は、BitLocker ドライブの暗号化を管理するために使用できる簡素化された管理インターフェイスを提供します。 MBAM グループポリシーテンプレートを構成して、組織に適した BitLocker ドライブ暗号化ポリシーオプションを設定し、それらを使用して、それらのポリシーに対するクライアントのコンプライアンスを監視することができます。 また、個々のコンピューターと企業全体の暗号化の状態について報告することもできます。 さらに、ユーザーが PIN またはパスワードを忘れた場合や、BIOS またはブートレコードが変更された場合に、回復キーの情報にアクセスできます。 MBAM の詳しい説明については、「 [mbam 2.5 につい](about-mbam-25.md)て」を参照してください。

MBAM の入手方法については、「 [MDOP の入手方法](https://docs.microsoft.com/microsoft-desktop-optimization-pack/index#how-to-get-mdop)」を参照してください。

## 概要

- <a href="" id="getting-started-with-mbam-2-5"></a>[MBAM 2.5 をお使いになる前に](getting-started-with-mbam-25.md)
  - [MBAM 2.5 の概要](about-mbam-25.md)
  - [MBAM 2.5 のリリース ノート](release-notes-for-mbam-25.md)
  - [MBAM 2.5 SP1 の概要](about-mbam-25-sp1.md)
  - [MBAM 2.5 SP1 のリリース ノート](release-notes-for-mbam-25-sp1.md)
  - [テスト環境での MBAM 2.5 の評価](evaluating-mbam-25-in-a-test-environment.md)
  - [MBAM 2.5 のアーキテクチャの概要](high-level-architecture-for-mbam-25.md)
  - [MBAM 2.5 のアクセシビリティ](accessibility-for-mbam-25.md)
- <a href="" id="planning-for-mbam-2-5"></a>[MBAM 2.5 の計画](planning-for-mbam-25.md)
  - [MBAM 2.5 に対応する環境の準備](preparing-your-environment-for-mbam-25.md)
  - [MBAM 2.5 展開の前提条件](mbam-25-deployment-prerequisites.md)
  - [MBAM 2.5 グループ ポリシー要件の計画](planning-for-mbam-25-group-policy-requirements.md)
  - [MBAM 2.5 グループとアカウントの計画](planning-for-mbam-25-groups-and-accounts.md)
  - [MBAM Web サイトをセキュリティで保護する方法の計画](planning-how-to-secure-the-mbam-websites.md)
  - [MBAM 2.5 の展開計画](planning-to-deploy-mbam-25.md)
  - [MBAM 2.5 がサポートされる構成](mbam-25-supported-configurations.md)
  - [MBAM 2.5 の高可用性のための計画](planning-for-mbam-25-high-availability.md)
  - [MBAM 2.5 のセキュリティに関する考慮事項](mbam-25-security-considerations.md)
  - [MBAM 2.5 の計画チェックリスト](mbam-25-planning-checklist.md)
- <a href="" id="deploying-mbam-2-5"></a>[MBAM 2.5 の展開](deploying-mbam-25.md)
  - [MBAM 2.5 サーバー インフラストラクチャの展開](deploying-the-mbam-25-server-infrastructure.md)
  - [MBAM 2.5 グループ ポリシー オブジェクトの展開](deploying-mbam-25-group-policy-objects.md)
  - [MBAM 2.5 クライアントの展開](deploying-the-mbam-25-client.md)
  - [MBAM 2.5 の展開チェックリスト](mbam-25-deployment-checklist.md)
  - [以前のバージョンから MBAM 2.5 または MBAM 2.5 SP1 へのアップグレード](upgrading-to-mbam-25-or-mbam-25-sp1-from-previous-versions.md)
  - [MBAM サーバーの機能またはソフトウェアの削除](removing-mbam-server-features-or-software.md)
- <a href="" id="operations-for-mbam-2-5"></a>[MBAM 2.5 の操作](operations-for-mbam-25.md)
  - [MBAM 2.5 機能の管理](administering-mbam-25-features.md)
  - [MBAM 2.5 での BitLocker 準拠の監視とレポート](monitoring-and-reporting-bitlocker-compliance-with-mbam-25.md)
  - [MBAM 2.5 での BitLocker 管理の実行](performing-bitlocker-management-with-mbam-25.md)
  - [MBAM 2.5 の保守](maintaining-mbam-25.md)
  - [Windows PowerShell を使用した MBAM 2.5 の管理](using-windows-powershell-to-administer-mbam-25.md)
- <a href="" id="troubleshooting-mbam-2-5"></a>[MBAM 2.5 のトラブルシューティング](troubleshooting-mbam-25.md)
- <a href="" id="technical-reference-for-mbam-2-5"></a>[MBAM 2.5 テクニカル リファレンス](technical-reference-for-mbam-25.md)
  - [クライアントのイベント ログ](client-event-logs.md)
  - [サーバーのイベント ログ](server-event-logs.md)

## 詳細情報

- [MDOP 情報の操作](index.md)

  MDOP テクノロジについては、ドキュメント、ビデオ、およびその他のリソースを参照してください。

- [MBAM 展開ガイド](https://www.microsoft.com/download/details.aspx?id=38398)

  各方法のステップバイステップの手順など、MBAM の展開方法を選択する方法については、こちらを参照してください。
    
- [MBAM 2.5 SP1 サーバーに修正プログラムを適用する](apply-hotfix-for-mbam-25-sp1.md)

  MBAM 2.5 SP1 サーバーホットフィックスの適用方法のガイド
