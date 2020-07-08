---
title: App-V 5.0 Server を展開する方法
description: App-V 5.0 Server を展開する方法
author: dansimp
ms.assetid: 4f8f16af-7d74-42b4-84b8-b04ce668225d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b94bab16349751aacf0aca0f8c2e5ac5a6ae6da7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814178"
---
# App-V 5.0 Server を展開する方法


次の手順を使用して、App-v 5.0 サーバーをインストールします。 App-v 5.0 SP3 サーバーの展開について詳しくは、「[アプリ-v 5.0 Sp3 につい](about-app-v-50-sp3.md#bkmk-migrate-to-50sp3)て」をご覧ください。

**始める前に:**

-   必要なソフトウェアがインストールされていることを確認します。 「 [App-v 5.0 の前提条件](app-v-50-prerequisites.md)」を参照してください。

-   「 [App-V 5.0 セキュリティに関する考慮事項](app-v-50-security-considerations.md)」のサーバーセクションを確認します。

-   各コンポーネントをホストするポートを指定します。

-   ファイアウォール規則を追加して、着信要求に対して指定されたポートへのアクセスを許可します。

-   Windows インストーラーの代わりに SQL スクリプトを使用して管理データベースまたはレポートデータベースを設定する場合は、管理サーバーまたはレポートサーバーをインストールする前に SQL スクリプトを実行する必要があります。 [SQL スクリプトを使用して App-v データベースを展開する方法に](how-to-deploy-the-app-v-databases-by-using-sql-scripts.md)ついて説明します。

**App-v 5.0 サーバーをインストールするには**

1. アプリをインストールするコンピューターに、App-v 5.0 サーバーのインストールファイルをコピーします。

2. **appv\_server\_setup.exe**を右クリックし、管理者として実行して、app-v 5.0 server のインストールを開始し、[**インストール**] をクリックします。

3. ライセンス条項を確認して同意し、Microsoft 更新プログラムを有効にするかどうかを選択します。

4. [**機能の選択**] ページで、次のすべてのコンポーネントを選択します。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">コンポーネント</th>
   <th align="left">説明</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>管理サーバー</p></td>
   <td align="left"><p>App-v インフラストラクチャの全体的な管理機能を提供します。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>管理データベース</p></td>
   <td align="left"><p>App-v 管理用のデータベース展開が容易になります。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>発行サーバー</p></td>
   <td align="left"><p>仮想アプリケーションのホスティング機能とストリーミング機能を提供します。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>レポートサーバー</p></td>
   <td align="left"><p>App-v 5.0 reporting services を提供します。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>レポートデータベース</p></td>
   <td align="left"><p>App-v レポート用のデータベース展開が容易になります。</p></td>
   </tr>
   </tbody>
   </table>

     

5. [**インストールの場所**] ページで、選択したコンポーネントをインストールする既定の場所をそのまま使うか、**インストール場所**の行に新しいパスを入力して場所を変更します。

6. [**新しい管理データベースの新規作成**] ページで、以下の適切なオプションを選択して、 **Microsoft SQL Server インスタンス**と**管理サーバーデータベース**を構成します。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">メソッド</th>
   <th align="left">必要な作業</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>ユーザー設定の Microsoft SQL Server インスタンスを使用している。</p></td>
   <td align="left"><p>[カスタムインスタンスの使用] を選択し、 <strong> </strong> インスタンスの名前を入力します。</p>
   <p>指定するには、INSTANCENAME という形式を使い <strong> </strong> ます。 想定されているインストール場所はローカルコンピューターです。</p>
   <p>サポートされていません: format <strong> ServerName の </strong> &lt; 厳密な &gt; インスタンスを使用するサーバー名 </strong> 。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>ユーザー設定のデータベース名を使用している。</p></td>
   <td align="left"><p>[ <strong> カスタム構成] を選択 </strong> し、データベース名を入力します。</p>
   <p>データベース名が一意である必要があります。インストールに失敗します。</p></td>
   </tr>
   </tbody>
   </table>

     

7. [**構成**] ページで、既定値のまま [**このローカルコンピューターを使用する**] を選びます。

   **注**  
   管理サーバーと管理データベースを並行してインストールする場合、このページの一部のオプションは使用できません。 この場合、適切なオプションが既定で選択されていますが、変更することはできません。

     

8. [**新しいレポートデータベースの新規作成**] ページで、以下の適切なオプションを選択して、 **Microsoft SQL Server インスタンス**と**レポートサーバーデータベース**を構成します。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">メソッド</th>
   <th align="left">必要な作業</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>ユーザー設定の Microsoft SQL Server インスタンスを使用している。</p></td>
   <td align="left"><p>[カスタムインスタンスの使用] を選択し、 <strong> </strong> インスタンスの名前を入力します。</p>
   <p>指定するには、INSTANCENAME という形式を使い <strong> </strong> ます。 想定されているインストール場所はローカルコンピューターです。</p>
   <p>サポートされていません: format <strong> ServerName の </strong> &lt; 厳密な &gt; インスタンスを使用するサーバー名 </strong> 。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>ユーザー設定のデータベース名を使用している。</p></td>
   <td align="left"><p>[ <strong> カスタム構成] を選択 </strong> し、データベース名を入力します。</p>
   <p>データベース名が一意である必要があります。インストールに失敗します。</p></td>
   </tr>
   </tbody>
   </table>

     

9. [**構成**] ページで、既定値のままにします (**このローカルコンピューターを使用**します)。

   **注**  
   管理サーバーと管理データベースを並行してインストールする場合、このページの一部のオプションは使用できません。 この場合、適切なオプションが既定で選択されていますが、変更することはできません。

     

10. [**構成**(Management Server 構成)] ページで、次を指定します。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">構成する項目</th>
    <th align="left">説明と例</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>App-v 環境を管理するための十分な権限を持つ広告グループを入力します。</p></td>
    <td align="left"><p>例: myの myuser</p>
    <p>インストール後、管理コンソールを使用して、ユーザーまたはグループを追加することができます。 ただし、グローバルセキュリティグループと Active Directory ドメインサービス (AD DS) 配布グループはサポートされていません。 <strong> </strong> <strong> </strong> この操作を実行するには、ドメインローカルグループまたはユニバーサルグループを使用する必要があります。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong>Web サイト名 </strong> : 発行サービスを実行するために使用されるカスタム名を指定します。</p></td>
    <td align="left"><p>独自の名前がない場合は、変更を加えないでください。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong>ポート </strong> のバインド: app-v で使用される一意のポート番号を指定します。</p></td>
    <td align="left"><p>例: <strong> 12345</strong></p>
    <p>指定したポートが別の web サイトで使用されていないことを確認します。</p></td>
    </tr>
    </tbody>
    </table>

     

11. [**発行サーバー構成**の**構成**] ページで、次を指定します。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">構成する項目</th>
    <th align="left">説明と例</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>管理サービスの URL を指定します。</p></td>
    <td align="left"><p>次<a href="http://localhost:12345" data-raw-source="http://localhost:12345">http://localhost:12345</a></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong>Web サイト名 </strong> : 発行サービスを実行するために使用されるカスタム名を指定します。</p></td>
    <td align="left"><p>独自の名前がない場合は、変更を加えないでください。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong>ポート </strong> のバインド: app-v で使用される一意のポート番号を指定します。</p></td>
    <td align="left"><p>例: 54321</p>
    <p>指定したポートが別の web サイトで使用されていないことを確認します。</p></td>
    </tr>
    </tbody>
    </table>

     

12. [ **Reporting Server** ] ページで、次を指定します。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">構成する項目</th>
    <th align="left">説明と例</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong>Web サイト名 </strong> : レポートサービスの実行に使用されるカスタム名を指定します。</p></td>
    <td align="left"><p>独自の名前がない場合は、変更を加えないでください。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong>ポート </strong> のバインド: app-v で使用される一意のポート番号を指定します。</p></td>
    <td align="left"><p>例: 55555</p>
    <p>指定したポートが別の web サイトで使用されていないことを確認します。</p></td>
    </tr>
    </tbody>
    </table>

     

13. インストールを開始するには、[**準備完了**] ページで [**インストール**] をクリックし、**完成**したページで [**閉じる**] をクリックします。

14. セットアップが正常に完了したことを確認するには、web ブラウザーを開いて、次の URL を入力します。

    **http:// &lt;管理サーバーのコンピューター名 &gt; : &lt; 管理サービスのポート番号 &gt; /Console.html**。

    例: **http://localhost:12345/console.html** 。 インストールに成功した場合、App-v 管理コンソールにエラーは表示されません。

    App-v**の提案をお寄せ**ください。 [ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。 **App-v の問題が発生しましたか?** App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

## 関連トピック


[APP-V 5.0 の展開](deploying-app-v-50.md)

[管理とレポート サービスとは別のコンピューターに管理とレポートのデータベースをインストールする方法](how-to-install-the-management-and-reporting-databases-on-separate-computers-from-the-management-and-reporting-services.md)

[リモート コンピューターに公開サーバーをインストールする方法](how-to-install-the-publishing-server-on-a-remote-computer.md)

[スクリプトを使用して APP-V 5.0 Server を展開する方法](how-to-deploy-the-app-v-50-server-using-a-script.md)

[PowerShell を使用して App-V 5.0 Client のレポート機能を有効にする方法](how-to-enable-reporting-on-the-app-v-50-client-by-using-powershell.md)

 

 





