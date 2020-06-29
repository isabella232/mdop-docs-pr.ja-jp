---
title: MBAM 2.5 スタンドアロン レポートの生成
description: MBAM 2.5 スタンドアロン レポートの生成
author: dansimp
ms.assetid: 0ec623ff-5155-4906-aef2-20cdc0f84667
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: e1c6b33de26cce5d9ad8d20461dbe0ea0f138c78
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823124"
---
# <span data-ttu-id="8de16-103">MBAM 2.5 スタンドアロン レポートの生成</span><span class="sxs-lookup"><span data-stu-id="8de16-103">Generating MBAM 2.5 Stand-alone Reports</span></span>


<span data-ttu-id="8de16-104">スタンドアロントポロジを使用して Microsoft BitLocker の管理と監視 (MBAM) を構成する場合、レポートを生成して、BitLocker ドライブ暗号化の使用状況とコンプライアンスを監視することができます。</span><span class="sxs-lookup"><span data-stu-id="8de16-104">When you configure Microsoft BitLocker Administration and Monitoring (MBAM) with the Stand-alone topology, you can generate reports to monitor BitLocker drive encryption usage and compliance.</span></span> <span data-ttu-id="8de16-105">このトピックは、次の手順で構成されています。</span><span class="sxs-lookup"><span data-stu-id="8de16-105">This topic contains the following procedures:</span></span>

