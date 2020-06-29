---
title: サーバー ログ レベルとデータベース パラメーターを変更する方法
description: サーバー ログ レベルとデータベース パラメーターを変更する方法
author: dansimp
ms.assetid: e3ebaee5-6c4c-4aa8-9766-c5aeb00f477a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bb35ac09c5e23f4847662171b68284f868e66dee
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818034"
---
# <span data-ttu-id="08808-103">サーバー ログ レベルとデータベース パラメーターを変更する方法</span><span class="sxs-lookup"><span data-stu-id="08808-103">How to Change the Server Logging Level and the Database Parameters</span></span>


<span data-ttu-id="08808-104">次の手順を使用して、Application Virtualization Server 管理コンソールからログレベルとデータベースログのパラメーターを変更できます。</span><span class="sxs-lookup"><span data-stu-id="08808-104">You can use the following procedures to change the logging level and the database log parameters from the Application Virtualization Server Management Console.</span></span>

<span data-ttu-id="08808-105">次のログレベルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="08808-105">The following logging levels are available:</span></span>

-   <span data-ttu-id="08808-106">トランザクションのみ</span><span class="sxs-lookup"><span data-stu-id="08808-106">Transaction Only</span></span>

-   <span data-ttu-id="08808-107">致命的なエラー</span><span class="sxs-lookup"><span data-stu-id="08808-107">Fatal Errors</span></span>

-   <span data-ttu-id="08808-108">エラー</span><span class="sxs-lookup"><span data-stu-id="08808-108">Errors</span></span>

-   <span data-ttu-id="08808-109">警告/エラー</span><span class="sxs-lookup"><span data-stu-id="08808-109">Warnings/Errors</span></span>

-   <span data-ttu-id="08808-110">情報/警告/エラー</span><span class="sxs-lookup"><span data-stu-id="08808-110">Info/Warnings/Errors</span></span>

-   <span data-ttu-id="08808-111">詳細</span><span class="sxs-lookup"><span data-stu-id="08808-111">Verbose</span></span>

<span data-ttu-id="08808-112">**注** **冗長**モードの使用時に生成されたログファイルのサイズにより、このレベルのログセットでは運用サーバーを実行しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="08808-112">**Note** Because of the size of the log file produced when you use **Verbose** mode, the recommendation is that you do not run production servers with this level of logging set.</span></span>

 

<span data-ttu-id="08808-113">データベースのログ記録パラメーターによって、データベースドライバーの種類、アクセス資格情報、ログデータベースの場所が決定されます。</span><span class="sxs-lookup"><span data-stu-id="08808-113">The database logging parameters determine the database driver type, access credentials, and location of the logging database.</span></span>

**<span data-ttu-id="08808-114">管理サーバーのログレベルを変更するには</span><span class="sxs-lookup"><span data-stu-id="08808-114">To change the logging level for Management Servers</span></span>**

1.  <span data-ttu-id="08808-115">[**サーバーグループ**] ノードをクリックして、サーバーグループを表示します。</span><span class="sxs-lookup"><span data-stu-id="08808-115">Click the **Server Groups** node to display the server groups.</span></span>

2.  <span data-ttu-id="08808-116">サーバーグループを右クリックし、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="08808-116">Right-click the server group, and select **Properties**.</span></span>

