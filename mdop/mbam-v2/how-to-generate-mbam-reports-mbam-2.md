---
title: MBAM レポートを生成する方法
description: MBAM レポートを生成する方法
author: dansimp
ms.assetid: 083550cb-8c3f-49b3-a30e-97d85374d2f4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ccdc1a2cd69d8cc2e2c2823827f5ea43ad867a78
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824094"
---
# <span data-ttu-id="e8afa-103">MBAM レポートを生成する方法</span><span class="sxs-lookup"><span data-stu-id="e8afa-103">How to Generate MBAM Reports</span></span>


<span data-ttu-id="e8afa-104">スタンドアロントポロジを使用して Microsoft BitLocker の管理と監視 (MBAM) をインストールすると、さまざまなレポートを生成して、BitLocker 暗号化の使用状況とコンプライアンスを監視できます。</span><span class="sxs-lookup"><span data-stu-id="e8afa-104">When you install Microsoft BitLocker Administration and Monitoring (MBAM) with the Stand-alone topology, you can generate different reports to monitor BitLocker encryption usage and compliance.</span></span> <span data-ttu-id="e8afa-105">このトピックの手順では、管理と監視の web サイトを開き、エンタープライズのコンプライアンス、個々のコンピューター、およびキーの回復アクティビティに関する Microsoft BitLocker の管理と監視のレポートを生成するために必要な手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="e8afa-105">The procedures in this topic describe how to open the Administration and Monitoring website and the steps that are needed to generate Microsoft BitLocker Administration and Monitoring reports on enterprise compliance, individual computers, and key recovery activity.</span></span> <span data-ttu-id="e8afa-106">MBAM レポートについて詳しくは、「 [Mbam レポートについ](understanding-mbam-reports-mbam-2.md)て」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e8afa-106">For detailed information to help understand MBAM reports, see [Understanding MBAM Reports](understanding-mbam-reports-mbam-2.md).</span></span>

<span data-ttu-id="e8afa-107">**注** レポートを実行するには、管理と監視サーバーの機能、コンプライアンスおよび監査データベース、コンプライアンスおよび監査レポートがインストールされているコンピューターで、**レポートユーザーロール**のメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8afa-107">**Note** To run the reports, you must be a member of the **Report Users Role** on the computers where the Administration and Monitoring Server features, Compliance and Audit Database, and Compliance and Audit Reports are installed.</span></span>

 

**<span data-ttu-id="e8afa-108">管理と監視の web サイトを開くには</span><span class="sxs-lookup"><span data-stu-id="e8afa-108">To open the Administration and Monitoring website</span></span>**

