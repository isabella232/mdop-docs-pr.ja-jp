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
ms.openlocfilehash: de3529fdb565859fcc212d1a9a614ac4ef4b183e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825237"
---
# MBAM 1.0 のアーキテクチャの概要


Microsoft BitLocker の管理と監視 (MBAM) は、BitLocker のプロビジョニングと展開を簡素化し、BitLocker のコンプライアンスとレポートを向上させ、サポートのコストを削減するために役立つクライアント/サーバーデータ暗号化ソリューションです。 MBAM には、このトピックで説明されている機能が含まれています。

また、MBAM アーキテクチャと MBAM セットアップの概要を示すビデオも用意されています。 詳細については、「 [Mbam 展開とアーキテクチャの概要](https://go.microsoft.com/fwlink/p/?LinkId=258392)」を参照してください。

## アーキテクチャの概要


次の図は、MBAM アーキテクチャを示しています。 MBAM 機能の紹介については、シングルサーバーの MBAM 展開トポロジを示します。 ただし、この MBAM 展開トポロジは、ラボ環境でのみ推奨されます。

**注** 運用展開では、少なくとも3台のコンピューターからインストールされた MBAM 展開トポロジをお勧めします。 MBAM 展開トポロジの詳細については、「 [mbam 1.0 サーバーインフラストラクチャの展開](deploying-the-mbam-10-server-infrastructure.md)」を参照してください。

 

![mbam single server deployment トポロジ](images/mbam-1-server.jpg)

1.  **管理と監視サーバー**。 MBAM 管理と監視サーバーは Windows サーバーにインストールされ、MBAM 管理および管理 web サイトと監視 web サービスをホストします。 MBAM 管理および管理 web サイトは、エンタープライズのコンプライアンス状態の決定、アクティビティの監査、ハードウェア機能の管理、回復データ (BitLocker 回復キーなど) へのアクセスに使用されます。 管理および監視サーバーは、次のデータベースとサービスに接続します。

    -   回復とハードウェアデータベース。 回復とハードウェアのデータベースは、Windows ベースのサーバーとサポートされている SQLServer インスタンスにインストールされています。 このデータベースには、MBAM クライアントコンピューターから収集された回復データとハードウェア情報が格納されます。

    -   コンプライアンスと監査データベース。 コンプライアンスと監査データベースは、Windows server とサポートされている SQLServer インスタンスにインストールされています。 このデータベースには、MBAM クライアントコンピューターのコンプライアンスデータが格納されます。 このデータは、主に SQL Server Reporting Services (SSRS) でホストされているレポートに使用されます。

    -   コンプライアンスおよび監査レポート。 コンプライアンスと監査レポートは、Windows ベースのサーバーにインストールされ、SSRS 機能がインストールされている SQLServer インスタンスでサポートされています。 これらのレポートでは、Microsoft BitLocker の管理と監視のレポートが提供されます。 これらのレポートには、MBAM 管理および管理 web サイトから、または SSRS サーバーから直接アクセスできます。

2.  **Mbam クライアント**。 Microsoft BitLocker 管理および監視クライアントは、次のタスクを実行します。

    -   グループポリシーを使用して、企業内のクライアントコンピューターの BitLocker 暗号化を適用します。

    -   オペレーティングシステムドライブ、固定データドライブ、およびリムーバブルデータ (USB) ドライブの3つの BitLocker データドライブの種類の回復キーを収集します。

    -   クライアントコンピューターに関する回復情報とハードウェア情報を収集します。

    -   コンピューターのコンプライアンスデータを収集し、データをレポートシステムに渡します。

3.  **ポリシーテンプレート**。 MBAM グループポリシーテンプレートは、サポートされている Windows ベースのサーバーまたはクライアントコンピューターにインストールされています。 このテンプレートは、BitLocker ドライブ暗号化の MBAM 実装設定を指定するために使用されます。

## 関連トピック


[MBAM 1.0 をお使いになる前に](getting-started-with-mbam-10.md)

 

 