3.  <span data-ttu-id="08808-117">[**プロパティ**] ダイアログボックスで、[**ログ**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="08808-117">In the **Properties** dialog box, select the **Logging** tab.</span></span>

4.  <span data-ttu-id="08808-118">[**サーバーグループのプロパティ**] ダイアログボックスで、サーバーを選び、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08808-118">In the **Server Group Properties** dialog box, select the server and then click **Edit**.</span></span>

5.  <span data-ttu-id="08808-119">[ **Add/Edit Log Module** ] ダイアログボックスで、[ **Event Type** ] ドロップダウンリストから [logging level] を選びます。</span><span class="sxs-lookup"><span data-stu-id="08808-119">In the **Add/Edit Log Module** dialog box, select the logging level from the **Event Type** drop-down list.</span></span>

6.  <span data-ttu-id="08808-120">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08808-120">Click **OK**.</span></span>

7.  <span data-ttu-id="08808-121">[**サーバーグループのプロパティ**] ダイアログボックスで、[ **OK]** または [**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08808-121">In the **Server Group Properties** dialog box, click **OK** or **Apply**.</span></span>

**<span data-ttu-id="08808-122">ストリーミングサーバーのログレベルを変更するには</span><span class="sxs-lookup"><span data-stu-id="08808-122">To change the logging level for Streaming Servers</span></span>**

1.  <span data-ttu-id="08808-123">ログレベルを変更するには、次のレジストリキーの値を編集します。</span><span class="sxs-lookup"><span data-stu-id="08808-123">Edit the following registry key value to change the logging level:</span></span>

    -   <span data-ttu-id="08808-124">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\DistributionServer\\LogLevel</span><span class="sxs-lookup"><span data-stu-id="08808-124">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\DistributionServer\\LogLevel</span></span>

2.  <span data-ttu-id="08808-125">次の値のいずれかを選択して、ログレベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="08808-125">Select one of the following values to set the logging level.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="08808-126">値</span><span class="sxs-lookup"><span data-stu-id="08808-126">Value</span></span></th>
    <th align="left"><span data-ttu-id="08808-127">ログレベル</span><span class="sxs-lookup"><span data-stu-id="08808-127">Logging Level</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="08808-128">0</span><span class="sxs-lookup"><span data-stu-id="08808-128">0</span></span></p></td>
    <td align="left"><p><span data-ttu-id="08808-129">トランザクションのみ</span><span class="sxs-lookup"><span data-stu-id="08808-129">Transactions Only</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="08808-130">件</span><span class="sxs-lookup"><span data-stu-id="08808-130">1</span></span></p></td>
    <td align="left"><p><span data-ttu-id="08808-131">致命的なエラー</span><span class="sxs-lookup"><span data-stu-id="08808-131">Fatal Errors</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="08808-132">両面</span><span class="sxs-lookup"><span data-stu-id="08808-132">2</span></span></p></td>
    <td align="left"><p><span data-ttu-id="08808-133">エラー</span><span class="sxs-lookup"><span data-stu-id="08808-133">Errors</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="08808-134">-</span><span class="sxs-lookup"><span data-stu-id="08808-134">3</span></span></p></td>
    <td align="left"><p><span data-ttu-id="08808-135">警告/エラー</span><span class="sxs-lookup"><span data-stu-id="08808-135">Warnings/Errors</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="08808-136">4d</span><span class="sxs-lookup"><span data-stu-id="08808-136">4</span></span></p></td>
    <td align="left"><p><span data-ttu-id="08808-137">情報/警告/エラー</span><span class="sxs-lookup"><span data-stu-id="08808-137">Information/ Warnings/Errors</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="08808-138">個</span><span class="sxs-lookup"><span data-stu-id="08808-138">5</span></span></p></td>
    <td align="left"><p><span data-ttu-id="08808-139">詳細</span><span class="sxs-lookup"><span data-stu-id="08808-139">Verbose</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

**<span data-ttu-id="08808-140">データベースログのパラメーターを変更するには</span><span class="sxs-lookup"><span data-stu-id="08808-140">To change database log parameters</span></span>**

1.  <span data-ttu-id="08808-141">[**サーバーグループ**] ノードをクリックして、サーバーグループを表示します。</span><span class="sxs-lookup"><span data-stu-id="08808-141">Click the **Server Groups** node to display the server groups.</span></span>

2.  <span data-ttu-id="08808-142">サーバーグループを右クリックし、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="08808-142">Right-click the server group, and select **Properties**.</span></span>

3.  <span data-ttu-id="08808-143">[**プロパティ**] ダイアログボックスで、[**ログ**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="08808-143">In the **Properties** dialog box, select the **Logging** tab.</span></span>

4.  <span data-ttu-id="08808-144">[**サーバーグループのプロパティ**] ダイアログボックスで、サーバーを選び、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08808-144">In the **Server Group Properties** dialog box, select the server and then click **Edit**.</span></span>

5.  <span data-ttu-id="08808-145">[ **Add/Edit Log Module** ] ダイアログボックスで、[**データベースドライバー** ] ドロップダウンリストからデータベースドライバーを選びます。</span><span class="sxs-lookup"><span data-stu-id="08808-145">In the **Add/Edit Log Module** dialog box, select a database driver from the **Database Driver** drop-down list.</span></span>

6.  <span data-ttu-id="08808-146">**DNS ホスト名**を入力します。</span><span class="sxs-lookup"><span data-stu-id="08808-146">Enter a **DNS Host Name**.</span></span>

7.  <span data-ttu-id="08808-147">[**ポートを動的に決定**する] チェックボックスをオンにするか、[**ポート**] フィールドにポート番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="08808-147">Click the **Dynamically Determine Port** check box, or enter a port number in the **Port** field.</span></span>

8.  <span data-ttu-id="08808-148">対応するフィールドに**サービス名**を入力します。</span><span class="sxs-lookup"><span data-stu-id="08808-148">Enter a **Service Name** in the corresponding field.</span></span>

9.  <span data-ttu-id="08808-149">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08808-149">Click **OK**.</span></span>

10. <span data-ttu-id="08808-150">[**サーバーグループのプロパティ**] ダイアログボックスで、[ **OK]** または [**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08808-150">On the **Server Group Properties** dialog box, click **OK** or **Apply**.</span></span>

## <span data-ttu-id="08808-151">関連トピック</span><span class="sxs-lookup"><span data-stu-id="08808-151">Related topics</span></span>


[<span data-ttu-id="08808-152">サーバー管理コンソールで Application Virtualization システムをカスタマイズする方法</span><span class="sxs-lookup"><span data-stu-id="08808-152">How to Customize an Application Virtualization System in the Server Management Console</span></span>](how-to-customize-an-application-virtualization-system-in-the-server-management-console.md)

 

 





