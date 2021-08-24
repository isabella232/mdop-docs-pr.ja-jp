---
title: MBAM 2.0 のアーキテクチャの概要
description: MBAM 2.0 のアーキテクチャの概要
author: dansimp
ms.assetid: 7f73dd3a-0b1f-4af6-a2f0-d0c5bc5d183a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f19480b5797362e6e4119fff9a14afd9d5a74d98
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910502"
---
# <a name="high-level-architecture-for-mbam-20"></a>MBAM 2.0 のアーキテクチャの概要


Microsoft BitLocker Administration and Monitoring (MBAM) は、BitLocker のプロビジョニングと展開を簡素化し、BitLocker でのコンプライアンスとレポート作成を改善し、サポート コストを削減するのに役立つクライアント/サーバー ソリューションです。 Microsoft BitLocker の管理と監視には、このトピックで説明されている機能が含まれています。

Microsoft BitLocker 管理と監視は、スタンドアロン トポロジ、または Microsoft System Center Configuration Manager 2007 または Microsoft System Center 2012 Configuration Manager と統合されたトポロジで展開できます。 このトピックでは、スタンドアロン トポロジのアーキテクチャについて説明します。 統合された Configuration Manager トポロジでの展開の詳細については [、「Using MBAM with Configuration Manager」を参照してください](using-mbam-with-configuration-manager.md)。

次の図は、2 台のサーバーと管理ワークステーションで構成される、実稼働環境の MBAM 推奨アーキテクチャを示しています。 このアーキテクチャは、最大 200,000 MBAM のクライアントをサポートします。 アーキテクチャ イメージ内のサーバー機能とデータベースについては、次のセクションで説明し、コンピューターまたはサーバーの下に一覧表示され、インストールすることをお勧めします。

**備考**  
単一サーバー アーキテクチャは、テスト環境でのみ使用する必要があります。

 

![mbam 2 2 サーバー展開トポロジ。](images/mbam2-3-servers.gif)

## <a name="administration-and-monitoring-server"></a>管理および監視サーバー


このサーバーには、次の機能がインストールされています。

-   **管理および監視サーバー**。 管理および監視サーバー機能は Windows サーバーにインストールされ、レポートとヘルプ デスク ポータル、および監視 Web サービスを含む管理および監視 Web サイトで構成されます。

-   **セルフサービス ポータル**。 ポータルSelf-ServiceサーバーにインストールWindowsされます。 この Self-Service ポータルを使用すると、クライアント コンピューター上のエンド ユーザーが Web サイトに個別にログオンし、ロックされた BitLocker ボリュームを回復する回復キーを取得できます。

## <a name="database-server"></a>データベース サーバー


このサーバーには、次の機能がインストールされています。

-   **回復データベース**. 回復データベースは、データベース サーバー WindowsサポートされているインスタンスにインストールMicrosoft SQL Server。 このデータベースには、MBAM クライアント コンピューターから収集された回復データが格納されます。

-   **コンプライアンスと監査データベース**. コンプライアンスデータベースと監査データベースは、WindowsサーバーとサポートされているインスタンスにインストールSQL Server。 このデータベースには、MBAM クライアント コンピューターのコンプライアンス データが格納されます。 このデータは、主に SSRS (SSRS) ホストSQL Server Reporting Servicesレポートに使用されます。

-   **コンプライアンスレポートと監査レポート**。 コンプライアンスレポートと監査レポートは、Windows サーバーにインストールされ、SQL Server (SSRS) 機能がインストールされている SQL Server Reporting Services のインスタンスにインストールされます。 これらのレポートは、管理および監視 Web サイトから、または SSRS サーバーから直接アクセスできる MBAM レポートを提供します。

## <a name="management-workstation"></a>管理ワークステーション


管理ワークステーションには、次の機能がインストールされています。この機能は、サーバーまたはWindowsコンピューターとして使用できます。

-   **ポリシー テンプレート**。 ポリシー テンプレートは、BitLocker ドライブ暗号化の MBAM 実装設定を定義するグループ ポリシー設定で構成されます。 ポリシー テンプレートは、任意のサーバーまたはワークステーションにインストールできますが、通常は管理ワークステーション (サーバーまたはクライアント コンピューターでサポートWindowsインストールされます。 ワークステーションは専用のコンピューターである必要はない。

## <a name="mbam-client"></a><a href="" id="---------mbam-client"></a> MBAM クライアント


MBAM クライアントは、コンピューターにインストールWindows次の特性があります。

-   グループ ポリシーを使用して、企業内のクライアント コンピューターの BitLocker ドライブ暗号化を強制します。

-   オペレーティング システム ドライブ、固定データ ドライブ、およびリムーバブル データ (USB) ドライブの 3 つの BitLocker データ ドライブの種類の回復キーを収集します。

-   コンピューターのコンプライアンス データを収集し、レポート システムにデータを渡します。

## <a name="related-topics"></a>関連トピック


[MBAM 2.0 をお使いになる前に](getting-started-with-mbam-20-mbam-2.md)

 

 





