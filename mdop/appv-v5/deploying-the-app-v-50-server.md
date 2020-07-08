---
title: App-V 5.0 Server の展開
description: App-V 5.0 Server の展開
author: dansimp
ms.assetid: a47f0dc8-2971-4e4d-8d57-6b69bbed4b63
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e8fb65015a172a88d5e27d377037348dbc044654
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814571"
---
# App-V 5.0 Server の展開


このトピックで説明するさまざまな展開構成を使用して、App-v 5.0 サーバー機能をインストールできます。 サーバー機能をインストールする前に、「 [app-v 5.0 のセキュリティに関する考慮事項](app-v-50-security-considerations.md)」のサーバーセクションを確認してください。

App-v 5.0 SP3 サーバーの展開について詳しくは、「[アプリ-v 5.0 Sp3 につい](about-app-v-50-sp3.md#bkmk-migrate-to-50sp3)て」をご覧ください。

**重要** App-v 5.0 サーバーをインストールして構成する前に、各コンポーネントをホストするポートを指定する必要があります。 また、関連するファイアウォール規則を追加して、着信要求に対して指定されたポートへのアクセスを許可する必要もあります。 インストーラーは、ファイアウォールの設定を変更しません。

 

## <a href="" id="---------app-v-5-0-server-overview"></a> App-v 5.0 サーバーの概要


App-v 5.0 サーバーは、5つのコンポーネントで構成されています。 各コンポーネントは、App-v 5.0 環境内で異なる目的を果たします。 ここでは、5つの各コンポーネントについて簡単に説明します。

-   管理サーバー– App-v 5.0 インフラストラクチャの全体的な管理機能を提供します。

-   管理データベース– App-v 5.0 管理のデータベース展開が容易になります。

-   公開サーバー–仮想アプリケーションのホスティング機能とストリーミング機能を提供します。

-   レポートサーバー– App-v 5.0 reporting services を提供します。

-   レポートデータベース– App-v 5.0 レポートのデータベース展開を容易にします。

## <a href="" id="---------app-v-5-0-stand-alone-deployment"></a> App-v 5.0 単体展開


アプリ-V 5.0 単体展開では、小規模の展開またはテスト環境に適したトポロジが提供されます。 この種類の実装を使うと、すべてのサーバーコンポーネントが1台のコンピューターに展開されます。 サービスと関連データベースは、app-v 5.0 コンポーネントを実行しているコンピューター上のリソースに対して競合します。 そのため、このトポロジは大規模な展開には使用しないでください。

[App-V 5.0 Server を展開する方法](how-to-deploy-the-app-v-50-server-50sp3.md)

[スクリプトを使用して APP-V 5.0 Server を展開する方法](how-to-deploy-the-app-v-50-server-using-a-script.md)

## <a href="" id="---------app-v-5-0-server-distributed-deployment"></a> App-v 5.0 Server 分散展開


分散展開トポロジは、大規模な App-v 5.0 クライアントベースをサポートし、環境をより簡単に管理およびスケーリングできるようにします。 この種類の展開を使用する場合、組織の構造と要件に基づいて、App-v 5.0 サーバーコンポーネントが複数のコンピューターに展開されます。

[管理とレポート サービスとは別のコンピューターに管理とレポートのデータベースをインストールする方法](how-to-install-the-management-and-reporting-databases-on-separate-computers-from-the-management-and-reporting-services.md)

[スタンドアロン コンピューターにレポート サーバーをインストールしてデータベースに接続する方法](how-to-install-the-reporting-server-on-a-standalone-computer-and-connect-it-to-the-database.md)

[スクリプトを使用して APP-V 5.0 Server を展開する方法](how-to-deploy-the-app-v-50-server-using-a-script.md)

[リモート コンピューターに公開サーバーをインストールする方法](how-to-install-the-publishing-server-on-a-remote-computer.md)

[スタンドアロン コンピューターに管理サーバーをインストールしてデータベースに接続する方法](how-to-install-the-management-server-on-a-standalone-computer-and-connect-it-to-the-database.md)

## エンタープライズソフトウェア配布 (ESD) ソリューションと App-v 5.0 を使用する


また、アプリ-V 5.0 を展開せずに ESD を使って、App-v 5.0 のクライアントとパッケージを展開することもできます。 統合のためのすべての機能は、使用する ESD によって異なります。

**注** アプリ-V 5.0 レポートサーバーおよびレポートデータベースは、ESD と共に展開して、App-v 5.0 クライアントからレポートデータを収集することができます。 ただし、他の3つのサーバーコンポーネントは、ESD 機能と競合するため、展開しないでください。

 

[電子ソフトウェア配布 (ESD) を使用した APP-V 5.0 パッケージの展開](deploying-app-v-50-packages-by-using-electronic-software-distribution--esd-.md)

## <a href="" id="---------app-v-5-0-server-logs"></a> App-v 5.0 サーバーログ


App-v 5.0 サーバーログ情報を使用して、App-v 5.0 を使用しているときにサーバーのインストールと操作イベントのトラブルシューティングを行うことができます。 サーバー関連のログ情報は、**イベントビューアー**で確認できます。 次の行は、サーバーに関連するイベントの特定のパスを示しています。

**イベントビューアー \ \ アプリケーションとサービスログ \\ Microsoft \ \ App V**

関連する設定ログは、次のディレクトリに保存されます。

**テンポラリ**

App-v 5.0 SP3 では、一部のログが統合されて移動されています。 「 [App-v 5.0 SP3 につい](about-app-v-50-sp3.md#bkmk-event-logs-moved)て」を参照してください。

## <a href="" id="---------app-v-5-0-reporting"></a> App-v 5.0 レポート


App-v 5.0 レポートを使用すると、App-v 5.0 クライアントはデータを収集し、そのデータを中央リポジトリに保存するように返信することができます。 この情報を使用して、組織内の仮想アプリケーションの使用状況をより適切に表示できます。 次の一覧は、App-v 5.0 クライアントで収集されるいくつかの種類の情報を示しています。

-   App-v 5.0 クライアントを実行しているコンピューターに関する情報。

-   App-v 5.0 クライアントを実行する特定のコンピューター上の仮想化されたパッケージに関する情報。

-   特定のユーザーに対して開いているパッケージとシャットダウンする情報

レポートの情報は、レポートサーバーデータベースに正常に送信されるまで保持されます。 データがデータベースに含まれたら、Microsoft SQL Server Reporting Services を使用して、必要なレポートを生成することができます。

レポート情報を取得する場合は、Microsoft SQL Server Reporting Services (SSRS) を使用する必要があります。これは Microsoft SQL で利用できます。 SSRS は、App-v 5.0 レポートサーバーをインストールするときにはインストールされず、関連付けられたレポートを生成するために個別に展開する必要があります。

[App-v 5.0 レポート](about-app-v-50-reporting.md)の詳細については、次のリンクを参照してください。

[PowerShell を使用して App-V 5.0 Client のレポート機能を有効にする方法](how-to-enable-reporting-on-the-app-v-50-client-by-using-powershell.md)

## App-v server のその他のリソース


[APP-V 5.0 の展開](deploying-app-v-50.md)






 

 





