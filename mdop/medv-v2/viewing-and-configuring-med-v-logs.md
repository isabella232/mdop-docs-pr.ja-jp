---
title: MED-V ログの表示と構成
description: MED-V ログの表示と構成
author: dansimp
ms.assetid: a15537ce-981d-4f55-9c3c-e7fbf94b8fe5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7984cec072827136db9ea52a535c0ea44c6bc2c3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823727"
---
# <span data-ttu-id="9ceff-103">MED-V ログの表示と構成</span><span class="sxs-lookup"><span data-stu-id="9ceff-103">Viewing and Configuring MED-V Logs</span></span>


<span data-ttu-id="9ceff-104">MED-V の問題と問題のトラブルシューティングを行うときに、MED-V イベントログにアクセスすることが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="9ceff-104">When you are troubleshooting MED-V issues and problems, you may find it helpful or necessary to access the MED-V event logs.</span></span> <span data-ttu-id="9ceff-105">ホストコンピューターとゲスト仮想マシンのイベントビューアーは、MED-V 管理ツールキットを使って開くことができます。</span><span class="sxs-lookup"><span data-stu-id="9ceff-105">You can open Event Viewer for the host computer and the guest virtual machine by using the MED-V Administration Toolkit.</span></span> <span data-ttu-id="9ceff-106">Med-v 管理ツールキットを使用して、MED-V イベントログで MED-V イベントを報告するログレベルを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="9ceff-106">You can also use the MED-V Administration Toolkit to set the logging level at which the MED-V event logs report MED-V events.</span></span>

