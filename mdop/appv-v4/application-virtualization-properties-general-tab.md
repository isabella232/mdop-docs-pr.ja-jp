---
title: Application Virtualization プロパティの [全般] タブ
description: Application Virtualization プロパティの [全般] タブ
author: dansimp
ms.assetid: be7449d9-171a-4a11-9382-83b7008ccbdd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6ee00bfc7f70ee7b17da42aad61356540a7a0be0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819687"
---
# <span data-ttu-id="1e911-103">Application Virtualization プロパティ: [全般] タブ</span><span class="sxs-lookup"><span data-stu-id="1e911-103">Application Virtualization Properties: General Tab</span></span>


<span data-ttu-id="1e911-104">[ **Application Virtualization Properties** ] ダイアログボックスの **[全般**] タブを使用して、ログの設定とデータの場所を変更します。</span><span class="sxs-lookup"><span data-stu-id="1e911-104">Use the **General** tab of the **Application Virtualization Properties** dialog box to modify log settings and data locations.</span></span>

<span data-ttu-id="1e911-105">このタブには、次の要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1e911-105">This tab contains the following elements.</span></span>

<a href="" id="log-level"></a>**<span data-ttu-id="1e911-106">ログレベル</span><span class="sxs-lookup"><span data-stu-id="1e911-106">Log Level</span></span>**  
<span data-ttu-id="1e911-107">ドロップダウンリストからレベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="1e911-107">Select the level from the drop-down list.</span></span> <span data-ttu-id="1e911-108">既定のレベルは**情報**です。</span><span class="sxs-lookup"><span data-stu-id="1e911-108">The default level is **Information**.</span></span>

<a href="" id="reset-log"></a>**<span data-ttu-id="1e911-109">ログのリセット</span><span class="sxs-lookup"><span data-stu-id="1e911-109">Reset Log</span></span>**  
<span data-ttu-id="1e911-110">現在のログファイルをバックアップして、すぐに新しいログファイルを開始するには、このボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1e911-110">Click this button to back up the current log file and immediately start a new log file.</span></span>

<a href="" id="location"></a>**<span data-ttu-id="1e911-111">位置情報</span><span class="sxs-lookup"><span data-stu-id="1e911-111">Location</span></span>**  
<span data-ttu-id="1e911-112">sftlog.txt ログファイルを保存する場所を入力するか参照します。</span><span class="sxs-lookup"><span data-stu-id="1e911-112">Enter or browse to the location where you want to save the log file sftlog.txt.</span></span> <span data-ttu-id="1e911-113">既定の場所は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1e911-113">The default locations are as follows:</span></span>

-   <span data-ttu-id="1e911-114">WindowsXP の場合は、Windows Server2003:*C:\\Documents および Settings\\All Users\\Application data¥ microsoft Application Virtualization Client*</span><span class="sxs-lookup"><span data-stu-id="1e911-114">For WindowsXP, Windows Server2003—*C:\\Documents and Settings\\All Users\\Application Data\\Microsoft\\Application Virtualization Client*</span></span>

-   <span data-ttu-id="1e911-115">Windows Vista、Windows 7、Windows Server2008、*C:\\ProgramData\\Microsoft\\Application Virtualization クライアント*の場合</span><span class="sxs-lookup"><span data-stu-id="1e911-115">For Windows Vista, Windows 7, Windows Server2008—*C:\\ProgramData\\Microsoft\\Application Virtualization Client*</span></span>

<a href="" id="system-log-level"></a>**<span data-ttu-id="1e911-116">システムログレベル</span><span class="sxs-lookup"><span data-stu-id="1e911-116">System Log Level</span></span>**  
<span data-ttu-id="1e911-117">ドロップダウンリストからレベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="1e911-117">Select the level from the drop-down list.</span></span> <span data-ttu-id="1e911-118">既定のレベルは**警告**です。</span><span class="sxs-lookup"><span data-stu-id="1e911-118">The default level is **Warning**.</span></span>

<span data-ttu-id="1e911-119">**注** システム**ログレベル**設定は、システムイベントログに送信されるメッセージのレベルを制御します。</span><span class="sxs-lookup"><span data-stu-id="1e911-119">**Note** The **System Log Level** setting controls the level of messages sent to the system event log.</span></span> <span data-ttu-id="1e911-120">ログに記録されたメッセージは、クライアントイベントログに記録されるメッセージと同じですが、クライアントイベントログの領域制限を持たない別の場所に格納されています。</span><span class="sxs-lookup"><span data-stu-id="1e911-120">The logged messages are identical to the messages that get logged to the client event log, but they are stored in a different location that does not have the space limitations of the client event log.</span></span> <span data-ttu-id="1e911-121">システムイベントログにはスペースの制限がないため、詳細なログが必要な場合に最適です。</span><span class="sxs-lookup"><span data-stu-id="1e911-121">Because the system event log does not have space limitations, it is ideally suited for situations where verbose logging is necessary.</span></span>

 

<a href="" id="global-data-directory"></a>**<span data-ttu-id="1e911-122">グローバルデータディレクトリ</span><span class="sxs-lookup"><span data-stu-id="1e911-122">Global Data Directory</span></span>**  
<span data-ttu-id="1e911-123">ログファイルのディレクトリの場所を入力または参照します。</span><span class="sxs-lookup"><span data-stu-id="1e911-123">Enter or browse to the location of the directory of the log file.</span></span> <span data-ttu-id="1e911-124">既定の場所は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1e911-124">The default locations are as follows:</span></span>

-   <span data-ttu-id="1e911-125">WindowsXP の場合は、Windows Server2003:*C:\\Documents および Settings\\All Users\\Application data¥ microsoft Application Virtualization Client*</span><span class="sxs-lookup"><span data-stu-id="1e911-125">For WindowsXP, Windows Server2003—*C:\\Documents and Settings\\All Users\\Application Data\\Microsoft\\Application Virtualization Client*</span></span>

-   <span data-ttu-id="1e911-126">Windows Vista、Windows 7、Windows Server2008、*C:\\ProgramData\\Microsoft\\Application Virtualization クライアント*の場合</span><span class="sxs-lookup"><span data-stu-id="1e911-126">For Windows Vista, Windows 7, Windows Server2008—*C:\\ProgramData\\Microsoft\\Application Virtualization Client*</span></span>

<a href="" id="user-data-directory"></a>**<span data-ttu-id="1e911-127">ユーザーデータディレクトリ</span><span class="sxs-lookup"><span data-stu-id="1e911-127">User Data Directory</span></span>**  
<span data-ttu-id="1e911-128">ユーザー固有のデータが保存されているディレクトリの場所を入力または参照します。</span><span class="sxs-lookup"><span data-stu-id="1e911-128">Enter or browse to the location of the directory where user-specific data is stored.</span></span> <span data-ttu-id="1e911-129">既定値は% APPDATA% です。</span><span class="sxs-lookup"><span data-stu-id="1e911-129">The default is %APPDATA%.</span></span> <span data-ttu-id="1e911-130">このパスは、クライアントコンピューター上の有効な環境変数である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e911-130">This path must be a valid environment variable on the client computer.</span></span>

## <span data-ttu-id="1e911-131">関連トピック</span><span class="sxs-lookup"><span data-stu-id="1e911-131">Related topics</span></span>


[<span data-ttu-id="1e911-132">Client Management Console: Application Virtualization プロパティ</span><span class="sxs-lookup"><span data-stu-id="1e911-132">Client Management Console: Application Virtualization Properties</span></span>](client-management-console-application-virtualization-properties.md)

 

 





