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
# <span data-ttu-id="a7a67-103">MBAM 2.5 レポートを移動する方法</span><span class="sxs-lookup"><span data-stu-id="a7a67-103">How to Move the MBAM 2.5 Reports</span></span>


<span data-ttu-id="a7a67-104">次の手順を使用して、レポート機能を1台のコンピューターから別のコンピューターに移動します。つまり、レポート機能をサーバー A からサーバー B に移動します。</span><span class="sxs-lookup"><span data-stu-id="a7a67-104">Use these procedures to move the Reports feature from one computer to another, that is, to move the Reports feature from Server A to Server B.</span></span>

<span data-ttu-id="a7a67-105">レポート機能を移動するための大まかな手順は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a7a67-105">The high-level steps for moving the Reports feature are:</span></span>

1.  <span data-ttu-id="a7a67-106">MBAM 管理と監視 Web サイトのすべてのインスタンスを停止します。</span><span class="sxs-lookup"><span data-stu-id="a7a67-106">Stop all instances of the MBAM Administration and Monitoring Website.</span></span>

2.  <span data-ttu-id="a7a67-107">サーバー B に MBAM 2.5 サーバーソフトウェアをインストールし、サーバー B でレポート機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="a7a67-107">Install the MBAM 2.5 Server software on Server B and configure the Reports feature on Server B.</span></span>

3.  <span data-ttu-id="a7a67-108">MBAM 管理および監視サーバーのレポート接続データを更新します。</span><span class="sxs-lookup"><span data-stu-id="a7a67-108">Update the reports connection data on the MBAM Administration and Monitoring servers.</span></span>

4.  <span data-ttu-id="a7a67-109">MBAM 管理と監視 Web サイトのインスタンスを再開します。</span><span class="sxs-lookup"><span data-stu-id="a7a67-109">Resume the instance of the MBAM Administration and Monitoring Website.</span></span>