-   [<span data-ttu-id="8de16-106">管理と監視の Web サイトを開くには</span><span class="sxs-lookup"><span data-stu-id="8de16-106">To open the Administration and Monitoring Website</span></span>](#bkmk-openadmin)

-   [<span data-ttu-id="8de16-107">企業のコンプライアンスレポートを生成するには</span><span class="sxs-lookup"><span data-stu-id="8de16-107">To generate an Enterprise Compliance Report</span></span>](#bkmk-enterprise)

-   [<span data-ttu-id="8de16-108">コンピューターのコンプライアンスレポートを生成するには</span><span class="sxs-lookup"><span data-stu-id="8de16-108">To generate a Computer Compliance Report</span></span>](#bkmk-computercomp)

-   [<span data-ttu-id="8de16-109">回復キーの監査レポートを生成するには</span><span class="sxs-lookup"><span data-stu-id="8de16-109">To generate a Recovery Key Audit Report</span></span>](#bkmk-recoverykey)

<span data-ttu-id="8de16-110">単体レポートの詳細については、「 [MBAM 2.5 単体レポートについ](understanding-mbam-25-stand-alone-reports.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8de16-110">For descriptions of the Stand-alone reports, see [Understanding MBAM 2.5 Stand-alone Reports](understanding-mbam-25-stand-alone-reports.md).</span></span>

<span data-ttu-id="8de16-111">**注** レポートを実行するには、 **Mbam Report Users**グループのメンバーである必要があります。これは Active Directory ドメインサービスで構成します。</span><span class="sxs-lookup"><span data-stu-id="8de16-111">**Note** To run the reports, you must be a member of the **MBAM Report Users** group, which you configure in Active Directory Domain Services.</span></span> <span data-ttu-id="8de16-112">詳細については、「 [MBAM 2.5 のグループとアカウントの計画](planning-for-mbam-25-groups-and-accounts.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8de16-112">For more information, see [Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md).</span></span>

 

<a href="" id="bkmk-openadmin"></a>**<span data-ttu-id="8de16-113">管理と監視の Web サイトを開くには</span><span class="sxs-lookup"><span data-stu-id="8de16-113">To open the Administration and Monitoring Website</span></span>**

1.  <span data-ttu-id="8de16-114">Web ブラウザーを開き、管理と監視の Web サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="8de16-114">Open a web browser and navigate to the Administration and Monitoring Website.</span></span> <span data-ttu-id="8de16-115">管理と監視の Web サイトの既定の URL は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8de16-115">The default URL for the Administration and Monitoring Website is:</span></span>

    *<span data-ttu-id="8de16-116">http (s)// &lt; mbam管理 servername &gt; : &lt; port &gt; /ヘルプデスク</span><span class="sxs-lookup"><span data-stu-id="8de16-116">http(s)://&lt;MBAMAdministrationServerName&gt;:&lt;port&gt;/Helpdesk</span></span>*

2.  <span data-ttu-id="8de16-117">左側のウィンドウで [**レポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8de16-117">In the left pane, click **Reports**.</span></span> <span data-ttu-id="8de16-118">上部のメニューバーで、実行するレポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="8de16-118">From the top menu bar, select the report you want to run.</span></span>

    <span data-ttu-id="8de16-119">MBAM クライアントデータは、コンピューターが紛失したり盗まれたりした場合に、履歴参照のためにコンプライアンスおよび監査データベース内に保持されます。</span><span class="sxs-lookup"><span data-stu-id="8de16-119">MBAM client data is retained in the Compliance and Audit Database for historical reference in case a computer is lost or stolen.</span></span> <span data-ttu-id="8de16-120">エンタープライズレポートを実行している場合、レポートデータの精度を向上させるために、適切な開始日と終了日を使用して、レポートの期間の範囲を 1 ~ 2 週間にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8de16-120">When running enterprise reports, we recommend that you use appropriate start and end dates to scope the time frames for the reports from one to two weeks to increase reporting data accuracy.</span></span>

    <span data-ttu-id="8de16-121">レポートを生成した後は、HTML、Microsoft Word、Microsoft Excel などのさまざまな形式で結果を保存できます。</span><span class="sxs-lookup"><span data-stu-id="8de16-121">After you generate a report, you can save the results in different formats, such as HTML, Microsoft Word, and Microsoft Excel.</span></span>

    <span data-ttu-id="8de16-122">**注** 管理と監視の Web サイトを構成する前に、Secure Sockets Layer (SSL) を使用するように SQL Server Reporting Services (SSRS) を構成します。</span><span class="sxs-lookup"><span data-stu-id="8de16-122">**Note** Configure SQL Server Reporting Services (SSRS) to use Secure Sockets Layer (SSL) before configuring the Administration and Monitoring Website.</span></span> <span data-ttu-id="8de16-123">何らかの理由で、SSRS が SSL を使用するように構成されていない場合、管理と監視の Web サイトを構成するときに、レポートの URL は HTTPS ではなく、HTTP に設定されます。</span><span class="sxs-lookup"><span data-stu-id="8de16-123">If, for any reason, SSRS is not configured to use SSL, the URL for the Reports will be set to HTTP instead of to HTTPS when you configure the Administration and Monitoring Website.</span></span> <span data-ttu-id="8de16-124">その後、管理と監視の Web サイトに移動してレポートを選択すると、"セキュリティで保護されたコンテンツのみが表示されます" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8de16-124">If you then go to the Administration and Monitoring Website and select a report, the following message displays: “Only Secure Content is Displayed.”</span></span> <span data-ttu-id="8de16-125">レポートを表示するには、[**すべてのコンテンツを表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8de16-125">To show the report, click **Show All Content**.</span></span>

     

<a href="" id="bkmk-enterprise"></a>**<span data-ttu-id="8de16-126">企業のコンプライアンスレポートを生成するには</span><span class="sxs-lookup"><span data-stu-id="8de16-126">To generate an Enterprise Compliance Report</span></span>**

1.  <span data-ttu-id="8de16-127">管理と監視の Web サイトで、左側のナビゲーションウィンドウから [**レポート**] ノードを選択し、[**エンタープライズコンプライアンスレポート**] を選択して、使用するフィルターを選択します。</span><span class="sxs-lookup"><span data-stu-id="8de16-127">From the Administration and Monitoring Website, select the **Reports** node from the left navigation pane, select **Enterprise Compliance Report**, and select the filters that you want to use.</span></span> <span data-ttu-id="8de16-128">エンタープライズコンプライアンスレポートで使用できるフィルターは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8de16-128">The available filters for the Enterprise Compliance Report are:</span></span>

    -   <span data-ttu-id="8de16-129">**コンプライアンスの状態**。</span><span class="sxs-lookup"><span data-stu-id="8de16-129">**Compliance Status**.</span></span> <span data-ttu-id="8de16-130">このフィルターを使用して、レポートのコンプライアンスステータスの種類を指定します (たとえば、準拠する、または準拠していない場合)。</span><span class="sxs-lookup"><span data-stu-id="8de16-130">Use this filter to specify the compliance status types of the report (for example, Compliant or Noncompliant).</span></span>

    -   <span data-ttu-id="8de16-131">**エラー状態**。</span><span class="sxs-lookup"><span data-stu-id="8de16-131">**Error State**.</span></span> <span data-ttu-id="8de16-132">このフィルターを使用して、レポートのエラー状態の種類 (エラーやエラーなど) を指定します。</span><span class="sxs-lookup"><span data-stu-id="8de16-132">Use this filter to specify the error state types of the report (for example, No Error or Error).</span></span>

2.  <span data-ttu-id="8de16-133">[**レポートの表示**] をクリックして、選択したレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="8de16-133">Click **View Report** to display the selected report.</span></span>

3.  <span data-ttu-id="8de16-134">コンピューターのコンプライアンスレポートでコンピューターに関する情報を表示するには、コンピューター名を選択します。</span><span class="sxs-lookup"><span data-stu-id="8de16-134">Select a computer name to view information about the computer in the Computer Compliance Report.</span></span>

4.  <span data-ttu-id="8de16-135">コンピューター名の横にあるプラス記号 (+) を選択すると、コンピューター上のボリュームに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8de16-135">Select the plus sign (+) next to the computer name to view information about the volumes on the computer.</span></span>

<a href="" id="bkmk-computercomp"></a>**<span data-ttu-id="8de16-136">コンピューターのコンプライアンスレポートを生成するには</span><span class="sxs-lookup"><span data-stu-id="8de16-136">To generate a Computer Compliance Report</span></span>**

1.  <span data-ttu-id="8de16-137">管理と監視の Web サイトで、左側のナビゲーションウィンドウから [**レポート**] ノードを選択し、[**コンピューターのコンプライアンスレポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8de16-137">From the Administration and Monitoring Website, select the **Report** node from the left navigation pane, and then select **Computer Compliance Report**.</span></span> <span data-ttu-id="8de16-138">コンピューターのコンプライアンスレポートを使用して、**ユーザー名**または**コンピューター名**を検索します。</span><span class="sxs-lookup"><span data-stu-id="8de16-138">Use the Computer Compliance Report to search for **User name** or **Computer name**.</span></span>

2.  <span data-ttu-id="8de16-139">[**レポートの表示**] をクリックして、コンピューターのコンプライアンスレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="8de16-139">Click **View Report** to view the Computer Compliance Report.</span></span>

3.  <span data-ttu-id="8de16-140">コンピューターのコンプライアンスレポートにコンピューターの詳細情報を表示するには、コンピューター名を選択します。</span><span class="sxs-lookup"><span data-stu-id="8de16-140">Select a computer name to display more information about the computer in the Computer Compliance Report.</span></span>

4.  <span data-ttu-id="8de16-141">コンピューター名の横にあるプラス記号 (+) を選択すると、コンピューター上のボリュームに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8de16-141">Select the plus sign (+) next to the computer name to view information about the volumes on the computer.</span></span>

    <span data-ttu-id="8de16-142">**注** MBAM クライアントコンピューターは、コンピューターが MBAM グループポリシー設定の要件を満たしているか、超える場合に、準拠していると見なされます。</span><span class="sxs-lookup"><span data-stu-id="8de16-142">**Note** An MBAM client computer is considered compliant if the computer matches or exceeds the requirements of the MBAM Group Policy settings.</span></span>

<a href="" id="bkmk-recoverykey"></a>**<span data-ttu-id="8de16-143">回復キーの監査レポートを生成するには</span><span class="sxs-lookup"><span data-stu-id="8de16-143">To generate a Recovery Key Audit Report</span></span>**

1.  <span data-ttu-id="8de16-144">管理と監視の Web サイトで、左側のナビゲーションウィンドウで [**レポート**] ノードを選択し、[**回復監査レポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8de16-144">From the Administration and Monitoring Website, select the **Report** node in the left navigation pane, and then select **Recovery Audit Report**.</span></span> <span data-ttu-id="8de16-145">回復キーの監査レポートのフィルターを選択します。</span><span class="sxs-lookup"><span data-stu-id="8de16-145">Select the filters for your Recovery Key Audit Report.</span></span> <span data-ttu-id="8de16-146">回復キーの監査で使用できるフィルターは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8de16-146">The available filters for recovery key audits are as follows:</span></span>

    -   <span data-ttu-id="8de16-147">**ヘルプデスクユーザー**。</span><span class="sxs-lookup"><span data-stu-id="8de16-147">**Helpdesk User**.</span></span> <span data-ttu-id="8de16-148">このフィルターを使用すると、ユーザーは依頼者のユーザー名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8de16-148">This filter enables users to specify the user name of the requester.</span></span> <span data-ttu-id="8de16-149">要求者は、エンドユーザーの代わりにキーにアクセスしたヘルプデスクのユーザーです。</span><span class="sxs-lookup"><span data-stu-id="8de16-149">The requester is the person in the Help Desk who accessed the key on behalf of an end user.</span></span>

    -   <span data-ttu-id="8de16-150">**エンドユーザー**。</span><span class="sxs-lookup"><span data-stu-id="8de16-150">**End User**.</span></span> <span data-ttu-id="8de16-151">このフィルターでは、ユーザーが requestee のユーザー名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8de16-151">This filter enables users to specify the user name of the requestee.</span></span> <span data-ttu-id="8de16-152">Requestee は、回復キーを取得するためにヘルプデスクを呼び出したエンドユーザーです。</span><span class="sxs-lookup"><span data-stu-id="8de16-152">The requestee is the end user who called the Help Desk to obtain a recovery key.</span></span>

    -   <span data-ttu-id="8de16-153">**結果を要求**します。</span><span class="sxs-lookup"><span data-stu-id="8de16-153">**Request Result**.</span></span> <span data-ttu-id="8de16-154">このフィルターを使用すると、ユーザーはレポートの基にする要求結果の種類 (成功または失敗など) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8de16-154">This filter enables users to specify the request result types (for example, Success or Failed) that they want to base the report on.</span></span> <span data-ttu-id="8de16-155">たとえば、失敗したキーアクセス試行を表示する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="8de16-155">For example, users may want to view failed key access attempts.</span></span>

    -   <span data-ttu-id="8de16-156">**キーの種類**。</span><span class="sxs-lookup"><span data-stu-id="8de16-156">**Key Type**.</span></span> <span data-ttu-id="8de16-157">このフィルターを使用すると、ユーザーは、レポートの基にするキーの種類 (回復キーパスワード、TPM パスワードハッシュなど) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8de16-157">This filter enables users to specify the key type (for example, Recovery Key Password or TPM Password Hash) that they want to base the report on.</span></span>

    -   <span data-ttu-id="8de16-158">**開始日**です。</span><span class="sxs-lookup"><span data-stu-id="8de16-158">**Start Date**.</span></span> <span data-ttu-id="8de16-159">このフィルターは、ユーザーが報告する日付範囲の開始日の部分を定義するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8de16-159">This filter is used to define the Start Date part of the date range that the user wants to report on.</span></span>

    -   <span data-ttu-id="8de16-160">**終了日**。</span><span class="sxs-lookup"><span data-stu-id="8de16-160">**End Date**.</span></span> <span data-ttu-id="8de16-161">このフィルターは、ユーザーが報告する日付範囲の終了日の部分を定義するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8de16-161">This filter is used to define the End Date part of the date range that the users want to report on.</span></span>

2.  <span data-ttu-id="8de16-162">[**レポートの表示**] をクリックして、レポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="8de16-162">Click **View Report** to view the report.</span></span>



## <span data-ttu-id="8de16-163">関連トピック</span><span class="sxs-lookup"><span data-stu-id="8de16-163">Related topics</span></span>


[<span data-ttu-id="8de16-164">MBAM 2.5 での BitLocker 準拠の監視とレポート</span><span class="sxs-lookup"><span data-stu-id="8de16-164">Monitoring and Reporting BitLocker Compliance with MBAM 2.5</span></span>](monitoring-and-reporting-bitlocker-compliance-with-mbam-25.md)

[<span data-ttu-id="8de16-165">MBAM 2.5 スタンドアロン レポートについて</span><span class="sxs-lookup"><span data-stu-id="8de16-165">Understanding MBAM 2.5 Stand-alone Reports</span></span>](understanding-mbam-25-stand-alone-reports.md)

 

## <span data-ttu-id="8de16-166">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="8de16-166">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="8de16-167">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="8de16-167">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="8de16-168">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="8de16-168">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





