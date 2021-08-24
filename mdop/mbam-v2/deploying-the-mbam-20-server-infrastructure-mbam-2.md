---
title: MBAM 2.0 サーバー インフラストラクチャの展開
description: MBAM 2.0 サーバー インフラストラクチャの展開
author: dansimp
ms.assetid: 52e68d94-e2b4-4b06-ae55-f900ea6cc59f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8aee322b9a1aacbf98ff8362e95e21c2dd3d289a
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910802"
---
# <a name="deploying-the-mbam-20-server-infrastructure"></a>MBAM 2.0 サーバー インフラストラクチャの展開


スタンドアロン トポロジの Microsoft BitLocker Administration and Monitoring (MBAM) Server の機能は、実稼働環境の 2 つ以上のサーバーに異なる構成でインストールできます。 推奨される構成は、スケーラビリティ要件に応じて、実稼働環境用の 2 台のサーバーです。 テスト環境でのみ MBAM インストールに 1 台のサーバーを使用します。 MBAM Server 機能の展開の計画の詳細については [、「Planning for MBAM 2.0 Server Deployment」を参照してください](planning-for-mbam-20-server-deployment-mbam-2.md)。

次の図は、推奨される 2 サーバー MBAM 展開を構成する方法の例を示しています。 この構成は、実稼働環境で最大 200,000 MBAM のクライアントをサポートします。 アーキテクチャ イメージ内のサーバー機能とデータベースについては、次のセクションで説明し、コンピューターまたはサーバーの下に一覧表示され、インストールすることをお勧めします。

![mbam 2 2 サーバー展開トポロジ。](images/mbam2-3-servers.gif)

## <a name="administration-and-monitoring-server"></a>管理および監視サーバー


このサーバーには、次の機能がインストールされています。

-   **管理および監視サーバー**。 管理および監視サーバー機能は、Windows サーバーにインストールされ、ヘルプ デスク Web サイトと監視 Web サービスで構成されます。

-   **セルフサービス ポータル**。 ポータルSelf-ServiceサーバーにインストールWindowsされます。 この Self-Service ポータルを使用すると、クライアント コンピューター上のエンド ユーザーが Web サイトに個別にログオンし、ロックされた BitLocker ボリュームを回復する回復キーを取得できます。

## <a name="database-server"></a>データベース サーバー


このサーバーには、次の機能がインストールされています。

-   **回復データベース**. 回復データベースは、データベース サーバー WindowsサポートされているインスタンスにインストールMicrosoft SQL Server。 このデータベースには、MBAM クライアント コンピューターから収集された回復データが格納されます。

-   **コンプライアンスと監査データベース**. コンプライアンスデータベースと監査データベースは、WindowsサーバーとサポートされているインスタンスにインストールSQL Server。 このデータベースには、MBAM クライアント コンピューターのコンプライアンス データが格納されます。 このデータは、主に SSRS (SSRS) ホストSQL Server Reporting Servicesレポートに使用されます。

-   **コンプライアンスレポートと監査レポート**。 コンプライアンスレポートと監査レポートは、Windows サーバーにインストールされ、SQL Server (SSRS) 機能がインストールされている SQL Server Reporting Services のインスタンスにインストールされます。 これらのレポートは、ヘルプ デスク Web サイトから、または SSRS サーバーから直接アクセスできる MBAM レポートを提供します。

## <a name="management-workstation"></a>管理ワークステーション


管理ワークステーションには、次の機能がインストールされています。この機能には、サーバーまたはWindowsコンピューターを使用できます。

-   **ポリシー テンプレート**。 ポリシー テンプレートは、BitLocker ドライブ暗号化の MBAM 実装設定を定義するグループ ポリシーで構成されます。 ポリシー テンプレートは、任意のサーバーまたはワークステーションにインストールできますが、通常は管理ワークステーション (サーバーまたはクライアント コンピューターでサポートWindowsインストールされます。 ワークステーションは専用のコンピューターである必要はない。

## <a name="mbam-client"></a><a href="" id="---------mbam-client"></a> MBAM クライアント


MBAM クライアントは、コンピューターにインストールWindows次の特性があります。

-   グループ ポリシーを使用して、企業内のクライアント コンピューターの BitLocker ドライブ暗号化を強制します。

-   オペレーティング システム ドライブ、固定データ ドライブ、およびリムーバブル データ (USB) ドライブの 3 つの BitLocker データ ドライブの種類の回復キーを収集します。

-   コンピューターのコンプライアンス データを収集し、レポート システムにデータを渡します。

## <a name="other-resources-for-deploying-mbam-20-server-features"></a>MBAM 2.0 サーバー機能を展開するその他のリソース


[MBAM 2.0 の展開](deploying-mbam-20-mbam-2.md)

 

 





