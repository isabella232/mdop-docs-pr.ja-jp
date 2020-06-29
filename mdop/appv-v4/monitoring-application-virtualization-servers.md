---
title: Application Virtualization サーバーの監視
description: Application Virtualization サーバーの監視
author: dansimp
ms.assetid: d84355ae-4fe4-41d9-ac3a-3eaa32d9a61f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a53c0c37ca609c701727a7f4e18019a9f20110ed
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816144"
---
# Application Virtualization サーバーの監視


Application Virtualization (App-v) サーバーの管理を簡素化するために、System Center Operations Manager2007 Management Pack を使用できます。 この管理パックは、Application Virtualization (App-v) 4.5 サーバーのみをサポートします。以前のサーバーバージョンはサポートされません。 管理パックは、app-v クライアント要求を処理するための App-v Server の可用性を最大化します。

## ステータスインジケーター


App-v サーバーの正常性ステータスインジケーターは、色分けされています。 色は、次の状態の値を表します。

-   [色なしの場合、サーバーが回復不可能なエラーなしで実行されていることを示します。

-   黄色は、コンポーネントのいずれかが正常に機能していないことを示します。 サーバーの全体的な機能は低下していますが、サーバーは引き続き利用できます。

-   赤は、サーバーが使用できないことと、キーサービスを提供できないこと、または外部サービスの依存関係と通信できないことを示します。

## モニタリングの条件


管理パックは、サーバーの正常性の次の側面を監視します。

-   サーバーの状態: サーバーイベントを監視し、サーバーが予期されたサービスを提供していることを確認します。

-   データストアアクセス—1つ以上の App-v 管理サーバーが、App-v データストアにアクセスして通信できるかどうかを追跡します。

-   コンテンツデータへのアクセス—ローカルディレクトリまたはネットワーク共有である \\ コンテンツディレクトリへのアクセスを監視し、要求されたファイルを読み取ることができます。

-   セキュリティ— App-v Server の証明書とセキュリティで保護された通信に関するエラーを報告します。

-   クライアント要求の処理: クライアント要求を処理して適切に応答する1つ以上の App-v サーバーの機能を監視します。 これらの要求には、構成要求、パッケージ読み込み要求、一連の要求などとしてのアイテムの公開が含まれます。

-   [サーバー構成] — App-v Server の構成設定を確認します。 これらの構成設定には、レジストリと App-v データストアの設定が含まれます。

## サーバーの相違点


App-v 管理サーバーと App-v ストリーミングサーバーの主な違いは次のとおりです。

-   App-v 管理サーバーは、パブリッシング、ストリーミング、管理、レポートサービスを提供できます。 そのため、管理パックは、アプリを管理することができるのではなく、app-v の管理サーバーのさまざまな側面を管理することができます。これには、パッケージストリーミングのみが用意されています。

-   App-v ストリーミングサーバーには、app-v データストアがないため、データストアへのアクセスは監視されません。 App-v ストリーミングサーバーの構成情報は、レジストリで管理されます。

-   App-v ストリーミングサーバーでは、App-v Server 管理コンソールインターフェイスは使用されません。その他のツールを使用して、構成を管理します。

## 関連トピック


[Application Virtualization サーバー](application-virtualization-server.md)

 

 





