---
title: MBAM レポートを生成する方法
description: MBAM レポートを生成する方法
author: dansimp
ms.assetid: cdf4ae76-040c-447c-8736-c9e57068d221
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7f0b5a4e984d7a609eab7204e67f46042992f586
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824527"
---
# <span data-ttu-id="a8dd3-103">MBAM レポートを生成する方法</span><span class="sxs-lookup"><span data-stu-id="a8dd3-103">How to Generate MBAM Reports</span></span>


<span data-ttu-id="a8dd3-104">Microsoft BitLocker の管理と監視 (MBAM) BitLocker 暗号化の使用状況とコンプライアンスを監視するさまざまなレポートが生成されます。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-104">Microsoft BitLocker Administration and Monitoring (MBAM) generates various reports to monitor BitLocker encryption usage and compliance.</span></span> <span data-ttu-id="a8dd3-105">このトピックでは、MBAM 管理 web サイトを開く方法と、企業のコンプライアンス、個々のコンピューター、ハードウェアの互換性、およびキーの回復アクティビティについて MBAM レポートを生成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-105">This topic describes how to open the MBAM administration website and how to generate MBAM reports on enterprise compliance, individual computers, hardware compatibility, and key recovery activity.</span></span> <span data-ttu-id="a8dd3-106">MBAM レポートの詳細については、「 [MBAM レポートについ](understanding-mbam-reports-mbam-1.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-106">For more information about MBAM reports, see [Understanding MBAM Reports](understanding-mbam-reports-mbam-1.md).</span></span>

<span data-ttu-id="a8dd3-107">**注** レポートを実行するには、管理と監視サーバーの機能、コンプライアンスおよび監査データベース、コンプライアンスおよび監査レポートがインストールされているコンピューターで、**レポートユーザー**ロールのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-107">**Note** To run the reports, you must be a member of the **Report Users** role on the computers where you have installed the Administration and Monitoring Server features, Compliance and Audit Database, and Compliance and Audit Reports.</span></span>

 

**<span data-ttu-id="a8dd3-108">MBAM 管理 web サイトを開くには</span><span class="sxs-lookup"><span data-stu-id="a8dd3-108">To open the MBAM Administration website</span></span>**

1.  <span data-ttu-id="a8dd3-109">Web ブラウザーを開き、MBAM web サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-109">Open a web browser and navigate to the MBAM website.</span></span> <span data-ttu-id="a8dd3-110">Web サイトの既定の URL は、Microsoft BitLocker 管理および監視サーバーの\*http:// &lt; computername &gt; \*です。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-110">The default URL for the website is *http://&lt;computername&gt;* of the Microsoft BitLocker Administration and Monitoring server.</span></span>

    <span data-ttu-id="a8dd3-111">**注** MBAMadministration web サイトがポート80以外のポートにインストールされている場合は、URL にそのポート番号を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-111">**Note** If the MBAMadministration website was installed on a port other than port 80, you must specify that port number in the URL.</span></span> <span data-ttu-id="a8dd3-112">たとえば、 \*http:// &lt; computername &gt; : &lt; port &gt; \*とします。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-112">For example, *http://&lt;computername&gt;:&lt;port&gt;*.</span></span> <span data-ttu-id="a8dd3-113">インストール時に MBAMadministration web サイトのホスト名を指定した場合、URL は\*http:// &lt; hostname &gt; \*になります。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-113">If you specified a Host Name for the MBAMadministration website during the installation, the URL would be *http://&lt;hostname&gt;*.</span></span>

     

2.  <span data-ttu-id="a8dd3-114">ナビゲーションウィンドウで [**レポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-114">In the navigation pane, click **Reports**.</span></span> <span data-ttu-id="a8dd3-115">メインウィンドウで、レポートの種類のタブをクリックします。**エンタープライズコンプライアンスレポート**、**コンピューターのコンプライアンスレポート**、**ハードウェア監査レポート**、または**回復監査レポート**。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-115">In the main pane, click the tab for your report type: **Enterprise Compliance Report**, **Computer Compliance Report**, **Hardware Audit Report**, or **Recovery Audit Report**.</span></span>

    <span data-ttu-id="a8dd3-116">**注** 歴史的な MBAM クライアントデータは、コンプライアンスデータベースに保持されます。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-116">**Note** Historical MBAM Client data is retained in the compliance database.</span></span> <span data-ttu-id="a8dd3-117">この保持されたデータは、コンピューターが紛失したり盗まれたりした場合に必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-117">This retained data may be needed in case a computer is lost or stolen.</span></span> <span data-ttu-id="a8dd3-118">エンタープライズレポートを実行している場合、レポートデータの正確さを向上させるには、適切な開始日と終了日を使用して、レポートの期間を 1 ~ 2 週間に範囲指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-118">When running enterprise reports, you should use appropriate start and end dates to scope the time frames for the reports from one to two weeks to increase the reporting data accuracy.</span></span>

     

**<span data-ttu-id="a8dd3-119">企業のコンプライアンスレポートを生成するには</span><span class="sxs-lookup"><span data-stu-id="a8dd3-119">To generate an enterprise Compliance Report</span></span>**

1.  <span data-ttu-id="a8dd3-120">MBAMadministration web サイトで、ナビゲーションウィンドウの [**レポート**] をクリックし、[**エンタープライズコンプライアンスレポート**] タブをクリックして、レポートに適したフィルターを選択します。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-120">On the MBAMadministration website, click **Reports** in the navigation pane, then click the **Enterprise Compliance Report** tab and select the appropriate filters for your report.</span></span> <span data-ttu-id="a8dd3-121">[エンタープライズコンプライアンスレポート] では、次のフィルターを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-121">For the Enterprise Compliance Report, you can set the following filters.</span></span>

    -   <span data-ttu-id="a8dd3-122">**コンプライアンスの状態**。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-122">**Compliance Status**.</span></span> <span data-ttu-id="a8dd3-123">このフィルターを使用して、レポートに含めるコンプライアンスの状態の種類 (たとえば、準拠または非準拠) を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-123">Use this filter to specify the compliance status types (for example, Compliant or Noncompliant) to include in the report.</span></span>

    -   <span data-ttu-id="a8dd3-124">**エラー状態**。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-124">**Error State**.</span></span> <span data-ttu-id="a8dd3-125">このフィルターを使用して、エラーやエラーなど、レポートに含めるエラー状態の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-125">Use this filter to specify the Error State types, such as No Error or Error, to include in the report.</span></span>

2.  <span data-ttu-id="a8dd3-126">[**レポートの表示**] をクリックして、指定したレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-126">Click **View Report** to display the specified report.</span></span>

    <span data-ttu-id="a8dd3-127">レポートの結果は、HTML、Microsoft Word、Microsoft Excel などのさまざまなファイル形式で保存できます。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-127">The report results can be saved in any of several available file formats such as HTML, Microsoft Word, and Microsoft Excel.</span></span>

    <span data-ttu-id="a8dd3-128">**注** エンタープライズコンプライアンスレポートは、6時間ごとに実行される SQL ジョブによって生成されます。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-128">**Note** The Enterprise Compliance report is generated by a SQL job that runs every six hours.</span></span> <span data-ttu-id="a8dd3-129">そのため、最初にレポートを表示しようとしたときに、一部のデータが失われることがあります。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-129">Therefore, the first time you try to view the report you may find that some data is missing.</span></span>

     

3.  <span data-ttu-id="a8dd3-130">コンピューターのコンプライアンスレポートでコンピューターに関する情報を表示するには、コンピューター名を選びます。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-130">To view information about a computer in the Computer Compliance Report, select the computer name.</span></span>

4.  <span data-ttu-id="a8dd3-131">コンピューター名の横にあるプラス記号 (+) を選択すると、コンピューター上のボリュームに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-131">Select the plus sign (+) next to the computer name to view information about the volumes on the computer.</span></span>

**<span data-ttu-id="a8dd3-132">コンピューターのコンプライアンスレポートを生成するには</span><span class="sxs-lookup"><span data-stu-id="a8dd3-132">To generate the Computer Compliance Report</span></span>**

1.  <span data-ttu-id="a8dd3-133">MBAMadministration web サイトで、ナビゲーションウィンドウの [**レポート**] ノードを選択し、[**コンピューターのコンプライアンスレポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-133">In the MBAMadministration website, select the **Report** node in the navigation pane, and then select the **Computer Compliance Report**.</span></span> <span data-ttu-id="a8dd3-134">コンピューターのコンプライアンスレポートを使用して、**ユーザー名**または**コンピューター名**を検索します。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-134">Use the Computer Compliance report to search for **user name** or **computer name**.</span></span>

2.  <span data-ttu-id="a8dd3-135">[**レポートの表示**] をクリックして、コンピューターレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-135">Click **View Report** to view the computer report.</span></span>

    <span data-ttu-id="a8dd3-136">検索結果は、HTML、Microsoft Word、Microsoft Excel など、使用できるいくつかのファイル形式で保存できます。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-136">Results can be saved in any of several available file formats such as HTML, Microsoft Word, and Microsoft Excel.</span></span>

3.  <span data-ttu-id="a8dd3-137">コンピューターのコンプライアンスレポートにコンピューターの詳細情報を表示するには、コンピューター名を選びます。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-137">To display more information about a computer in the Computer Compliance Report, select the computer name.</span></span>

4.  <span data-ttu-id="a8dd3-138">コンピューター名の横にあるプラス記号 (+) を選択すると、コンピューター上のボリュームに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-138">Select the plus sign (+) next to the computer name to view information about the volumes on the computer.</span></span>

    <span data-ttu-id="a8dd3-139">**注** MBAM クライアントコンピューターは、コンピューターが MBAM ポリシー設定の要件を満たしているか、コンピューターのハードウェアモデルが [互換性のない] に設定されている場合に、準拠していると見なされます。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-139">**Note** An MBAM Client computer is considered compliant if the computer matches the requirements of the MBAM policy settings or the computer’s hardware model is set to incompatible.</span></span> <span data-ttu-id="a8dd3-140">そのため、コンピューターに関連付けられているディスクボリュームに関する詳細情報を表示している場合、ハードウェアの互換性のために BitLocker 暗号化から除外されたコンピューターは、ドライブのボリューム暗号化状態が準拠していない場合でも、準拠として表示される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-140">Therefore, when you are viewing detailed information about the disk volumes associated with the computer, computers that are exempt from BitLocker encryption due to hardware compatibility can be displayed as compliant even though their drive volume encryption status is displayed as noncompliant.</span></span>

     

**<span data-ttu-id="a8dd3-141">ハードウェア互換性監査レポートを生成するには</span><span class="sxs-lookup"><span data-stu-id="a8dd3-141">To generate the Hardware Compatibility Audit Report</span></span>**

1.  <span data-ttu-id="a8dd3-142">MBAMadministration web サイトで、ナビゲーションウィンドウから [**レポート**] ノードを選び、[**ハードウェア監査レポート**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-142">From the MBAMadministration website, select the **Report** node from the navigation pane, and then select the **Hardware Audit Report**.</span></span> <span data-ttu-id="a8dd3-143">ハードウェア監査レポートに適したフィルターを選択します。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-143">Select the appropriate filters for your Hardware Audit report.</span></span> <span data-ttu-id="a8dd3-144">ハードウェア監査レポートには、次の使用可能なフィルターが用意されています。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-144">The Hardware Audit report offers the following available filters:</span></span>

    -   <span data-ttu-id="a8dd3-145">**ユーザー (Domain\\User)**。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-145">**User (Domain\\User)**.</span></span> <span data-ttu-id="a8dd3-146">変更を加えたユーザーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-146">Specifies the name of the user who made a change.</span></span>

    -   <span data-ttu-id="a8dd3-147">**種類を変更**します。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-147">**Change Type**.</span></span> <span data-ttu-id="a8dd3-148">検索する変更の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-148">Specifies the type of changes you are looking for.</span></span>

    -   <span data-ttu-id="a8dd3-149">**開始日**です。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-149">**Start Date**.</span></span> <span data-ttu-id="a8dd3-150">報告する日付範囲の開始日の部分を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-150">Specifies the Start Date part of the date range that you want to report on.</span></span>

    -   <span data-ttu-id="a8dd3-151">**終了日**。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-151">**End Date**.</span></span> <span data-ttu-id="a8dd3-152">レポートする日付範囲の終了日の部分を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-152">Specifies the End Date part of the date range that you want to report on.</span></span>

2.  <span data-ttu-id="a8dd3-153">[**レポートの表示**] をクリックして、レポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-153">Click **View Report** to view the report.</span></span>

    <span data-ttu-id="a8dd3-154">検索結果は、HTML、Microsoft Word、Microsoft Excel などのさまざまなファイル形式で保存できます。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-154">Results can be saved in several available file formats such as HTML, Microsoft Word, and Microsoft Excel.</span></span>

**<span data-ttu-id="a8dd3-155">回復キーの監査レポートを生成するには</span><span class="sxs-lookup"><span data-stu-id="a8dd3-155">To generate the Recovery Key Audit Report</span></span>**

1.  <span data-ttu-id="a8dd3-156">MBAMadministration web サイトで、ナビゲーションウィンドウの [**レポート**] ノードを選択し、[**回復監査] レポート**を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-156">From the MBAMadministration website, select the **Report** node in the navigation pane, and then select the **Recovery Audit Report**.</span></span> <span data-ttu-id="a8dd3-157">回復キーの監査レポートのフィルターを選択します。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-157">Select the filters for your Recovery Key Audit report.</span></span> <span data-ttu-id="a8dd3-158">回復キーの監査で使用できるフィルターは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-158">The available filters for Recovery Key audits are as follows:</span></span>

    -   <span data-ttu-id="a8dd3-159">**要求者**。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-159">**Requestor**.</span></span> <span data-ttu-id="a8dd3-160">要求者のユーザー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-160">Specifies the user name of the requestor.</span></span> <span data-ttu-id="a8dd3-161">要求者は、ユーザーの代わりにキーにアクセスしたヘルプデスクのユーザーです。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-161">The requestor is the person in the help desk who accessed the key on behalf of a user.</span></span>

    -   <span data-ttu-id="a8dd3-162">**Requestee**。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-162">**Requestee**.</span></span> <span data-ttu-id="a8dd3-163">Requestee のユーザー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-163">Specifies the user name of the requestee.</span></span> <span data-ttu-id="a8dd3-164">Requestee は、回復キーを取得するためにヘルプデスクを呼び出したユーザーです。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-164">The requestee is the person who called the help desk to obtain a recovery key.</span></span>

    -   <span data-ttu-id="a8dd3-165">**要求の結果**要求の結果の種類を指定します。たとえば、成功または失敗。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-165">**Request Result** Specifies the request result types, such as: Success or Failed.</span></span> <span data-ttu-id="a8dd3-166">たとえば、失敗したキーアクセス試行を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-166">For example, you may want to view failed key access attempts.</span></span>

    -   <span data-ttu-id="a8dd3-167">**キーの種類**。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-167">**Key Type**.</span></span> <span data-ttu-id="a8dd3-168">キーの種類 (回復キーパスワード、TPM パスワードハッシュなど) を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-168">Specifies the Key Type, such as: Recovery Key Password or TPM Password Hash.</span></span>

    -   <span data-ttu-id="a8dd3-169">**開始日**です。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-169">**Start Date**.</span></span> <span data-ttu-id="a8dd3-170">日付範囲の開始日の部分を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-170">Specifies the Start Date part of the date range.</span></span>

    -   <span data-ttu-id="a8dd3-171">**終了日**。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-171">**End Date**.</span></span> <span data-ttu-id="a8dd3-172">日付範囲の終了日の部分を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-172">Specifies the End Date part of the date range.</span></span>

2.  <span data-ttu-id="a8dd3-173">[**レポートの表示**] をクリックして、レポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-173">Click **View Report** to display the report.</span></span>

    <span data-ttu-id="a8dd3-174">検索結果は、HTML、Microsoft Word、Microsoft Excel などのさまざまなファイル形式で保存できます。</span><span class="sxs-lookup"><span data-stu-id="a8dd3-174">Results can be saved in several available file formats such as HTML, Microsoft Word, and Microsoft Excel.</span></span>

## <span data-ttu-id="a8dd3-175">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a8dd3-175">Related topics</span></span>


[<span data-ttu-id="a8dd3-176">MBAM 1.0 での BitLocker 準拠の監視とレポート</span><span class="sxs-lookup"><span data-stu-id="a8dd3-176">Monitoring and Reporting BitLocker Compliance with MBAM 1.0</span></span>](monitoring-and-reporting-bitlocker-compliance-with-mbam-10.md)

 

 