<span data-ttu-id="a7a67-110">**注** このトピックの「Windows PowerShell スクリプトの例」を実行するには、Windows PowerShell の実行ポリシーを更新して、スクリプトを実行できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7a67-110">**Note** To run the example Windows PowerShell scripts in this topic, you must update the Windows PowerShell execution policy to enable scripts to be run.</span></span> <span data-ttu-id="a7a67-111">手順については、「 [Windows PowerShell スクリプトを実行](https://technet.microsoft.com/library/ee176949.aspx)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7a67-111">See [Running Windows PowerShell Scripts](https://technet.microsoft.com/library/ee176949.aspx) for instructions.</span></span>

 

**<span data-ttu-id="a7a67-112">MBAM 管理と監視 Web サイトを停止する</span><span class="sxs-lookup"><span data-stu-id="a7a67-112">Stop the MBAM Administration and Monitoring Website</span></span>**

-   <span data-ttu-id="a7a67-113">管理と監視の Web サイトを実行しているサーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、Web サイトの管理と監視を停止します。</span><span class="sxs-lookup"><span data-stu-id="a7a67-113">On the server that is running the Administration and Monitoring Website, use the Internet Information Services (IIS) Manager console to stop the Administration and Monitoring Website.</span></span>

    <span data-ttu-id="a7a67-114">この手順を自動化するために、Windows PowerShell を使用して、次のようなコマンドを入力できます。</span><span class="sxs-lookup"><span data-stu-id="a7a67-114">To automate this procedure, you can use Windows PowerShell to enter a command that is similar to the following:</span></span>

    ``` syntax
    PS C:\> Stop-Website "Microsoft BitLocker Administration and Monitoring"
    ```

**<span data-ttu-id="a7a67-115">MBAM サーバーソフトウェアをインストールして、サーバー B で MBAM サーバー構成ウィザードを実行する</span><span class="sxs-lookup"><span data-stu-id="a7a67-115">Install MBAM Server software and run the MBAM Server Configuration wizard on Server B</span></span>**

1.  <span data-ttu-id="a7a67-116">サーバー B に MBAM サーバーソフトウェアをインストールします。手順については、「 [MBAM 2.5 サーバーソフトウェアをインストールする](installing-the-mbam-25-server-software.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7a67-116">Install the MBAM Server software on Server B. For instructions, see [Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md).</span></span>

2.  <span data-ttu-id="a7a67-117">サーバー B で、MBAM サーバー構成ウィザードを起動し、[**新しい機能の追加**] をクリックして、[**レポート**機能のみ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7a67-117">On Server B, start the MBAM Server Configuration wizard, click **Add New Features**, and then select only the **Reports** feature.</span></span>

    <span data-ttu-id="a7a67-118">または、 **MbamReport** Windows PowerShell コマンドレットを使用して、レポートを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="a7a67-118">Alternatively, you can use the **Enable-MbamReport** Windows PowerShell cmdlet to configure the Reports.</span></span>

    <span data-ttu-id="a7a67-119">レポートを構成する手順については、「 [MBAM 2.5 レポートを構成する方法](how-to-configure-the-mbam-25-reports.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7a67-119">For instructions on how to configure the Reports, see [How to Configure the MBAM 2.5 Reports](how-to-configure-the-mbam-25-reports.md).</span></span>

**<span data-ttu-id="a7a67-120">管理/監視サーバーでレポートの接続データを更新する</span><span class="sxs-lookup"><span data-stu-id="a7a67-120">Update the reports connection data on the Administration and Monitoring Server</span></span>**

1.  <span data-ttu-id="a7a67-121">レポート機能を実行しているサーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、レポート URL を更新します。</span><span class="sxs-lookup"><span data-stu-id="a7a67-121">On the server that is running the Reports feature, use the Internet Information Services (IIS) Manager console to update the Reports URL.</span></span>

2.  <span data-ttu-id="a7a67-122">[ **Microsoft BitLocker 管理と監視**] を展開して、[**ヘルプデスク**] ノードを選びます。</span><span class="sxs-lookup"><span data-stu-id="a7a67-122">Expand **Microsoft BitLocker Administration and Monitoring**, and then select the **HelpDesk** node.</span></span>

3.  <span data-ttu-id="a7a67-123">[**機能] ビュー**の [**管理**] セクションで、[**構成エディター**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7a67-123">In the **Management** section of the **Features View**, select **Configuration Editor**.</span></span>

4.  <span data-ttu-id="a7a67-124">[**セクション**] フィールドで、[ **appSettings**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a7a67-124">In the **Section** field, select **appSettings**.</span></span>

5.  <span data-ttu-id="a7a67-125">[**コレクション**] 行を選択し、ウィンドウの右端にある省略記号ボタン **(...)** をクリックして、**コレクションエディター**を開きます。</span><span class="sxs-lookup"><span data-stu-id="a7a67-125">Select the **Collection** row, and then click the "ellipses" button **(…)** at the far right of the pane to open the **Collection Editor**.</span></span>

6.  <span data-ttu-id="a7a67-126">**コレクションエディター**で、" **mbam**" という文字列が含まれている行を選択し、server B のサーバー名を反映するように、 **microsoft mbam. url**の値を更新します。</span><span class="sxs-lookup"><span data-stu-id="a7a67-126">In the **Collection Editor**, select the row that contains **Microsoft.Mbam.Reports.Url**, and update the value for **Microsoft.Mbam.Reports.Url** to reflect the server name for Server B.</span></span>

    <span data-ttu-id="a7a67-127">SQL Server Reporting Services の名前付きインスタンスでレポート機能を既に構成している場合は、URL にインスタンスの名前を追加または更新します。たとえば、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="a7a67-127">If you previously configured the Reports feature on a named instance of SQL Server Reporting Services, add or update the name of the instance to the URL, for example:</span></span>

    `http://$SERVERNAME$/ReportServer_$SQLSRSINSTANCENAME$/Pages....)`

7.  <span data-ttu-id="a7a67-128">この手順を自動化するために、Windows PowerShell を使用して、次のコード例に示すように、管理および監視サーバー上でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a7a67-128">To automate this procedure, you can use Windows PowerShell to run a command on the Administration and Monitoring Server that is similar to the following code example.</span></span>

    ``` syntax
    PS C:\> Set-WebConfigurationProperty '/appSettings/add[@key="Microsoft.Mbam.Reports.Url"]' -PSPath "IIS:\\sites\Microsoft Bitlocker Administration and Monitoring\HelpDesk" -Name "Value" -Value "http://$SERVERNAME$/ReportServer[_$SRSINSTANCENAME$]/Pages/ReportViewer.aspx?/Microsoft+BitLocker+Administration+and+Monitoring/"
    ```

    <span data-ttu-id="a7a67-129">次の表の説明を使用して、コード例の値を環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="a7a67-129">Using the descriptions in the following table, replace the values in the code example with values that match your environment.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="a7a67-130">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a7a67-130">Parameter</span></span></th>
    <th align="left"><span data-ttu-id="a7a67-131">説明</span><span class="sxs-lookup"><span data-stu-id="a7a67-131">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a7a67-132">$SERVERNAME $</span><span class="sxs-lookup"><span data-stu-id="a7a67-132">$SERVERNAME$</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a7a67-133">レポートが移動されたサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="a7a67-133">Name of the server to which the Reports were moved.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="a7a67-134">$SRSINSTANCENAME $</span><span class="sxs-lookup"><span data-stu-id="a7a67-134">$SRSINSTANCENAME$</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a7a67-135">レポートが移動された SQL Server Reporting Services のインスタンスの名前です。</span><span class="sxs-lookup"><span data-stu-id="a7a67-135">Name of the instance of SQL Server Reporting Services to which the Reports were moved.</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

**<span data-ttu-id="a7a67-136">管理と監視の Web サイトのインスタンスを再開する</span><span class="sxs-lookup"><span data-stu-id="a7a67-136">Resume the instance of the Administration and Monitoring Website</span></span>**

1.  <span data-ttu-id="a7a67-137">管理と監視の Web サイトを実行しているサーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、管理と監視の Web サイトを開きます。</span><span class="sxs-lookup"><span data-stu-id="a7a67-137">On the server that is running the Administration and Monitoring Website, use the Internet Information Services (IIS) Manager console to start the Administration and Monitoring Website.</span></span>

2.  <span data-ttu-id="a7a67-138">この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a7a67-138">To automate this procedure, you can use Windows PowerShell to run a command that is similar to the following:</span></span>

    ``` syntax
    PS C:\> Start-Website "Microsoft BitLocker Administration and Monitoring"
    ```

    <span data-ttu-id="a7a67-139">**注** このコマンドを実行するには、windows powershell の IIS モジュールを Windows PowerShell の現在のインスタンスに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7a67-139">**Note** To run this command, you must add the IIS module for Windows PowerShell to the current instance of Windows PowerShell.</span></span>

     



## <span data-ttu-id="a7a67-140">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a7a67-140">Related topics</span></span>


[<span data-ttu-id="a7a67-141">MBAM 2.5 レポートを構成する方法</span><span class="sxs-lookup"><span data-stu-id="a7a67-141">How to Configure the MBAM 2.5 Reports</span></span>](how-to-configure-the-mbam-25-reports.md)

[<span data-ttu-id="a7a67-142">Windows PowerShell を使用した MBAM 2.5 サーバー機能の構成</span><span class="sxs-lookup"><span data-stu-id="a7a67-142">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span>](configuring-mbam-25-server-features-by-using-windows-powershell.md)

[<span data-ttu-id="a7a67-143">他のサーバーへの MBAM 2.5 機能の移行</span><span class="sxs-lookup"><span data-stu-id="a7a67-143">Moving MBAM 2.5 Features to Another Server</span></span>](moving-mbam-25-features-to-another-server.md)

 
## <span data-ttu-id="a7a67-144">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="a7a67-144">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="a7a67-145">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="a7a67-145">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="a7a67-146">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="a7a67-146">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
 





