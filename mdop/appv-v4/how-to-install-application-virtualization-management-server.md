---
title: Application Virtualization Management Server をインストールする方法
description: Application Virtualization Management Server をインストールする方法
author: dansimp
ms.assetid: 8184be79-8c27-4328-a3c1-183791b5556c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dfd06ee1d2448990d5a740f3d59b0e5e4b45be4d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817364"
---
# Application Virtualization Management Server をインストールする方法


Application Virtualization Management Server は、アプリケーションをクライアントに公開します。 大規模な展開の一般的な負荷分散環境では、サーバーグループ内のすべてのサーバーが同じアプリケーションをストリーミングする必要があります。 Application Virtualization Management Server がさまざまなアプリケーションを公開する場合は、サーバーをさまざまなサーバーグループに割り当てます。 この場合、サーバーグループの容量を増やす必要がある場合もあります。

ネットワーク上でターゲットコンピューターを指定していて、ローカル管理者権限を持つログインアカウントを使用している場合は、次の手順に従って、Application Virtualization Management Server をインストールし、適切なサーバーグループに割り当てることができます。

**注**  
インストールウィザードでは、サーバーグループレコード (存在しない場合) と、Application Virtualization Management Server のメンバーシップのレコードをこのグループに作成できます。



インストールプロセスが完了したら、サーバーを再起動します。

**Application Virtualization Management Server をインストールするには**

1.  ターゲットコンピューターにインストールされている Application Virtualization Management Server の以前のバージョンを確認し、必要に応じてアンインストールします。

2.  **Microsoft Application Virtualization Management Server インストール**ウィザードを開くには、ネットワーク上のアプリケーションの仮想化システム**setup.exe**プログラムの場所に移動します。このプログラムをネットワークから実行するか、またはターゲットコンピューターにディレクトリをコピーして、 **Setup.exe**ファイルをダブルクリックします。

3.  [**ようこそ**] ページで、[**次へ**] をクリックします。

4.  [**使用許諾契約書**] ページで、ライセンス契約を読み、ライセンス契約に同意する場合は、[**ライセンス条項に同意**する] を選択します。 **[次へ]** をクリックします。

5.  [**登録情報**] ページで、ユーザー名と**組織**を入力する必要があります。 **[次へ]** をクリックします。

6.  [**セットアップの種類**] ページで、[**カスタム**] を選びます。 **[次へ]** をクリックします。 [**カスタムセットアップ**] ページで、[ **application virtualization Server**を除くすべての application virtualization システムコンポーネント] の選択を解除し、[**次へ**] をクリックします。

    **注意**  
    コンポーネントがコンピューターに既にインストールされている場合、[**カスタムセットアップ**] ウィンドウで選択を解除すると、コンポーネントが自動的にアンインストールされます。



7.  [**構成データベース**] ページで、使用可能なサーバーの一覧からデータベースサーバーを選ぶか、[**次のホスト名を使用**する] を選んで**サーバー名**と**ポート番号**のデータを指定して、サーバーを追加します。 **[次へ]** をクリックします。

    **注**  
    Application Virtualization Management Server は、大文字と小文字を区別する SQL をサポートしていません。



~~~
If a database is available, click the radio button, select the database from the list, and then click **Next**. Setup will upgrade it to this newer version. If the name does not appear in the list, enter the name in the space provided.

**Note**  
When naming a server, do not use the backslash character (/) in the server name.

If you need to install a database, see [How to Install a Database](how-to-install-a-database.md). If you would like to create a new database for this version, select **Create a new database** and specify the name that will be assigned to the new database. You can also specify a new location for the database by selecting the check box and entering the path.
~~~



8. [**接続セキュリティモード**] ページで、ドロップダウンリストから目的の証明書を選びます。 **[次へ]** をクリックします。

   **注**  
   **セキュリティで保護された接続モード**の設定では、サーバー証明書が公開キー基盤からプロビジョニングされている必要があります。 サーバー証明書がサーバーにインストールされていない場合、このオプションは利用できません。選択することはできません。 使用されている証明書へのネットワークサービスアカウントの読み取りアクセス権を付与する必要があります。



9. [ **TCP ポートの構成**] ページで、既定のポート (554) を使用するには、[ **use default port (554)**] を選びます。 カスタムポートを指定するには、[**カスタムポートを使用**する] を選択し、使用するポート番号を指定します。 **[次へ]** をクリックします。

   **注**  
   セキュリティで保護されていない環境にサーバーをインストールする場合は、既定のポート (554) を使用するか、カスタムポートを定義できます。



10. [**管理者グループ**] ページで、[**グループ名**] にこのサーバーを管理する権限が与えられているセキュリティグループの名前を指定します。 **[次へ]** をクリックします。 指定したグループを確認して、[**次へ**] をクリックします。

11. [**既定のプロバイダーグループ**] ページで、既定のプロバイダーグループの名前を指定し、[**次へ**] をクリックします。

12. [**コンテンツパス**] ページで、SFT ファイルが保存されるターゲットコンピューター上の場所を指定し、[**次へ**] をクリックします。

   **注**  
   管理サーバーの HTTP または RTSP ポートが既に割り当てられている場合は、新しいポートを選択するように求められます。 目的のポートを選択し、[**次へ**] をクリックします。



13. [**プログラムをインストールする準備ができ**ました] ページで、Application Virtualization Management Server をインストールするには、[**インストール**] をクリックします。

   **注**  
   この手順を完了しようとしたときにエラー25120が表示される場合は、IIS**管理スクリプトとツール**を有効にする必要があります。 この Windows 機能を有効にするには、[**プログラムと機能**] コントロールパネルを開き、[ **Windows 機能を有効または無効**にする] を選択して、[**インターネットインフォメーションサービス**] に移動します。

   [ **Web 管理ツール**] で、 **IIS 管理スクリプトとツール**を有効にします。



14. **インストールウィザードの完了**画面で、[**完了**] をクリックします。

   **重要**  
   インストールが完了するまで数分かかることがあります。 Windows デスクトップ通知領域の上に、インストールが成功したことを示す状態メッセージが点滅します。

   プロンプトが表示された場合は、コンピューターを再起動する必要はありません。 ただし、システムのパフォーマンスを最適化するには、再起動をお勧めします。



## 関連トピック


[サーバーおよびシステム コンポーネントをインストールする方法](how-to-install-the-servers-and-system-components.md)









