---
title: MBAM 2.0 サーバーの展開計画
description: MBAM 2.0 サーバーの展開計画
author: dansimp
ms.assetid: b57f1a42-134f-4997-8697-7fbed08e2fc4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 57e6510556522dce029c958172bd89a361e06b83
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812611"
---
# MBAM 2.0 サーバーの展開計画


Microsoft BitLocker の管理と監視 (MBAM) サーバーインフラストラクチャは、企業の要件に基づいて1つまたは複数のサーバーコンピューターにインストールできるサーバー機能のセットによって異なります。 Configuration Manager トポロジを使用して Microsoft BitLocker の管理と監視をインストールする場合は、「 [Configuration manager を使用して MBAM を展開するための計画](planning-to-deploy-mbam-with-configuration-manager-2.md)」を参照してください。

**注** 1台のサーバーでの Microsoft BitLocker 管理と監視のインストールは、テスト環境でのみお勧めします。

 

## MBAM サーバー展開の計画


MBAM サーバー展開用のインフラストラクチャには、次の機能が含まれます。

-   回復用データベース

-   コンプライアンスと監査データベース

-   コンプライアンスと監査レポート

-   セルフサービスポータル

-   管理と監視サーバー

-   MBAM グループポリシーテンプレート

MBAM Server データベースと機能は、スケーラビリティ要件に応じて、さまざまな構成でインストールできます。 すべての MBAM Server 機能は1台のサーバーにインストールすることも、複数のサーバーに分散することもできます。 2 ~ 4 台のサーバーの構成をコンピューターの要件に応じて使うこともできますが、運用環境には 2 server 構成を使用することをお勧めします。

各 MBAM 機能には、特定の前提条件があります。 サーバー機能の前提条件とハードウェアとソフトウェアの要件の一覧については、「 [mbam 2.0 の展開に関する前提条件](mbam-20-deployment-prerequisites-mbam-2.md)と[Mbam 2.0 でサポートされている構成](mbam-20-supported-configurations-mbam-2.md)」を参照してください。

サーバー関連の MBAM 機能に加えて、サーバーセットアップアプリケーションには MBAM グループポリシーテンプレートが含まれています。 このテンプレートには、エンタープライズでの BitLocker ドライブ暗号化を管理するように構成したグループポリシーオブジェクト (GPO) の設定が含まれています。 このテンプレートは、グループポリシー管理コンソール (GPMC) または高度なグループポリシー管理 (AGPM) を実行できる任意のコンピューターにインストールできます。

MBAM サーバーの展開を計画するときには、MBAM の BitLocker 回復キーは1回だけ使用することをお勧めします。その後、回復キーの有効期限が切れます。 使用後にキーの有効期限が切れるようにするには、ヘルプデスクポータルまたはセルフサービスポータルを使用してキーを取得する必要があります。

## MBAM Server 機能の展開の順序


複数のサーバーに MBAM 機能を導入するには、次の順序で機能をインストールする必要があります。

1.  回復用データベース

2.  コンプライアンスと監査データベース

3.  コンプライアンス監査とレポート

4.  セルフサービスポータル

5.  管理と監視サーバー

6.  MBAM グループポリシーテンプレート

**注** 各機能をインストールするコンピューターの名前を把握しておきます。 この情報は、インストールプロセス全体で使用する必要があります。 この作業に役立てるために、展開チェックリストを印刷して使用することができます。 MBAM 展開チェックリストの詳細については、「 [mbam 2.0 の展開チェックリスト](mbam-20-deployment-checklist-mbam-2.md)」を参照してください。

 

## 関連トピック


[MBAM 2.0 の展開計画](planning-to-deploy-mbam-20-mbam-2.md)

[MBAM 2.0 サーバー インフラストラクチャの展開](deploying-the-mbam-20-server-infrastructure-mbam-2.md)

 

 





