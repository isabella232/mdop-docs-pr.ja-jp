---
title: ログ レポート レベルの変更およびログ ファイルのリセットを行う方法
description: ログ レポート レベルの変更およびログ ファイルのリセットを行う方法
author: dansimp
ms.assetid: 9561d6fb-b35c-491b-a355-000064583194
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7307dee0030d9c03a8107d9d0ceef2086a94df07
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818047"
---
# <span data-ttu-id="461e5-103">ログ レポート レベルの変更およびログ ファイルのリセットを行う方法</span><span class="sxs-lookup"><span data-stu-id="461e5-103">How to Change the Log Reporting Levels and Reset the Log Files</span></span>


<span data-ttu-id="461e5-104">次の手順を使用して、Application Virtualization 管理コンソールの**Application virtualization**ノードからログレポートレベルを変更できます。</span><span class="sxs-lookup"><span data-stu-id="461e5-104">You can use the following procedure to change the log reporting level from the **Application Virtualization** node in the Application Virtualization Management Console.</span></span> <span data-ttu-id="461e5-105">ログファイルが最大サイズ (既定では 256 MB) に達すると、次にログへの書き込みが行われたときにリセットが強制されます。</span><span class="sxs-lookup"><span data-stu-id="461e5-105">When the log file reaches the maximum size (default is 256 MB), a reset is forced when the next write to the log occurs.</span></span> <span data-ttu-id="461e5-106">リセットすると、新しいログファイルが作成され、古いファイルはバックアップとして名前が変更されます。</span><span class="sxs-lookup"><span data-stu-id="461e5-106">A reset causes a new log file to be created, and the old file is renamed as a backup.</span></span>

**<span data-ttu-id="461e5-107">ログレポートのレベルを変更するには</span><span class="sxs-lookup"><span data-stu-id="461e5-107">To change the log reporting level</span></span>**

1.  <span data-ttu-id="461e5-108">[ **Application Virtualization** ] ノードを右クリックし、ポップアップメニューから [**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="461e5-108">Right-click the **Application Virtualization** node, and select **Properties** from the pop-up menu.</span></span>

2.  <span data-ttu-id="461e5-109">[**プロパティ**] ダイアログボックスの [全般] タブで、[**ログレベル**] ドロップダウンリストから必要**な**ログレベルを選びます。</span><span class="sxs-lookup"><span data-stu-id="461e5-109">On the **General** tab in the **Properties** dialog box, from the **Log Level** drop-down list, select the desired log level.</span></span>

    <span data-ttu-id="461e5-110">**注** ログレベルとして [**詳細**] を選択した場合、ログファイルは非常に早く大きくなります。</span><span class="sxs-lookup"><span data-stu-id="461e5-110">**Note** If you choose **Verbose** as the logging level, the log files will grow large very quickly.</span></span> <span data-ttu-id="461e5-111">これにより、クライアントのパフォーマンスが妨げられる可能性があります。そのためには、特定の問題を診断する目的でのみこのログレベルを使用することをお勧め</span><span class="sxs-lookup"><span data-stu-id="461e5-111">This might inhibit client performance, so best practice is to use this log level only for diagnosing specific problems.</span></span>

     

3.  <span data-ttu-id="461e5-112">[**プロパティ**] ダイアログボックスの [全般] タブで、[**システムログレベル**] ドロップダウンリストから必要**な**ログレベルを選びます。</span><span class="sxs-lookup"><span data-stu-id="461e5-112">On the **General** tab in the **Properties** dialog box, from the **System Log Level** drop-down list, select the desired log level.</span></span>

    <span data-ttu-id="461e5-113">**注** システム**ログレベル**設定は、システムイベントログに送信されるメッセージのレベルを制御します。</span><span class="sxs-lookup"><span data-stu-id="461e5-113">**Note** The **System Log Level** setting controls the level of messages sent to the system event log.</span></span> <span data-ttu-id="461e5-114">ログに記録されたメッセージは、クライアントイベントログに記録されるメッセージと同じですが、別の場所に格納されています。</span><span class="sxs-lookup"><span data-stu-id="461e5-114">The logged messages are identical to the messages that get logged to the client event log, but they are stored in a different location.</span></span>

     

4.  <span data-ttu-id="461e5-115">[ **OK]** または [**適用**] をクリックして設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="461e5-115">Click **OK** or **Apply** to change the setting.</span></span>

**<span data-ttu-id="461e5-116">ログファイルをリセットするには</span><span class="sxs-lookup"><span data-stu-id="461e5-116">To reset the log file</span></span>**

1.  <span data-ttu-id="461e5-117">[ **Application Virtualization** ] ノードを右クリックし、ポップアップメニューから [**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="461e5-117">Right-click the **Application Virtualization** node, and select **Properties** from the pop-up menu.</span></span>

2.  <span data-ttu-id="461e5-118">[**プロパティ**] ダイアログボックスの [**全般**] タブで、[**ログのリセット**] をクリックして現在のログファイルをバックアップし、新しいログファイルをすぐに開始します。</span><span class="sxs-lookup"><span data-stu-id="461e5-118">On the **General** tab in the **Properties** dialog box, click **Reset Log** to back up the current log file and immediately start a new log file.</span></span> <span data-ttu-id="461e5-119">バックアップログファイルは、同じフォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="461e5-119">The backup log files are stored in the same folder.</span></span>

3.  <span data-ttu-id="461e5-120">[ **OK]** または [**適用**] をクリックして設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="461e5-120">Click **OK** or **Apply** to change the setting.</span></span>

## <span data-ttu-id="461e5-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="461e5-121">Related topics</span></span>


[<span data-ttu-id="461e5-122">Application Virtualization Client Management Console でクライアントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="461e5-122">How to Configure the Client in the Application Virtualization Client Management Console</span></span>](how-to-configure-the-client-in-the-application-virtualization-client-management-console.md)

[<span data-ttu-id="461e5-123">Application Virtualization Client のユーザー アクセス許可</span><span class="sxs-lookup"><span data-stu-id="461e5-123">User Access Permissions in Application Virtualization Client</span></span>](user-access-permissions-in-application-virtualization-client.md)

 

 





