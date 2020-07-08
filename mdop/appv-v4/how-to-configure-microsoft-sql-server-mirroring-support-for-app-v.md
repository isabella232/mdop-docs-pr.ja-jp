---
title: App-V 用に Microsoft SQL Server ミラーリングのサポートを構成する方法
description: App-V 用に Microsoft SQL Server ミラーリングのサポートを構成する方法
author: dansimp
ms.assetid: 6d069eb5-109f-460a-836a-de49473b7035
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: fb572442cd12bb32fc9406de65f05a3bf061f946
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817934"
---
# App-V 用に Microsoft SQL Server ミラーリングのサポートを構成する方法


Microsoft Application Virtualization (App-v) 環境で Microsoft SQL Server データベースのミラーリングを使用するように構成するには、次の手順に従います。 データベースミラーリングの構成は、障害回復とフェールオーバーのシナリオで役立ちます。 App-v 4.5 SP2 では、Microsoft SQL Server 2005 と SQL Server 2008 で現在利用できるデータベースミラーリングのすべてのモードがサポートされています。

**注**  
この手順は、Microsoft SQL Server との SQL Server データベースとデータベースのミラーリングのセットアップと構成に精通している管理者向けに記述されています。そのため、アプリに固有の構成設定のみが含まれています。



**Microsoft SQL Server データベースのミラーリングを使用するように App-v 環境を構成するには**

1.  データベースミラーリングの標準的なビジネスプラクティスに従って、App-v データベースの SQL Server データベースのミラーリングをセットアップします。 Microsoft SQL Server データベースのミラーリングに関する一般的な情報については、次のリンクを参照してください。

    -   **MICROSOFT SQL 2005**:[データベースミラーリングのセットアップ](https://go.microsoft.com/fwlink/?LinkId=187478)(https://go.microsoft.com/fwlink/?LinkId=187478)

    -   **MICROSOFT SQL 2008**:[データベースミラーリングのセットアップ](https://go.microsoft.com/fwlink/?LinkId=187477)(https://go.microsoft.com/fwlink/?LinkId=187477)

    また、[データベースミラーリングのベストプラクティスとパフォーマンスに関する考慮事項](https://go.microsoft.com/fwlink/?LinkId=190270)( https://go.microsoft.com/fwlink/?LinkId=190270) .

2.  ミラーリングをセットアップした後で、App-v データベースに状態 **(プリンシパル、同期済み)** が表示されていることを確認し、ミラーされたデータベースに状態 **(ミラー、同期済み、復元)** が表示されていることを確認します。 次の手順に進む前に、ミラーリングの問題を解決してください。 状態の監視に関する追加情報については、「[ミラーリング状態の監視](https://go.microsoft.com/fwlink/?LinkId=190279)()」をご覧ください https://go.microsoft.com/fwlink/?LinkId=190279) 。

3.  App-v データベースのミラーをホストする sql server コンピューターで、[account name ** &lt; domain &gt; \\ &lt; managementserverhostname &gt; $ **] というアカウント名を使用して、app-v Management Server の network service アカウント用の sql server ログインを作成します。

4.  Microsoft SQL Server Native Client を App-v Management Server にインストールして、別のコンピューターにインストールされている場合は、App-v Management Web サービスを実行しているコンピューターにインストールします。 追加の App-v 管理サーバーを使用して、負荷分散のためにミラーリングされた SQL データベースに接続することを計画している場合は、これらのコンピューターにも Microsoft SQL Server Native Client をインストールする必要があります。 Microsoft ダウンロードセンター () で microsoft [Sql server 2008 Feature Pack](https://go.microsoft.com/fwlink/?LinkId=187479)のページから Microsoft Sql Server Native Client をダウンロードでき https://go.microsoft.com/fwlink/?LinkId=187479) ます。

5.  レジストリキーの**HKEY \ _LOCAL \ _MACHINE \** "\" というメッセージが表示されていることを確認してください。 \ \ または \ という名前のファイルが含まれていることを確認します。 たとえば、 *serverhostname\\instancename*のようにインスタンス名が含まれている場合は、インスタンス名を削除する必要があります。

    **重要**  
    データベースのミラーリングが有効になっている場合、App-v Management Server は TCP/IP ネットワークライブラリを使って SQL Server と通信するため、インスタンス名を使うことはできません。 代わりに、ポート番号をレジストリキーに指定する必要があります。



6.  レジストリキーの**HKEY \ _LOCAL \ _MACHINE**を確認し、sql Server コンピューターの sql に使用されているポート番号が含まれていることを確認してください。 名前付きインスタンスを使用している場合は、このキー値を名前付きインスタンスに使用するポートに設定する必要があります。

7.  レジストリキーの**HKEY \ _LOCAL \ _MACHINE \** "\" のような名前を付けてください \ \ "\" のように、REG \ _SZ として、この値を、ミラーをホストする SQL Server のホスト名に設定します。

8.  レジストリキーの**HKEY \ _LOCAL \ _MACHINE \ "\** pc \" を DWORD として作成し、その値を、sql Server を実行しているコンピューター上で、ミラーをホストするために使用されているコンピューターの sql 用のポート番号に設定します。 ミラーの名前付きインスタンスを使用している場合は、このキー値を名前付きインスタンスで使うポート番号に設定する必要があります。

9.  App-v 管理 Web サービスを実行しているコンピューターで、ユニバーサルデータリンク (UDL) のテキストファイルを構成します。 App-v がインストールされているディレクトリで、[ **Sftmgmt** ] をダブルクリックし、次の値を指定します。

    -   [**プロバイダー** ] タブで、OLE DB プロバイダーの**SQL Server Native Client 10.0**を選択します。

    -   [**次へ**] をクリックして、[**接続**] タブを選択します。[**サーバー名**] ボックスに、SQL server のサーバー名を入力します。 次に、[ **WINDOWS NT の統合セキュリティを使用する**] を選びます。 最後に、リストをクリックして**データベースを選択**し、[app-v データベース名] を選びます。

    -   [**すべて**] タブをクリックし、エントリの**フェールオーバーパートナー**を選択します。 [**値の編集**] をクリックし、フェールオーバー SQL server のサーバー名を入力します。 **[OK]** をクリックします。

    **重要**  
    App-v システムでは、Kerberos 認証を使用します。 そのため、sql Server で Kerberos 認証が有効になっていて、sql Server サービスがドメインユーザーアカウントで実行されている場合は、SPN を手動で構成する必要があります。 詳細については、「[分散環境の App-v 管理を構成](https://go.microsoft.com/fwlink/?LinkId=203186)する」の記事の「SQL サービスでドメインベースのアカウントを使用する場合」を参照してください https://go.microsoft.com/fwlink/?LinkId=203186) 。



10. データベースのミラーリングが正常に実行されていることを確認するには、フェールオーバーをテストし、App-v 管理サーバーが正常に機能していることを確認します。

    **重要**  
    操作を続行し、標準のビジネスプラクティスに従って、障害が発生した場合にシステムの操作が中断されないようにします。



~~~
After the failover has occurred successfully, as verified by using the SQL Server status monitoring information, right-click the **Applications** node in the App-V Management Console, and then select **Refresh**. The list of applications should display normally if the system is working correctly.
~~~

## 関連トピック


[Application Virtualization サーバー管理コンソールで管理タスクを実行する方法](how-to-perform-administrative-tasks-in-the-application-virtualization-server-management-console.md)









