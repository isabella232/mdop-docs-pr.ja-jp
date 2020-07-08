---
title: MBAM 2.0 の高可用性
description: MBAM 2.0 の高可用性
author: dansimp
ms.assetid: 244ee013-9e2a-48d2-b842-4e10594fd74f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6482a099d96aee731f81368b8b787325e592c453
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824727"
---
# MBAM 2.0 の高可用性


このトピックでは、Microsoft BitLocker の管理と監視 (MBAM) の高可用性インストールに関する基本情報について説明します。 このバージョンの MBAM では、高可用性シナリオが完全にはサポートされていないため、ここでは説明しません。 関連するブログとフォーラムを検索することをお勧めします。ここでは、ユーザーが環境内で MBAM の高可用性を正しく設定した方法を説明しています。

## MBAM の高可用性シナリオ


Microsoft BitLocker の管理と監視は、フォールトトレラントとして設計されています。 サーバーが利用できなくなった場合、ユーザーは悪影響を受けないようにしてください。 たとえば、MBAM エージェントが MBAM web サーバーに接続できない場合、ユーザーに操作の確認を求めるメッセージは表示されません。

MBAM のインストールを計画する場合は、次の項目を考慮してください。これは、MBAM サービスの可用性に影響を与える可能性があります。

-   ドライブの暗号化と回復パスワード–回復パスワードを預託たりできない場合、クライアントコンピューターでは暗号化は開始されません。

-   コンプライアンスステータスデータアップロード–コンプライアンスステータスレポートサービスをホストしているサーバーが利用できない場合、コンプライアンスデータは最新のままになりません。

-   ヘルプデスクの回復キーアクセス-ヘルプデスクが MBAM データベース情報にアクセスできない場合、ヘルプデスクはユーザーに回復キーを提供できません。

-   レポートの可用性–コンプライアンスレポートおよび監査レポートをホストしているサーバーが利用できない場合、レポートは使用できません。

## <a href="" id="how-the-mbam-backup-uses-the-volume-shadow-copy-service--vss--"></a>MBAM バックアップがボリュームシャドウコピーサービス (VSS) を使用する方法


MBAM 2.0 は、Microsoft BitLocker 管理および管理ライターと呼ばれるボリュームシャドウコピーサービス (VSS) ライターを提供します。これにより、コンプライアンスと監査データベースおよび回復データベースのバックアップが容易になります。

MBAM Server Windows Installer は、MBAM VSS ライターを登録します。 VSS ライター登録中にエラーが発生すると、MBAM サーバーのインストールがロールバックされます。 コンプライアンスと監査データベースと回復データベースが異なるサーバーにインストールされているトポロジでは、MBAM VSS Writer の個別のインスタンスが各サーバーに登録されます。 MBAM VSS Writer は、SQL Server VSS Writer に依存しています。 SQL Server VSS Writer は、Microsoft SQL Server インストールの一部として登録されています。 VSS ライターを使用してバックアップを実行するすべてのバックアップテクノロジは、MBAM VSS ライターを検出できます。

## 関連トピック


[MBAM 2.0 の保守](maintaining-mbam-20-mbam-2.md)

 

 





