---
title: アプリケーション仮想化セキュリティ ガイドの概要
description: アプリケーション仮想化セキュリティ ガイドの概要
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
ms.openlocfilehash: 82914de48a5a5777f6ce4b50fe3e8af34dd82494
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910782"
---
# <a name="introduction-to-the-application-virtualization-security-guide"></a>アプリケーション仮想化セキュリティ ガイドの概要


この Microsoft Application Virtualization (App-V) セキュリティ ガイドには、App-V 展開で選択されたセキュリティ機能の構成を担当する管理者向け手順が記載されています。

**備考**  
このドキュメントでは、特定のセキュリティ オプションを選択するためのガイダンスは提供されていない。 この情報は、App-V セキュリティのベスト プラクティスに関するホワイト ペーパーで提供されています <https://go.microsoft.com/fwlink/?LinkId=127120> 。

 

このガイドを使用する App-V 管理者は、次のセキュリティ関連テクノロジについて理解している必要があります。

-   Active Directory Domain Services

-   公開キーインフラストラクチャ (PKI)

-   インターネット プロトコル セキュリティ (IPsec)

-   グループ ポリシー

-   インターネット インフォメーション サービス (IIS)

## <a name="app-v-infrastructure-components"></a>APP-V インフラストラクチャ コンポーネント


拡張セキュリティ App-V 環境を計画する場合は、いくつかの異なるインフラストラクチャ モデルを検討できます。

**備考**  
App-V インフラストラクチャ モデルの詳細については、次のドキュメントを参照してください。

-   [App-V の計画と展開ガイド](https://go.microsoft.com/fwlink/?LinkId=122063)

-   [インフラストラクチャの計画と設計ガイド シリーズ](https://go.microsoft.com/fwlink/?LinkId=151986)

 

これらのモデルは、次の図に示す App-V コンポーネントの一部を使用しますが、一部のコンポーネントを使用している可能性があります。

![app-v ブランチ オフィスの図。](images/appvbranchoffices.gif)

<a href="" id="application-virtualization--app-v--management-server"></a>アプリケーション仮想化 (App-V) 管理サーバー  
App-V 管理サーバーは、パッケージ コンテンツをストリーミングし、ショートカットとファイルの種類の関連付けを App-V クライアントに発行します。 App-V 管理サーバーは、アクティブなアップグレード、ライセンス管理、およびレポート作成に使用できるデータベースもサポートします。

<a href="" id="application-virtualization--app-v--streaming-server"></a>アプリケーション仮想化 (App-V) ストリーミング サーバー  
App-V ストリーミング サーバーは、ブランチ オフィスなどの環境で App-V クライアントにストリーミングするパッケージをホストします。App-V 管理サーバーへの接続の帯域幅がクライアントにパッケージコンテンツをストリーミングするには不十分です。 ストリーミング サーバーにはストリーミング機能だけが含まれているので、App-V 管理コンソールまたは App-V 管理 Web サービスは提供されません。

<a href="" id="application-virtualization--app-v--data-store"></a>アプリケーション仮想化 (App-V) データ ストア  
App-V データ ストアは、SQLデータベース内に、App-V インフラストラクチャに関連する情報を保持します。 App-V データ ストアの情報には、すべてのアプリケーション レコード、アプリケーション割り当て、およびアプリケーション仮想化環境を管理するグループが含まれます。

<a href="" id="application-virtualization--app-v--management-service"></a>アプリケーション仮想化 (App-V) 管理サービス  
App-V Management Service は、読み取り/書き込み要求をアプリケーション仮想化データ ストアに伝達します。 このコンポーネントは、App-V 管理サーバーと同じコンピューターにインストールするか、IIS がインストールされている別のコンピューターにインストールできます。

<a href="" id="application-virtualization--app-v--management-console"></a>アプリケーション仮想化 (App-V) 管理コンソール  
App-V 管理コンソールは、App-V Server 管理用のスナップイン管理ユーティリティです。 このコンポーネントは、App-V Server と同じコンピューターにインストールするか、MMC 3.0 と .NET 2.0 がインストールされている別のワークステーションにインストールできます。

<a href="" id="application-virtualization--app-v--sequencer"></a>アプリケーション仮想化 (App-V) シーケンサー  
App-V Sequencer は、アプリケーションのインストールを監視およびキャプチャし、仮想アプリケーション パッケージを作成します。 Sequencer の出力は、アプリケーション アイコン、アプリケーション定義情報を含む OSD ファイル、パッケージ マニフェスト ファイル、およびアプリケーションのコンテンツ ファイルを含む SFT ファイルで構成されます。 必要に応じてWindows App-V インフラストラクチャを使用せずにパッケージをインストールする場合は、新しいインストーラー ファイルを作成できます。

<a href="" id="application-virtualization--app-v--client"></a>アプリケーション仮想化 (App-V) クライアント  
App-V クライアントは、App-V デスクトップ クライアント コンピューターまたは App-V ターミナル サービス クライアント コンピューターにインストールされます。 仮想アプリケーション パッケージの仮想環境を提供します。 App-V クライアントは、キャッシュへのパッケージ ストリーミング、仮想アプリケーション発行の更新、およびアプリケーション仮想化サーバーとの対話を管理します。

 

 