<span data-ttu-id="9ceff-107">MED-V 管理ツールキットを開く方法の詳細については、「[管理ツールキットを使用した med-v のトラブルシューティング](troubleshooting-med-v-by-using-the-administration-toolkit.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ceff-107">For information about how to open the MED-V Administration Toolkit, see [Troubleshooting MED-V by Using the Administration Toolkit](troubleshooting-med-v-by-using-the-administration-toolkit.md).</span></span>

## <span data-ttu-id="9ceff-108">MED-V イベントログの表示</span><span class="sxs-lookup"><span data-stu-id="9ceff-108">Viewing MED-V Event Logs</span></span>


<span data-ttu-id="9ceff-109">[ **Med-v 管理ツールキット**] ウィンドウで、[ **host Events** ] をクリックして、ホストコンピューターのイベントビューアーを開きます。</span><span class="sxs-lookup"><span data-stu-id="9ceff-109">On the **MED-V Administration Toolkit** window, click **Host Events** to open the event viewer for the host computer.</span></span> <span data-ttu-id="9ceff-110">または、[**ゲストイベント**] をクリックして、ゲスト仮想マシンのイベントビューアーを開きます。</span><span class="sxs-lookup"><span data-stu-id="9ceff-110">Or, click **Guest Events** to open Event Viewer for the guest virtual machine.</span></span>

<span data-ttu-id="9ceff-111">イベントビューアーには、MED-V を展開または管理するときに発生する可能性がある問題のトラブルシューティングに使用できる、対応するイベントログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9ceff-111">Event Viewer opens and displays the corresponding event logs that you can use to troubleshoot the issues that you might encounter when you deploy or manage MED-V.</span></span> <span data-ttu-id="9ceff-112">既定では、エラーと警告のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9ceff-112">By default, only errors and warnings are displayed.</span></span> <span data-ttu-id="9ceff-113">特定のイベント Id とメッセージの詳細については、「 [Med-v イベントログのメッセージ](med-v-event-log-messages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ceff-113">For more information about specific event IDs and messages, see [MED-V Event Log Messages](med-v-event-log-messages.md).</span></span>

<span data-ttu-id="9ceff-114">**注** エンドユーザーが管理者権限を持っている場合にのみ、イベントログファイルをゲストに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="9ceff-114">**Note** End users can only save event log files in the guest if they have administrative permissions.</span></span>

 

### <span data-ttu-id="9ceff-115">ホストコンピューターでイベントビューアーを手動で開くには</span><span class="sxs-lookup"><span data-stu-id="9ceff-115">To manually open the Event Viewer in the host computer</span></span>

1.  <span data-ttu-id="9ceff-116">[**スタート**] をクリックし、[**コントロールパネル**] をクリックして、[**管理ツール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ceff-116">Click **Start**, click **Control Panel**, and then click **Administrative Tools**.</span></span>

2.  <span data-ttu-id="9ceff-117">[**イベントビューアー**] をダブルクリックし、[**アプリケーションとサービスログ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ceff-117">Double-click **Event Viewer**, and then click **Applications and Services Logs**.</span></span>

3.  <span data-ttu-id="9ceff-118">[ **MEDV**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ceff-118">Double-click **MEDV**.</span></span>

## <span data-ttu-id="9ceff-119">MED-V イベントログの構成</span><span class="sxs-lookup"><span data-stu-id="9ceff-119">Configuring MED-V Event Logs</span></span>


<span data-ttu-id="9ceff-120">Med-v のイベントログレベルを指定するには、MED-V 管理ツールキットの対応するオプションボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="9ceff-120">You can specify the MED-V event logging level by selecting the corresponding option button on the MED-V Administration Toolkit.</span></span> <span data-ttu-id="9ceff-121">イベントログには、エラーのみ、エラーと警告、エラー、警告、情報メッセージを含めるかどうかを決めることができます。</span><span class="sxs-lookup"><span data-stu-id="9ceff-121">You can decide whether event logging includes errors only, errors and warnings, or errors, warnings and informational messages.</span></span> <span data-ttu-id="9ceff-122">指定されたイベントログレベルは、ホストコンピューターとゲスト仮想マシンの両方に対して設定されます。</span><span class="sxs-lookup"><span data-stu-id="9ceff-122">The event logging level specified is set for both the host computer and the guest virtual machine.</span></span>

<span data-ttu-id="9ceff-123">また、EventLogLevel registry 値を編集して、イベントログレベルを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="9ceff-123">You can also specify the event logging level by editing the EventLogLevel registry value.</span></span> <span data-ttu-id="9ceff-124">詳細については、「 [Med-v ワークスペース構成の設定を管理する](managing-med-v-workspace-configuration-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ceff-124">For more information, see [Managing MED-V Workspace Configuration Settings](managing-med-v-workspace-configuration-settings.md).</span></span>

<span data-ttu-id="9ceff-125">**注** **Med-v 管理ツールキット**ウィンドウで指定したレベルは、将来の med-v イベントログに適用されます。</span><span class="sxs-lookup"><span data-stu-id="9ceff-125">**Note** The level you specify on the **MED-V Administration Toolkit** window applies to future MED-V event logging.</span></span> <span data-ttu-id="9ceff-126">すべてのエラー、警告、情報メッセージを取得するようにレベルを設定した場合、イベントログの入力が速くなり、古いイベントが削除されます。</span><span class="sxs-lookup"><span data-stu-id="9ceff-126">If you set the level to capture all errors, warnings, and informational messages, then the event logs fill more quickly and older events are removed.</span></span>

 

## <span data-ttu-id="9ceff-127">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9ceff-127">Related topics</span></span>


[<span data-ttu-id="9ceff-128">MED-V ワークスペースの再開とリセット</span><span class="sxs-lookup"><span data-stu-id="9ceff-128">Restarting and Resetting a MED-V Workspace</span></span>](restarting-and-resetting-a-med-v-workspace.md)

[<span data-ttu-id="9ceff-129">MED-V ワークスペースの構成の表示</span><span class="sxs-lookup"><span data-stu-id="9ceff-129">Viewing MED-V Workspace Configurations</span></span>](viewing-med-v-workspace-configurations.md)

 

 





