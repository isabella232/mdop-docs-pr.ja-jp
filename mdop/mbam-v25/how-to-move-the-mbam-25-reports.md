---
title: MBAM 2.5 レポートを移動する方法
description: MBAM 2.5 レポートを移動する方法
author: dansimp
ms.assetid: c8223656-ca9d-41c8-94a3-64d07a6b99e9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1cdef260b4381671a1b9de66565ece0b70876200
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812394"
---
# MBAM 2.5 レポートを移動する方法


次の手順を使用して、レポート機能を1台のコンピューターから別のコンピューターに移動します。つまり、レポート機能をサーバー A からサーバー B に移動します。

レポート機能を移動するための大まかな手順は、次のとおりです。

1.  MBAM 管理と監視 Web サイトのすべてのインスタンスを停止します。

2.  サーバー B に MBAM 2.5 サーバーソフトウェアをインストールし、サーバー B でレポート機能を構成します。

3.  MBAM 管理および監視サーバーのレポート接続データを更新します。

4.  MBAM 管理と監視 Web サイトのインスタンスを再開します。

**注** このトピックの「Windows PowerShell スクリプトの例」を実行するには、Windows PowerShell の実行ポリシーを更新して、スクリプトを実行できるようにする必要があります。 手順については、「 [Windows PowerShell スクリプトを実行](https://technet.microsoft.com/library/ee176949.aspx)する」を参照してください。

 

**MBAM 管理と監視 Web サイトを停止する**

-   管理と監視の Web サイトを実行しているサーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、Web サイトの管理と監視を停止します。

    この手順を自動化するために、Windows PowerShell を使用して、次のようなコマンドを入力できます。

    ``` syntax
    PS C:\> Stop-Website "Microsoft BitLocker Administration and Monitoring"
    ```

**MBAM サーバーソフトウェアをインストールして、サーバー B で MBAM サーバー構成ウィザードを実行する**

1.  サーバー B に MBAM サーバーソフトウェアをインストールします。手順については、「 [MBAM 2.5 サーバーソフトウェアをインストールする](installing-the-mbam-25-server-software.md)」を参照してください。

2.  サーバー B で、MBAM サーバー構成ウィザードを起動し、[**新しい機能の追加**] をクリックして、[**レポート**機能のみ] を選択します。

    または、 **MbamReport** Windows PowerShell コマンドレットを使用して、レポートを構成することもできます。

    レポートを構成する手順については、「 [MBAM 2.5 レポートを構成する方法](how-to-configure-the-mbam-25-reports.md)」を参照してください。

**管理/監視サーバーでレポートの接続データを更新する**

1.  レポート機能を実行しているサーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、レポート URL を更新します。

2.  [ **Microsoft BitLocker 管理と監視**] を展開して、[**ヘルプデスク**] ノードを選びます。

3.  [**機能] ビュー**の [**管理**] セクションで、[**構成エディター**] を選択します。

4.  [**セクション**] フィールドで、[ **appSettings**] を選びます。

5.  [**コレクション**] 行を選択し、ウィンドウの右端にある省略記号ボタン **(...)** をクリックして、**コレクションエディター**を開きます。

6.  **コレクションエディター**で、" **mbam**" という文字列が含まれている行を選択し、server B のサーバー名を反映するように、 **microsoft mbam. url**の値を更新します。

    SQL Server Reporting Services の名前付きインスタンスでレポート機能を既に構成している場合は、URL にインスタンスの名前を追加または更新します。たとえば、次のようにします。

    `http://$SERVERNAME$/ReportServer_$SQLSRSINSTANCENAME$/Pages....)`

7.  この手順を自動化するために、Windows PowerShell を使用して、次のコード例に示すように、管理および監視サーバー上でコマンドを実行します。

    ``` syntax
    PS C:\> Set-WebConfigurationProperty '/appSettings/add[@key="Microsoft.Mbam.Reports.Url"]' -PSPath "IIS:\\sites\Microsoft Bitlocker Administration and Monitoring\HelpDesk" -Name "Value" -Value "http://$SERVERNAME$/ReportServer[_$SRSINSTANCENAME$]/Pages/ReportViewer.aspx?/Microsoft+BitLocker+Administration+and+Monitoring/"
    ```

    次の表の説明を使用して、コード例の値を環境に一致する値に置き換えます。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">パラメーター</th>
    <th align="left">説明</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>$SERVERNAME $</p></td>
    <td align="left"><p>レポートが移動されたサーバーの名前。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>$SRSINSTANCENAME $</p></td>
    <td align="left"><p>レポートが移動された SQL Server Reporting Services のインスタンスの名前です。</p></td>
    </tr>
    </tbody>
    </table>

     

**管理と監視の Web サイトのインスタンスを再開する**

1.  管理と監視の Web サイトを実行しているサーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、管理と監視の Web サイトを開きます。

2.  この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドを実行します。

    ``` syntax
    PS C:\> Start-Website "Microsoft BitLocker Administration and Monitoring"
    ```

    **注** このコマンドを実行するには、windows powershell の IIS モジュールを Windows PowerShell の現在のインスタンスに追加する必要があります。

     



## 関連トピック


[MBAM 2.5 レポートを構成する方法](how-to-configure-the-mbam-25-reports.md)

[Windows PowerShell を使用した MBAM 2.5 サーバー機能の構成](configuring-mbam-25-server-features-by-using-windows-powershell.md)

[他のサーバーへの MBAM 2.5 機能の移行](moving-mbam-25-features-to-another-server.md)

 
## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。
 





