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
ms.openlocfilehash: ddc061a1aec5141548c2d2141be38f8501d2244d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824704"
---
# MBAM 2.0 のアーキテクチャの概要


Microsoft BitLocker の管理と監視 (MBAM) は、BitLocker のプロビジョニングと展開を簡素化し、BitLocker に関するコンプライアンスとレポートを向上させ、サポートのコストを削減するために使用できるクライアント/サーバーソリューションです。 Microsoft BitLocker の管理と監視には、このトピックで説明する機能が含まれています。

Microsoft BitLocker の管理と監視は、スタンドアロントポロジまたは Microsoft System Center Configuration Manager 2007 または MicrosoftSystemCenter2012 ConfigurationManager と統合されたトポロジに展開できます。 このトピックでは、スタンドアロントポロジのアーキテクチャについて説明します。 統合構成マネージャートポロジでの展開について詳しくは、「 [MBAM と構成マネージャーを使用する](using-mbam-with-configuration-manager.md)」をご覧ください。

次の図は、2つのサーバーと管理ワークステーションで構成される運用環境の MBAM 推奨アーキテクチャを示しています。 このアーキテクチャでは、最大 20万 MBAM クライアントがサポートされています。 アーキテクチャイメージのサーバー機能とデータベースについては、次のセクションで説明しています。また、これらの機能をインストールすることをお勧めするコンピューターまたはサーバーの下に表示されています。

**注** 単一サーバーアーキテクチャは、テスト環境でのみ使用する必要があります。

 

![mbam 2 2-サーバー展開トポロジ](images/mbam2-3-servers.gif)

## 管理と監視サーバー


このサーバーには、次の機能がインストールされています。

-   **管理と監視サーバー**。 管理と監視のサーバー機能は Windows サーバーにインストールされ、管理と監視の web サイトで構成されます。これには、レポート、ヘルプデスクポータル、および監視 web サービスが含まれます。

-   **セルフサービスポータル**。 セルフサービスポータルは Windows サーバーにインストールされます。 セルフサービスポータルを使用すると、クライアントコンピューターのエンドユーザーが、ロックされた BitLocker ボリュームを回復するための回復キーを取得できる web サイトに個別にログオンできます。

## データベースサーバー


このサーバーには、次の機能がインストールされています。

-   **回復データベース**。 回復データベースは、Windows server とサポートされている Microsoft SQLServer のインスタンスにインストールされています。 このデータベースには、MBAM クライアントコンピューターから収集された回復データが格納されます。

-   **コンプライアンスと監査データベース**。 コンプライアンスと監査データベースは、Windows server とサポートされている SQLServer のインスタンスにインストールされています。 このデータベースには、MBAM クライアントコンピューターのコンプライアンスデータが格納されます。 このデータは、主に SQL Server Reporting Services (SSRS) ホストであるレポートに使用されます。

-   **コンプライアンスおよび監査レポート**。 コンプライアンスと監査レポートは、Windows server と、SQL Server Reporting Services (SSRS) 機能がインストールされている SQLServer のサポートされているインスタンスにインストールされています。 これらのレポートには、管理と監視の web サイトから、または SSRS サーバーから直接アクセスできる MBAM レポートが用意されています。

## 管理ワークステーション


以下の機能は管理ワークステーションにインストールされます。これは、Windows server またはクライアントコンピューターとして使用できます。

-   **ポリシーテンプレート**。 ポリシーテンプレートは、BitLocker ドライブ暗号化の MBAM 実装設定を定義するグループポリシー設定で構成されます。 ポリシーテンプレートは、任意のサーバーまたはワークステーションにインストールできますが、一般的には、サポートされている Windows サーバーまたはクライアントコンピューターである管理ワークステーションにインストールされます。 ワークステーションは専用のコンピュータである必要はありません。

## <a href="" id="---------mbam-client"></a> MBAM クライアント


MBAM クライアントは Windows コンピューターにインストールされ、次のような特徴があります。

-   グループポリシーを使用して、企業内のクライアントコンピューターの BitLocker ドライブ暗号化を適用します。

-   オペレーティングシステムドライブ、固定データドライブ、およびリムーバブルデータ (USB) ドライブの3つの BitLocker データドライブの種類の回復キーを収集します。

-   コンピューターのコンプライアンスデータを収集し、データをレポートシステムに渡します。

## 関連トピック


[MBAM 2.0 をお使いになる前に](getting-started-with-mbam-20-mbam-2.md)

 

 