1.  <span data-ttu-id="e8afa-109">Web ブラウザーを開き、管理と監視の web サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="e8afa-109">Open a web browser and navigate to the Administration and Monitoring website.</span></span> <span data-ttu-id="e8afa-110">管理および監視 web サイトの既定の URL は\*http:// &lt; computername &gt; \*です。</span><span class="sxs-lookup"><span data-stu-id="e8afa-110">The default URL for the Administration and Monitoring website is *http://&lt;computername&gt;*.</span></span>

    <span data-ttu-id="e8afa-111">**注** 管理と監視の web サイトが80以外のポートにインストールされている場合は、URL にポートを指定する必要があります (たとえば、 \*http:// &lt; computername &gt; : &lt; port &gt; \*)。</span><span class="sxs-lookup"><span data-stu-id="e8afa-111">**Note** If theAdministration and Monitoring website was installed on a port other than 80, you have to specify the port in the URL (for example, *http://&lt;computername&gt;:&lt;port&gt;*.</span></span> <span data-ttu-id="e8afa-112">インストール中に管理と監視の web サイトのホスト名を指定した場合、URL*は &lt; http:// &gt; hostname*になります。</span><span class="sxs-lookup"><span data-stu-id="e8afa-112">If you specified a host name for theAdministration and Monitoring website during the installation, the URL is *http://&lt;hostname&gt;*.</span></span>

     

2.  <span data-ttu-id="e8afa-113">左側のウィンドウで [**レポート**] をクリックし、トップメニューバーから実行するレポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="e8afa-113">In the left pane, click **Reports** and then select the report you want to run from the top menu bar.</span></span>

    <span data-ttu-id="e8afa-114">歴史的な MBAM クライアントデータは、コンピューターが紛失したり盗まれたりした場合に、履歴参照のためにコンプライアンスデータベースに保持されます。</span><span class="sxs-lookup"><span data-stu-id="e8afa-114">Historical MBAM client data is retained in the compliance database for historical reference in case a computer is lost or stolen.</span></span> <span data-ttu-id="e8afa-115">エンタープライズレポートを実行している場合、レポートデータの精度を向上させるために、適切な開始日と終了日を使用して、レポートの期間の範囲を 1 ~ 2 週間にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e8afa-115">When running enterprise reports, we recommend that you use appropriate start and end dates to scope the time frames for the reports from one to two weeks to increase reporting data accuracy.</span></span>

    <span data-ttu-id="e8afa-116">**注** SSRS がセキュアソケットレイヤーを使用するように構成されていない場合、MBAM サーバーをインストールするときに、レポートの URL は HTTPS ではなく、HTTP に設定されます。</span><span class="sxs-lookup"><span data-stu-id="e8afa-116">**Note** If SSRS was not configured to use Secure Socket Layer, the URL for the reports will be set to HTTP instead of to HTTPS when you install the MBAM Server.</span></span> <span data-ttu-id="e8afa-117">その後、ヘルプデスクポータルに移動してレポートを選ぶと、"セキュリティで保護されたコンテンツのみが表示されます" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8afa-117">If you then go to the Help Desk portal and select a report, the following message displays: “Only Secure Content is Displayed.”</span></span> <span data-ttu-id="e8afa-118">レポートを表示するには、[**すべてのコンテンツを表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8afa-118">To show the report, click **Show All Content**.</span></span>

     

**<span data-ttu-id="e8afa-119">企業のコンプライアンスレポートを生成するには</span><span class="sxs-lookup"><span data-stu-id="e8afa-119">To generate an Enterprise Compliance Report</span></span>**

1.  <span data-ttu-id="e8afa-120">管理と監視の web サイトで、左側のナビゲーションウィンドウから [**レポート**] ノードを選択し、[**エンタープライズコンプライアンスレポート**] を選択して、使用するフィルターを選択します。</span><span class="sxs-lookup"><span data-stu-id="e8afa-120">From the Administration and Monitoring website, select the **Reports** node from the left navigation pane, select **Enterprise Compliance Report**, and select the filters that you want to use.</span></span> <span data-ttu-id="e8afa-121">エンタープライズコンプライアンスレポートで使用できるフィルターは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e8afa-121">The available filters for the Enterprise Compliance Report are the following:</span></span>

    -   <span data-ttu-id="e8afa-122">**コンプライアンスの状態**。</span><span class="sxs-lookup"><span data-stu-id="e8afa-122">**Compliance Status**.</span></span> <span data-ttu-id="e8afa-123">このフィルターを使用して、レポートのコンプライアンスステータスの種類 (たとえば、準拠、非準拠など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="e8afa-123">Use this filter to specify the compliance status types (for example, Compliant, or Noncompliant) of the report.</span></span>

    -   <span data-ttu-id="e8afa-124">**エラー状態**。</span><span class="sxs-lookup"><span data-stu-id="e8afa-124">**Error State**.</span></span> <span data-ttu-id="e8afa-125">このフィルターを使用して、レポートのエラー状態の種類 (エラーやエラーなど) を指定します。</span><span class="sxs-lookup"><span data-stu-id="e8afa-125">Use this filter to specify the error state types (for example, No Error, or Error) of the report.</span></span>

2.  <span data-ttu-id="e8afa-126">[**レポートの表示**] をクリックして、選択したレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="e8afa-126">Click **View Report** to display the selected report.</span></span>

    <span data-ttu-id="e8afa-127">結果は、HTML、Microsoft Word、Microsoft Excel など、さまざまな形式で保存できます。</span><span class="sxs-lookup"><span data-stu-id="e8afa-127">Results can be saved in different formats, such as HTML, Microsoft Word, and Microsoft Excel.</span></span>

    <span data-ttu-id="e8afa-128">**注** エンタープライズコンプライアンスレポートは、6時間ごとに実行される SQL ジョブによって生成されます。</span><span class="sxs-lookup"><span data-stu-id="e8afa-128">**Note** The Enterprise Compliance report is generated by a SQL job that runs every six hours.</span></span> <span data-ttu-id="e8afa-129">そのため、最初にレポートを表示したときに、一部のデータが失われることがあります。</span><span class="sxs-lookup"><span data-stu-id="e8afa-129">Therefore, the first time you view the report, you may find that some data is missing.</span></span> <span data-ttu-id="e8afa-130">更新されたレポートデータは、SQL Management Studio を使用して手動で生成できます。</span><span class="sxs-lookup"><span data-stu-id="e8afa-130">You can generate updated report data manually by using SQL Management Studio.</span></span> <span data-ttu-id="e8afa-131">[**オブジェクトエクスプローラー** ] ウィンドウで、 **[SQL Server エージェント**]、[**ジョブ**] の順に展開し、 **CreateCache**ジョブを右クリックして、[**ステップでジョブを開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8afa-131">From the **Object Explorer** window, expand **SQL Server Agent**, expand **Jobs**, right-click the **CreateCache** job, and select **Start Job at Step….**</span></span>

     

3.  <span data-ttu-id="e8afa-132">コンピューターのコンプライアンスレポートでコンピューターに関する情報を表示するには、コンピューター名を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8afa-132">Select a computer name to view information about the computer in the Computer Compliance Report.</span></span>

4.  <span data-ttu-id="e8afa-133">コンピューター名の横にあるプラス記号 (+) を選択すると、コンピューター上のボリュームに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8afa-133">Select the plus sign (+) next to the computer name to view information about the volumes on the computer.</span></span>

**<span data-ttu-id="e8afa-134">コンピューターのコンプライアンスレポートを生成するには</span><span class="sxs-lookup"><span data-stu-id="e8afa-134">To generate the Computer Compliance Report</span></span>**

1.  <span data-ttu-id="e8afa-135">管理と監視の web サイトで、左側のナビゲーションウィンドウから [**レポート**] ノードを選択し、[**コンピューターのコンプライアンスレポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8afa-135">In the Administration and Monitoring website, select the **Report** node from the left navigation pane, and then select the **Computer Compliance Report**.</span></span> <span data-ttu-id="e8afa-136">コンピューターのコンプライアンスレポートを使用して、**ユーザー名**または**コンピューター名**を検索します。</span><span class="sxs-lookup"><span data-stu-id="e8afa-136">Use the Computer Compliance report to search for **user name** or **computer name**.</span></span>

2.  <span data-ttu-id="e8afa-137">[**レポートの表示**] をクリックして、コンピューターレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="e8afa-137">Click **View Report** to view the computer report.</span></span>

    <span data-ttu-id="e8afa-138">結果は、HTML、Microsoft Word、Microsoft Excel など、さまざまな形式で保存できます。</span><span class="sxs-lookup"><span data-stu-id="e8afa-138">Results can be saved in different formats, such as HTML, Microsoft Word, and Microsoft Excel.</span></span>

3.  <span data-ttu-id="e8afa-139">コンピューターのコンプライアンスレポートにコンピューターの詳細情報を表示するには、コンピューター名を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8afa-139">Select a computer name to display more information about the computer in the Computer Compliance Report.</span></span>

4.  <span data-ttu-id="e8afa-140">コンピューター名の横にあるプラス記号 (+) を選択すると、コンピューター上のボリュームに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8afa-140">Select the plus sign (+) next to the computer name to view information about the volumes on the computer.</span></span>

    <span data-ttu-id="e8afa-141">**注** MBAM クライアントコンピューターは、コンピューターが MBAM ポリシー設定の要件を満たしている場合に、準拠していると見なされます。</span><span class="sxs-lookup"><span data-stu-id="e8afa-141">**Note** An MBAM client computer is considered compliant if the computer matches the requirements of the MBAM policy settings.</span></span>

     

**<span data-ttu-id="e8afa-142">回復キーの監査レポートを生成するには</span><span class="sxs-lookup"><span data-stu-id="e8afa-142">To generate the Recovery Key Audit Report</span></span>**

1.  <span data-ttu-id="e8afa-143">管理と監視の web サイトで、左側のナビゲーションウィンドウで [**レポート**] ノードを選択し、[**回復監査] レポート**を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8afa-143">From the Administration and Monitoring website, select the **Report** node in the left navigation pane, and then select the **Recovery Audit Report**.</span></span> <span data-ttu-id="e8afa-144">回復キーの監査レポートのフィルターを選択します。</span><span class="sxs-lookup"><span data-stu-id="e8afa-144">Select the filters for your Recovery Key Audit report.</span></span> <span data-ttu-id="e8afa-145">回復キーの監査で使用できるフィルターは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e8afa-145">The available filters for Recovery Key audits are as follows:</span></span>

    -   <span data-ttu-id="e8afa-146">**要求者**。</span><span class="sxs-lookup"><span data-stu-id="e8afa-146">**Requestor**.</span></span> <span data-ttu-id="e8afa-147">このフィルターを使用すると、ユーザーは依頼者のユーザー名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e8afa-147">This filter enables users to specify the user name of the requester.</span></span> <span data-ttu-id="e8afa-148">要求者とは、ユーザーの代わりにキーにアクセスした、ヘルプデスクの担当者のことです。</span><span class="sxs-lookup"><span data-stu-id="e8afa-148">The requester is the person in the Help Desk who accessed the key on behalf of a user.</span></span>

    -   <span data-ttu-id="e8afa-149">**Requestee**。</span><span class="sxs-lookup"><span data-stu-id="e8afa-149">**Requestee**.</span></span> <span data-ttu-id="e8afa-150">このフィルターでは、ユーザーが requestee のユーザー名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e8afa-150">This filter enables users to specify the user name of the requestee.</span></span> <span data-ttu-id="e8afa-151">Requestee は、回復キーを取得するためにヘルプデスクを呼び出したユーザーです。</span><span class="sxs-lookup"><span data-stu-id="e8afa-151">The requestee is the person who called the Help Desk to obtain a recovery key.</span></span>

    -   <span data-ttu-id="e8afa-152">**結果を要求**します。</span><span class="sxs-lookup"><span data-stu-id="e8afa-152">**Request Result**.</span></span> <span data-ttu-id="e8afa-153">このフィルターを使用すると、ユーザーはレポートの基にする要求結果の種類 (成功または失敗など) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e8afa-153">This filter enables users to specify the request result types (for example, Success or Failed) that they want to base the report on.</span></span> <span data-ttu-id="e8afa-154">たとえば、失敗したキーアクセス試行を表示する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="e8afa-154">For example, users may want to view failed key access attempts.</span></span>

    -   <span data-ttu-id="e8afa-155">**キーの種類**。</span><span class="sxs-lookup"><span data-stu-id="e8afa-155">**Key Type**.</span></span> <span data-ttu-id="e8afa-156">このフィルターを使用すると、ユーザーは、レポートの基にするキーの種類 (回復キーパスワードや TPM パスワードハッシュなど) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e8afa-156">This filter enables users to specify the Key Type (for example: Recovery Key Password or TPM Password Hash) that they want to base the report on.</span></span>

    -   <span data-ttu-id="e8afa-157">**開始日**です。</span><span class="sxs-lookup"><span data-stu-id="e8afa-157">**Start Date**.</span></span> <span data-ttu-id="e8afa-158">このフィルターは、ユーザーが報告する日付範囲の開始日の部分を定義するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e8afa-158">This filter is used to define the Start Date part of the date range that the user wants to report on.</span></span>

    -   <span data-ttu-id="e8afa-159">**終了日**。</span><span class="sxs-lookup"><span data-stu-id="e8afa-159">**End Date**.</span></span> <span data-ttu-id="e8afa-160">このフィルターは、ユーザーが報告する日付範囲の終了日の部分を定義するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e8afa-160">This filter is used to define the End Date part of the date range that the users want to report on.</span></span>

2.  <span data-ttu-id="e8afa-161">[**レポートの表示**] をクリックして、レポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="e8afa-161">Click **View Report** to view the report.</span></span>

    <span data-ttu-id="e8afa-162">結果は、HTML、Microsoft Word、Microsoft Excel など、さまざまな形式で保存できます。</span><span class="sxs-lookup"><span data-stu-id="e8afa-162">Results can be saved in different formats, such as HTML, Microsoft Word, and Microsoft Excel.</span></span>

## <span data-ttu-id="e8afa-163">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e8afa-163">Related topics</span></span>


[<span data-ttu-id="e8afa-164">MBAM 2.0 での BitLocker 準拠の監視とレポート</span><span class="sxs-lookup"><span data-stu-id="e8afa-164">Monitoring and Reporting BitLocker Compliance with MBAM 2.0</span></span>](monitoring-and-reporting-bitlocker-compliance-with-mbam-20-mbam-2.md)

 

 





