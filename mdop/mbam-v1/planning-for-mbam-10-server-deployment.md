---
title: MBAM 1.0 サーバーの展開計画
description: MBAM 1.0 サーバーの展開計画
author: dansimp
ms.assetid: 3cbef284-3092-4c42-9234-2826b18ddef1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 76ff9c444ce3f9c39161341610fb0cd9a763dc6d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812427"
---
# MBAM 1.0 サーバーの展開計画


Microsoft BitLocker の管理と監視 (MBAM) サーバーインフラストラクチャは、企業の要件に基づいて1つまたは複数のサーバーコンピューターにインストールできるサーバー機能のセットによって異なります。

## MBAM サーバー展開の計画


次の MBAM 機能は、MBAM サーバー展開のサーバーインフラストラクチャを表しています。

-   回復とハードウェアデータベース

-   コンプライアンスと監査データベース

-   コンプライアンスと監査レポート

-   管理と監視サーバー

MBAM server データベースと機能は、スケーラビリティのニーズに応じて、さまざまな構成でインストールできます。 すべての MBAM Server 機能は1台のサーバーにインストールすることも、複数のサーバーに分散することもできます。 通常、運用環境では、3台のサーバーまたは5サーバーの構成を使用することをお勧めしますが、コンピューティングのニーズに応じて、2つまたは4つのサーバーの構成も使うことができます。

**注** MBAM と推奨される展開トポロジのパフォーマンスのスケーラビリティの詳細については、「MBAM スケーラビリティと高可用性ガイド」を参照してください <https://go.microsoft.com/fwlink/p/?LinkId=258314> 。

 

各 MBAM 機能には、特定の前提条件があります。 サーバー機能の前提条件とハードウェアとソフトウェアの要件の一覧については、「 [mbam 1.0 の展開に関する前提条件](mbam-10-deployment-prerequisites.md)と[Mbam 1.0 でサポートされている構成](mbam-10-supported-configurations.md)」を参照してください。

サーバー関連の MBAM 機能に加えて、サーバーセットアップアプリケーションには MBAM グループポリシーテンプレートが含まれています。 このテンプレートは、グループポリシー管理コンソール (GPMC) または高度なグループポリシー管理 (AGPM) を実行できる任意のコンピューターにインストールできます。

## MBAM Server 機能の展開の順序


MBAM Server 機能を展開する場合は、次の順序で機能をインストールします。

1.  回復とハードウェアデータベース

2.  コンプライアンスと監査データベース

3.  コンプライアンス監査とレポート

4.  管理と監視サーバー

5.  ポリシーテンプレート

**注** 各機能をインストールするコンピューターの名前を把握しておきます。 この情報は、インストールプロセス全体で使用されます。 インストールプロセスを支援するために、展開チェックリストを印刷して使用することができます。 MBAM 展開チェックリストの詳細については、「 [mbam 1.0 の展開チェックリスト](mbam-10-deployment-checklist.md)」を参照してください。

 

## 関連トピック


[MBAM 1.0 の展開計画](planning-to-deploy-mbam-10.md)

[MBAM 1.0 サーバー インフラストラクチャの展開](deploying-the-mbam-10-server-infrastructure.md)

 

 





