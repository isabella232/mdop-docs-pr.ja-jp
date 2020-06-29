---
title: Application Virtualization セキュリティガイドの概要
description: Application Virtualization セキュリティガイドの概要
author: dansimp
ms.assetid: 50e1d220-7a95-45b8-933b-3dadddebe26f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4b41c65c5ad753aa606d47d2eafe4a28e035cc4e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816267"
---
# Application Virtualization セキュリティガイドの概要


この Microsoft Application Virtualization (App-v) セキュリティガイドには、App-v の展開用に選択されたセキュリティ機能の構成を担当する管理者向けの手順が記載されています。

**注** このドキュメントでは、特定のセキュリティオプションを選ぶためのガイダンスは提供していません。 この情報については、「App V セキュリティのベストプラクティス」をご覧 <https://go.microsoft.com/fwlink/?LinkId=127120> ください。

 

このガイドを使用する App-v 管理者として、次のセキュリティ関連テクノロジに精通している必要があります。

-   Active Directory Domain Services

-   公開キー基盤 (PKI)

-   インターネットプロトコルセキュリティ (IPsec)

-   グループポリシー

-   インターネットインフォメーションサービス (IIS)

## APP-V インフラストラクチャコンポーネント


セキュリティで保護されたアプリを拡張する環境を計画するときは、いくつかの異なるインフラストラクチャモデルを検討することができます。

**注** App-v インフラストラクチャモデルの詳細については、次のドキュメントを参照してください。

-   [App-v の計画と展開ガイド](https://go.microsoft.com/fwlink/?LinkId=122063)

-   [インフラストラクチャ計画と設計ガイドシリーズ](https://go.microsoft.com/fwlink/?LinkId=151986)

 

これらのモデルでは、次の図に示すように、一部の App-v コンポーネントを使用することはできません。

![app-v ブランチオフィスダイアグラム](images/appvbranchoffices.gif)

<a href="" id="application-virtualization--app-v--management-server"></a>Application Virtualization (App V) Management Server  
App-v 管理サーバーは、パッケージコンテンツをストリームし、ショートカットとファイルの種類の関連付けを App-v クライアントに公開します。 App-v 管理サーバーでは、アクティブなアップグレード、ライセンス管理、およびレポートに使用できるデータベースもサポートされています。

<a href="" id="application-virtualization--app-v--streaming-server"></a>Application Virtualization (App-v) Streaming Server  
App-v ストリーミングサーバーは、ブランチオフィスなどの環境で、app-v クライアントにストリーミングするためのパッケージをホストします。これは、パッケージコンテンツをクライアントにストリーミング配信するための帯域幅が十分でない場合です。 ストリーミングサーバーにはストリーミング機能のみが含まれており、App-v の管理コンソールまたは App-v の管理 Web サービスを利用することはできません。

<a href="" id="application-virtualization--app-v--data-store"></a>Application Virtualization (App-v) データストア  
SQL データベースの App-v データストアは、App-v インフラストラクチャに関連する情報を保持します。 App-v データストアの情報には、すべてのアプリケーションレコード、アプリケーションの割り当て、およびアプリケーションの仮想化環境を管理するグループが含まれます。

<a href="" id="application-virtualization--app-v--management-service"></a>Application Virtualization (App-v) 管理サービス  
App-v 管理サービスは、読み取り/書き込み要求をアプリケーションの仮想化データストアに伝達します。 このコンポーネントは、App-v Management Server と同じコンピューター、または IIS がインストールされている別のコンピューターにインストールできます。

<a href="" id="application-virtualization--app-v--management-console"></a>Application Virtualization (App V) 管理コンソール  
App-v 管理コンソールは、app-v Server 管理のスナップイン管理ユーティリティです。 このコンポーネントは、App-v Server と同じコンピューター上にインストールすることも、MMC 3.0 との別のワークステーションにインストールすることもできます。NET 2.0 がインストールされています。

<a href="" id="application-virtualization--app-v--sequencer"></a>Application Virtualization (App-v) Sequencer  
App-v Sequencer は、アプリケーションのインストールを監視してキャプチャし、仮想アプリケーションパッケージを作成します。 Sequencer の出力は、アプリケーションアイコン、アプリケーション定義情報を含む OSD ファイル、パッケージマニフェストファイル、およびアプリケーションのコンテンツファイルを含む SFT ファイルで構成されます。 必要に応じて、App-v インフラストラクチャを使わずに、パッケージをインストールするための Windows Installer ファイルを作成できます。

<a href="" id="application-virtualization--app-v--client"></a>Application Virtualization (App-v) クライアント  
App-v クライアントは、app-v デスクトップクライアントコンピューターまたは App-v ターミナルサービスクライアントコンピューターにインストールされます。 仮想アプリケーションパッケージの仮想環境を提供します。 App-v クライアントは、アプリへのパッケージストリーミング、仮想アプリケーション発行の更新、アプリケーション仮想化サーバーとの操作を管理します。

 

 





