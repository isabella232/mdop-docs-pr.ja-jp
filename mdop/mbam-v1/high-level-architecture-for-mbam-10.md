---
title: MBAM 1.0 のアーキテクチャの概要
description: MBAM 1.0 のアーキテクチャの概要
author: dansimp
ms.assetid: b1349196-88ed-4d6c-8a1d-998f18127b6b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: d06c7bd801a9dd63916d310af75e88a307e7226a
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910412"
---
# <a name="high-level-architecture-for-mbam-10"></a>MBAM 1.0 のアーキテクチャの概要


Microsoft BitLocker Administration and Monitoring (MBAM) は、BitLocker のプロビジョニングと展開を簡素化し、BitLocker のコンプライアンスとレポート作成を改善し、サポート コストを削減するのに役立つクライアント/サーバー のデータ暗号化ソリューションです。 MBAM には、このトピックで説明する機能が含まれています。

さらに、MBAM アーキテクチャと MBAM セットアップの概要を示すビデオがあります。 詳細については [、「MBAM 展開とアーキテクチャの概要」を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=258392)。

## <a name="architecture-overview"></a>アーキテクチャの概要


次の図は、MBAM アーキテクチャを示しています。 MBAM 機能を導入するために、単一サーバーの MBAM 展開トポロジが表示されます。 ただし、この MBAM 展開トポロジはラボ環境にのみ推奨されます。

**備考**  
実稼働環境では、少なくとも 3 コンピューターの MBAM 展開トポロジをお勧めします。 MBAM 展開トポロジの詳細については [、「MBAM 1.0](deploying-the-mbam-10-server-infrastructure.md)Server Infrastructure の展開」を参照してください。

 

![mbam 単一サーバー展開トポロジ。](images/mbam-1-server.jpg)

1.  **管理および監視サーバー**。 MBAM 管理および監視サーバーは、Windowsサーバーにインストールされ、MBAM 管理および管理 Web サイトと監視 Web サービスをホストします。 MBAM 管理および管理 Web サイトを使用して、エンタープライズ コンプライアンスの状態を判断し、アクティビティを監査し、ハードウェア機能を管理し、BitLocker 回復キーなどの回復データにアクセスします。 管理サーバーと監視サーバーは、次のデータベースとサービスに接続します。

    -   回復とハードウェア データベース。 回復およびハードウェア データベースは、Windowsベースのサーバーにインストールされ、SQL Serverされます。 このデータベースには、MBAM クライアント コンピューターから収集される回復データとハードウェア情報が格納されます。

    -   コンプライアンスと監査データベース。 コンプライアンスデータベースと監査データベースは、Windowsサーバーにインストールされ、SQL Serverされます。 このデータベースには、MBAM クライアント コンピューターのコンプライアンス データが格納されます。 このデータは、主に、SSRS (SSRS) によってホストSQL Server Reporting Servicesに使用されます。

    -   コンプライアンスレポートと監査レポート。 コンプライアンスレポートと監査レポートは、WINDOWSベースのサーバーにインストールされ、SSRS 機能がインストールSQL Serverサポートされているサーバー インスタンスにインストールされます。 これらのレポートは、Microsoft BitLocker 管理レポートと監視レポートを提供します。 これらのレポートには、MBAM Administration and Management Web サイトから、または SSRS Server から直接アクセスできます。

2.  **MBAM クライアント 。** Microsoft BitLocker 管理および監視クライアントは、次のタスクを実行します。

    -   グループ ポリシーを使用して、エンタープライズ内のクライアント コンピューターの BitLocker 暗号化を適用します。

    -   オペレーティング システム ドライブ、固定データ ドライブ、およびリムーバブル データ (USB) ドライブの 3 つの BitLocker データ ドライブの種類の回復キーを収集します。

    -   クライアント コンピューターに関する回復情報とハードウェア情報を収集します。

    -   コンピューターのコンプライアンス データを収集し、レポート システムにデータを渡します。

3.  **ポリシー テンプレート**。 MBAM グループ ポリシー テンプレートは、サポートされているサーバー またはクライアント Windowsにインストールされます。 このテンプレートは、BitLocker ドライブ暗号化の MBAM 実装設定を指定するために使用されます。

## <a name="related-topics"></a>関連トピック


[MBAM 1.0 をお使いになる前に](getting-started-with-mbam-10.md)

 

 





