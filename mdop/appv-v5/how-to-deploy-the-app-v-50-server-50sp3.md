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
# <span data-ttu-id="afddc-103">App-V 5.0 Server を展開する方法</span><span class="sxs-lookup"><span data-stu-id="afddc-103">How to Deploy the App-V 5.0 Server</span></span>


<span data-ttu-id="afddc-104">次の手順を使用して、App-v 5.0 サーバーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="afddc-104">Use the following procedure to install the App-V 5.0 server.</span></span> <span data-ttu-id="afddc-105">App-v 5.0 SP3 サーバーの展開について詳しくは、「[アプリ-v 5.0 Sp3 につい](about-app-v-50-sp3.md#bkmk-migrate-to-50sp3)て」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="afddc-105">For information about deploying the App-V 5.0 SP3 Server, see [About App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-migrate-to-50sp3).</span></span>

**<span data-ttu-id="afddc-106">始める前に:</span><span class="sxs-lookup"><span data-stu-id="afddc-106">Before you start:</span></span>**

-   <span data-ttu-id="afddc-107">必要なソフトウェアがインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="afddc-107">Ensure that you’ve installed prerequisite software.</span></span> <span data-ttu-id="afddc-108">「 [App-v 5.0 の前提条件](app-v-50-prerequisites.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afddc-108">See [App-V 5.0 Prerequisites](app-v-50-prerequisites.md).</span></span>

-   <span data-ttu-id="afddc-109">「 [App-V 5.0 セキュリティに関する考慮事項](app-v-50-security-considerations.md)」のサーバーセクションを確認します。</span><span class="sxs-lookup"><span data-stu-id="afddc-109">Review the server section of [App-V 5.0 Security Considerations](app-v-50-security-considerations.md).</span></span>

-   <span data-ttu-id="afddc-110">各コンポーネントをホストするポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="afddc-110">Specify a port where each component will be hosted.</span></span>

-   <span data-ttu-id="afddc-111">ファイアウォール規則を追加して、着信要求に対して指定されたポートへのアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="afddc-111">Add firewall rules to allow incoming requests to access the specified ports.</span></span>

-   <span data-ttu-id="afddc-112">Windows インストーラーの代わりに SQL スクリプトを使用して管理データベースまたはレポートデータベースを設定する場合は、管理サーバーまたはレポートサーバーをインストールする前に SQL スクリプトを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="afddc-112">If you use SQL scripts, instead of the Windows Installer, to set up the Management database or Reporting database, you must run the SQL scripts before installing the Management Server or Reporting Server.</span></span> <span data-ttu-id="afddc-113">[SQL スクリプトを使用して App-v データベースを展開する方法に](how-to-deploy-the-app-v-databases-by-using-sql-scripts.md)ついて説明します。</span><span class="sxs-lookup"><span data-stu-id="afddc-113">See [How to Deploy the App-V Databases by Using SQL Scripts](how-to-deploy-the-app-v-databases-by-using-sql-scripts.md).</span></span>

**<span data-ttu-id="afddc-114">App-v 5.0 サーバーをインストールするには</span><span class="sxs-lookup"><span data-stu-id="afddc-114">To install the App-V 5.0 server</span></span>**

1. <span data-ttu-id="afddc-115">アプリをインストールするコンピューターに、App-v 5.0 サーバーのインストールファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="afddc-115">Copy the App-V 5.0 server installation files to the computer on which you want to install it.</span></span>

2. <span data-ttu-id="afddc-116">**appv\_server\_setup.exe**を右クリックし、管理者として実行して、app-v 5.0 server のインストールを開始し、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="afddc-116">Start the App-V 5.0 server installation by right-clicking and running **appv\_server\_setup.exe** as an administrator, and then click **Install**.</span></span>

3. <span data-ttu-id="afddc-117">ライセンス条項を確認して同意し、Microsoft 更新プログラムを有効にするかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="afddc-117">Review and accept the license terms, and choose whether to enable Microsoft updates.</span></span>

4. <span data-ttu-id="afddc-118">[**機能の選択**] ページで、次のすべてのコンポーネントを選択します。</span><span class="sxs-lookup"><span data-stu-id="afddc-118">On the **Feature Selection** page, select all of the following components.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="afddc-119">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="afddc-119">Component</span></span></th>
   <th align="left"><span data-ttu-id="afddc-120">説明</span><span class="sxs-lookup"><span data-stu-id="afddc-120">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="afddc-121">管理サーバー</span><span class="sxs-lookup"><span data-stu-id="afddc-121">Management server</span></span></p></td>
   <td align="left"><p><span data-ttu-id="afddc-122">App-v インフラストラクチャの全体的な管理機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="afddc-122">Provides overall management functionality for the App-V infrastructure.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="afddc-123">管理データベース</span><span class="sxs-lookup"><span data-stu-id="afddc-123">Management database</span></span></p></td>
   <td align="left"><p><span data-ttu-id="afddc-124">App-v 管理用のデータベース展開が容易になります。</span><span class="sxs-lookup"><span data-stu-id="afddc-124">Facilitates database predeployments for App-V management.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="afddc-125">発行サーバー</span><span class="sxs-lookup"><span data-stu-id="afddc-125">Publishing server</span></span></p></td>
   <td align="left"><p><span data-ttu-id="afddc-126">仮想アプリケーションのホスティング機能とストリーミング機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="afddc-126">Provides hosting and streaming functionality for virtual applications.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="afddc-127">レポートサーバー</span><span class="sxs-lookup"><span data-stu-id="afddc-127">Reporting server</span></span></p></td>
   <td align="left"><p><span data-ttu-id="afddc-128">App-v 5.0 reporting services を提供します。</span><span class="sxs-lookup"><span data-stu-id="afddc-128">Provides App-V 5.0 reporting services.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="afddc-129">レポートデータベース</span><span class="sxs-lookup"><span data-stu-id="afddc-129">Reporting database</span></span></p></td>
   <td align="left"><p><span data-ttu-id="afddc-130">App-v レポート用のデータベース展開が容易になります。</span><span class="sxs-lookup"><span data-stu-id="afddc-130">Facilitates database predeployments for App-V reporting.</span></span></p></td>
   </tr>
   </tbody>
   </table>

     

5. <span data-ttu-id="afddc-131">[**インストールの場所**] ページで、選択したコンポーネントをインストールする既定の場所をそのまま使うか、**インストール場所**の行に新しいパスを入力して場所を変更します。</span><span class="sxs-lookup"><span data-stu-id="afddc-131">On the **Installation Location** page, accept the default location where the selected components will be installed, or change the location by typing a new path on the **Installation Location** line.</span></span>

6. <span data-ttu-id="afddc-132">[**新しい管理データベースの新規作成**] ページで、以下の適切なオプションを選択して、 **Microsoft SQL Server インスタンス**と**管理サーバーデータベース**を構成します。</span><span class="sxs-lookup"><span data-stu-id="afddc-132">On the initial **Create New Management Database** page, configure the **Microsoft SQL Server instance** and **Management Server database** by selecting the appropriate option below.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="afddc-133">メソッド</span><span class="sxs-lookup"><span data-stu-id="afddc-133">Method</span></span></th>
   <th align="left"><span data-ttu-id="afddc-134">必要な作業</span><span class="sxs-lookup"><span data-stu-id="afddc-134">What you need to do</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="afddc-135">ユーザー設定の Microsoft SQL Server インスタンスを使用している。</span><span class="sxs-lookup"><span data-stu-id="afddc-135">You are using a custom Microsoft SQL Server instance.</span></span></p></td>
   <td align="left"><p><span data-ttu-id="afddc-136">[カスタムインスタンスの使用] を選択し、 <strong> </strong> インスタンスの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="afddc-136">Select <strong>Use the custom instance</strong>, and type the name of the instance.</span></span></p>
   <p><span data-ttu-id="afddc-137">指定するには、INSTANCENAME という形式を使い <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="afddc-137">Use the format <strong>INSTANCENAME</strong>.</span></span> <span data-ttu-id="afddc-138">想定されているインストール場所はローカルコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="afddc-138">The assumed installation location is the local computer.</span></span></p>
   <p><span data-ttu-id="afddc-139">サポートされていません: format <strong> ServerName の </strong> &lt; 厳密な &gt; インスタンスを使用するサーバー名 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="afddc-139">Not supported: A server name using the format <strong>ServerName</strong>&lt;strong&gt;INSTANCE</strong>.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="afddc-140">ユーザー設定のデータベース名を使用している。</span><span class="sxs-lookup"><span data-stu-id="afddc-140">You are using a custom database name.</span></span></p></td>
   <td align="left"><p><span data-ttu-id="afddc-141">[ <strong> カスタム構成] を選択 </strong> し、データベース名を入力します。</span><span class="sxs-lookup"><span data-stu-id="afddc-141">Select <strong>Custom configuration</strong> and type the database name.</span></span></p>
   <p><span data-ttu-id="afddc-142">データベース名が一意である必要があります。インストールに失敗します。</span><span class="sxs-lookup"><span data-stu-id="afddc-142">The database name must be unique, or the installation will fail.</span></span></p></td>
   </tr>
   </tbody>
   </table>

     

7. <span data-ttu-id="afddc-143">[**構成**] ページで、既定値のまま [**このローカルコンピューターを使用する**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="afddc-143">On the **Configure** page, accept the default value **Use this local computer**.</span></span>

   **<span data-ttu-id="afddc-144">注</span><span class="sxs-lookup"><span data-stu-id="afddc-144">Note</span></span>**  
   <span data-ttu-id="afddc-145">管理サーバーと管理データベースを並行してインストールする場合、このページの一部のオプションは使用できません。</span><span class="sxs-lookup"><span data-stu-id="afddc-145">If you are installing the Management server and Management database side by side, some options on this page are not available.</span></span> <span data-ttu-id="afddc-146">この場合、適切なオプションが既定で選択されていますが、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="afddc-146">In this case, the appropriate options are selected by default and cannot be changed.</span></span>

     

8. <span data-ttu-id="afddc-147">[**新しいレポートデータベースの新規作成**] ページで、以下の適切なオプションを選択して、 **Microsoft SQL Server インスタンス**と**レポートサーバーデータベース**を構成します。</span><span class="sxs-lookup"><span data-stu-id="afddc-147">On the initial **Create New Reporting Database** page, configure the **Microsoft SQL Server instance** and **Reporting Server database** by selecting the appropriate option below.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="afddc-148">メソッド</span><span class="sxs-lookup"><span data-stu-id="afddc-148">Method</span></span></th>
   <th align="left"><span data-ttu-id="afddc-149">必要な作業</span><span class="sxs-lookup"><span data-stu-id="afddc-149">What you need to do</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="afddc-150">ユーザー設定の Microsoft SQL Server インスタンスを使用している。</span><span class="sxs-lookup"><span data-stu-id="afddc-150">You are using a custom Microsoft SQL Server instance.</span></span></p></td>
   <td align="left"><p><span data-ttu-id="afddc-151">[カスタムインスタンスの使用] を選択し、 <strong> </strong> インスタンスの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="afddc-151">Select <strong>Use the custom instance</strong>, and type the name of the instance.</span></span></p>
   <p><span data-ttu-id="afddc-152">指定するには、INSTANCENAME という形式を使い <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="afddc-152">Use the format <strong>INSTANCENAME</strong>.</span></span> <span data-ttu-id="afddc-153">想定されているインストール場所はローカルコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="afddc-153">The assumed installation location is the local computer.</span></span></p>
   <p><span data-ttu-id="afddc-154">サポートされていません: format <strong> ServerName の </strong> &lt; 厳密な &gt; インスタンスを使用するサーバー名 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="afddc-154">Not supported: A server name using the format <strong>ServerName</strong>&lt;strong&gt;INSTANCE</strong>.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="afddc-155">ユーザー設定のデータベース名を使用している。</span><span class="sxs-lookup"><span data-stu-id="afddc-155">You are using a custom database name.</span></span></p></td>
   <td align="left"><p><span data-ttu-id="afddc-156">[ <strong> カスタム構成] を選択 </strong> し、データベース名を入力します。</span><span class="sxs-lookup"><span data-stu-id="afddc-156">Select <strong>Custom configuration</strong> and type the database name.</span></span></p>
   <p><span data-ttu-id="afddc-157">データベース名が一意である必要があります。インストールに失敗します。</span><span class="sxs-lookup"><span data-stu-id="afddc-157">The database name must be unique, or the installation will fail.</span></span></p></td>
   </tr>
   </tbody>
   </table>

     

9. <span data-ttu-id="afddc-158">[**構成**] ページで、既定値のままにします (**このローカルコンピューターを使用**します)。</span><span class="sxs-lookup"><span data-stu-id="afddc-158">On the **Configure** page, accept the default value: **Use this local computer**.</span></span>

   **<span data-ttu-id="afddc-159">注</span><span class="sxs-lookup"><span data-stu-id="afddc-159">Note</span></span>**  
   <span data-ttu-id="afddc-160">管理サーバーと管理データベースを並行してインストールする場合、このページの一部のオプションは使用できません。</span><span class="sxs-lookup"><span data-stu-id="afddc-160">If you are installing the Management server and Management database side by side, some options on this page are not available.</span></span> <span data-ttu-id="afddc-161">この場合、適切なオプションが既定で選択されていますが、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="afddc-161">In this case, the appropriate options are selected by default and cannot be changed.</span></span>

     

10. <span data-ttu-id="afddc-162">[**構成**(Management Server 構成)] ページで、次を指定します。</span><span class="sxs-lookup"><span data-stu-id="afddc-162">On the **Configure** (Management Server Configuration) page, specify the following:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="afddc-163">構成する項目</span><span class="sxs-lookup"><span data-stu-id="afddc-163">Item to configure</span></span></th>
    <th align="left"><span data-ttu-id="afddc-164">説明と例</span><span class="sxs-lookup"><span data-stu-id="afddc-164">Description and examples</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="afddc-165">App-v 環境を管理するための十分な権限を持つ広告グループを入力します。</span><span class="sxs-lookup"><span data-stu-id="afddc-165">Type the AD group with sufficient permissions to manage the App-V environment.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="afddc-166">例: myの myuser</span><span class="sxs-lookup"><span data-stu-id="afddc-166">Example: MyDomain\MyUser</span></span></p>
    <p><span data-ttu-id="afddc-167">インストール後、管理コンソールを使用して、ユーザーまたはグループを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="afddc-167">After installation, you can add additional users or groups by using the Management console.</span></span> <span data-ttu-id="afddc-168">ただし、グローバルセキュリティグループと Active Directory ドメインサービス (AD DS) 配布グループはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="afddc-168">However, global security groups and Active Directory Domain Services (AD DS) distribution groups are not supported.</span></span> <span data-ttu-id="afddc-169"><strong> </strong> <strong> </strong> この操作を実行するには、ドメインローカルグループまたはユニバーサルグループを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="afddc-169">You must use <strong>Domain local</strong> or <strong>Universal</strong> groups are required to perform this action.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong><span data-ttu-id="afddc-170">Web サイト名 </strong> : 発行サービスを実行するために使用されるカスタム名を指定します。</span><span class="sxs-lookup"><span data-stu-id="afddc-170">Website name</strong>: Specify the custom name that will be used to run the publishing service.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="afddc-171">独自の名前がない場合は、変更を加えないでください。</span><span class="sxs-lookup"><span data-stu-id="afddc-171">If you do not have a custom name, do not make any changes.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="afddc-172">ポート </strong> のバインド: app-v で使用される一意のポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="afddc-172">Port binding</strong>: Specify a unique port number that will be used by App-V.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="afddc-173">例: <strong> 12345</span><span class="sxs-lookup"><span data-stu-id="afddc-173">Example: <strong>12345</span></span></strong></p>
    <p><span data-ttu-id="afddc-174">指定したポートが別の web サイトで使用されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="afddc-174">Ensure that the port specified is not being used by another website.</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

11. <span data-ttu-id="afddc-175">[**発行サーバー構成**の**構成**] ページで、次を指定します。</span><span class="sxs-lookup"><span data-stu-id="afddc-175">On the **Configure** **Publishing Server Configuration** page, specify the following:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="afddc-176">構成する項目</span><span class="sxs-lookup"><span data-stu-id="afddc-176">Item to configure</span></span></th>
    <th align="left"><span data-ttu-id="afddc-177">説明と例</span><span class="sxs-lookup"><span data-stu-id="afddc-177">Description and examples</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="afddc-178">管理サービスの URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="afddc-178">Specify the URL for the management service.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="afddc-179">次<a href="http://localhost:12345" data-raw-source="http://localhost:12345">http://localhost:12345</span><span class="sxs-lookup"><span data-stu-id="afddc-179">Example: <a href="http://localhost:12345" data-raw-source="http://localhost:12345">http://localhost:12345</span></span></a></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong><span data-ttu-id="afddc-180">Web サイト名 </strong> : 発行サービスを実行するために使用されるカスタム名を指定します。</span><span class="sxs-lookup"><span data-stu-id="afddc-180">Website name</strong>: Specify the custom name that will be used to run the publishing service.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="afddc-181">独自の名前がない場合は、変更を加えないでください。</span><span class="sxs-lookup"><span data-stu-id="afddc-181">If you do not have a custom name, do not make any changes.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="afddc-182">ポート </strong> のバインド: app-v で使用される一意のポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="afddc-182">Port binding</strong>: Specify a unique port number that will be used by App-V.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="afddc-183">例: 54321</span><span class="sxs-lookup"><span data-stu-id="afddc-183">Example: 54321</span></span></p>
    <p><span data-ttu-id="afddc-184">指定したポートが別の web サイトで使用されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="afddc-184">Ensure that the port specified is not being used by another website.</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

12. <span data-ttu-id="afddc-185">[ **Reporting Server** ] ページで、次を指定します。</span><span class="sxs-lookup"><span data-stu-id="afddc-185">On the **Reporting Server** page, specify the following:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="afddc-186">構成する項目</span><span class="sxs-lookup"><span data-stu-id="afddc-186">Item to configure</span></span></th>
    <th align="left"><span data-ttu-id="afddc-187">説明と例</span><span class="sxs-lookup"><span data-stu-id="afddc-187">Description and examples</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="afddc-188">Web サイト名 </strong> : レポートサービスの実行に使用されるカスタム名を指定します。</span><span class="sxs-lookup"><span data-stu-id="afddc-188">Website name</strong>: Specify the custom name that will be used to run the Reporting Service.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="afddc-189">独自の名前がない場合は、変更を加えないでください。</span><span class="sxs-lookup"><span data-stu-id="afddc-189">If you do not have a custom name, do not make any changes.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong><span data-ttu-id="afddc-190">ポート </strong> のバインド: app-v で使用される一意のポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="afddc-190">Port binding</strong>: Specify a unique port number that will be used by App-V.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="afddc-191">例: 55555</span><span class="sxs-lookup"><span data-stu-id="afddc-191">Example: 55555</span></span></p>
    <p><span data-ttu-id="afddc-192">指定したポートが別の web サイトで使用されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="afddc-192">Ensure that the port specified is not being used by another website.</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

13. <span data-ttu-id="afddc-193">インストールを開始するには、[**準備完了**] ページで [**インストール**] をクリックし、**完成**したページで [**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="afddc-193">To start the installation, click **Install** on the **Ready** page, and then click **Close** on the **Finished** page.</span></span>

14. <span data-ttu-id="afddc-194">セットアップが正常に完了したことを確認するには、web ブラウザーを開いて、次の URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="afddc-194">To verify that the setup completed successfully, open a web browser, and type the following URL:</span></span>

    <span data-ttu-id="afddc-195">**http:// &lt;管理サーバーのコンピューター名 &gt; : &lt; 管理サービスのポート番号 &gt; /Console.html**。</span><span class="sxs-lookup"><span data-stu-id="afddc-195">**http://&lt;Management server machine name&gt;:&lt;Management service port number&gt;/Console.html**.</span></span>

    <span data-ttu-id="afddc-196">例: **http://localhost:12345/console.html** 。</span><span class="sxs-lookup"><span data-stu-id="afddc-196">Example: **http://localhost:12345/console.html**.</span></span> <span data-ttu-id="afddc-197">インストールに成功した場合、App-v 管理コンソールにエラーは表示されません。</span><span class="sxs-lookup"><span data-stu-id="afddc-197">If the installation succeeded, the App-V Management console is displayed with no errors.</span></span>

    <span data-ttu-id="afddc-198">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="afddc-198">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="afddc-199">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="afddc-199">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="afddc-200">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="afddc-200">Got an App-V issue?</span></span>** <span data-ttu-id="afddc-201">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="afddc-201">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="afddc-202">関連トピック</span><span class="sxs-lookup"><span data-stu-id="afddc-202">Related topics</span></span>


[<span data-ttu-id="afddc-203">APP-V 5.0 の展開</span><span class="sxs-lookup"><span data-stu-id="afddc-203">Deploying App-V 5.0</span></span>](deploying-app-v-50.md)

[<span data-ttu-id="afddc-204">管理とレポート サービスとは別のコンピューターに管理とレポートのデータベースをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="afddc-204">How to Install the Management and Reporting Databases on Separate Computers from the Management and Reporting Services</span></span>](how-to-install-the-management-and-reporting-databases-on-separate-computers-from-the-management-and-reporting-services.md)

[<span data-ttu-id="afddc-205">リモート コンピューターに公開サーバーをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="afddc-205">How to Install the Publishing Server on a Remote Computer</span></span>](how-to-install-the-publishing-server-on-a-remote-computer.md)

[<span data-ttu-id="afddc-206">スクリプトを使用して APP-V 5.0 Server を展開する方法</span><span class="sxs-lookup"><span data-stu-id="afddc-206">How to Deploy the App-V 5.0 Server Using a Script</span></span>](how-to-deploy-the-app-v-50-server-using-a-script.md)

[<span data-ttu-id="afddc-207">PowerShell を使用して App-V 5.0 Client のレポート機能を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="afddc-207">How to Enable Reporting on the App-V 5.0 Client by Using PowerShell</span></span>](how-to-enable-reporting-on-the-app-v-50-client-by-using-powershell.md)

 

 





