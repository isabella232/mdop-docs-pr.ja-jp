---
title: MED-V ワークスペースの展開の監視
description: MED-V ワークスペースの展開の監視
author: dansimp
ms.assetid: 5de0cb06-b8a9-48a5-b8b3-836954295765
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6ec4c7c85326e7945aa3d61b7f96872afe24fe37
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827214"
---
# <span data-ttu-id="86059-103">MED-V ワークスペースの展開の監視</span><span class="sxs-lookup"><span data-stu-id="86059-103">Monitoring MED-V Workspace Deployments</span></span>


<span data-ttu-id="86059-104">Microsoft Enterprise デスクトップ仮想化 (MED-V) 2.0 の監視機能を使用すると、個々の MED-V ワークスペースに対してクエリを実行して、MED-V ワークスペースが展開された後で初めてエンタープライズ全体でセットアップが成功したかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="86059-104">The monitoring feature in Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 lets you run queries on individual MED-V workspaces to determine whether first time setup succeeded throughout your enterprise after the MED-V workspaces are deployed.</span></span> <span data-ttu-id="86059-105">初回のセットアップが正常に完了するまでは、MED-V が使用可能な状態になっていないため、初回のセットアップの成否を監視することが重要です。</span><span class="sxs-lookup"><span data-stu-id="86059-105">Monitoring the success of first time setup is important because MED-V is not in a usable state until first time setup has been completed successfully.</span></span>

<span data-ttu-id="86059-106">このセクションでは、初回セットアップ時の成功または失敗を監視するときに役立つ情報と指示について説明します。</span><span class="sxs-lookup"><span data-stu-id="86059-106">This section provides information and instruction to assist you in monitoring the success or failure of first time setup.</span></span>

## <span data-ttu-id="86059-107">MED-V ワークスペースの展開を監視するには</span><span class="sxs-lookup"><span data-stu-id="86059-107">To monitor MED-V workspace deployments</span></span>


<span data-ttu-id="86059-108">監視機能は、組み込みのインプロセス Windows Management Instrumentation (WMI) プロバイダーで構成されています。これは、WMI クエリ言語を使って照会し、MED-V ワークスペース上のすべてのエンドユーザーに対して初めてセットアップするときの状態を検出することができます。</span><span class="sxs-lookup"><span data-stu-id="86059-108">The monitoring feature consists of a coupled in-process Windows Management Instrumentation (WMI) provider that you can query using WMI Query Language to discover the status of first time setup for all end users on a MED-V workspace.</span></span>

<span data-ttu-id="86059-109">WMI プロバイダーは、Microsoft .Net Framework 3.5 から WMI プロバイダ拡張フレームワークを使って実装されています。</span><span class="sxs-lookup"><span data-stu-id="86059-109">The WMI provider is implemented by using the WMI Provider Extension framework from the Microsoft .Net Framework 3.5.</span></span> <span data-ttu-id="86059-110">WMI プロバイダーは LocalService のコンテキストで実行され、\\ProgramData. には、初めてのセットアップ状態が安全に保存されます。</span><span class="sxs-lookup"><span data-stu-id="86059-110">The WMI provider executes in the context of LocalService and stores the first time setup state securely under \\ProgramData.</span></span>

<span data-ttu-id="86059-111">WMI プロバイダーは、 **root\\microsoft\\medv**名前空間に実装され、class **FTS \ _Status**を実装します。これにより、メソッド**setftsstate**が公開されます。</span><span class="sxs-lookup"><span data-stu-id="86059-111">The WMI provider is implemented in the **root\\microsoft\\medv** namespace and implements the class **FTS\_Status**, which exposes the method **SetFtsState**.</span></span> <span data-ttu-id="86059-112">MED では、 **Setftsstate**を使って、初回のセットアップの状態を設定します。</span><span class="sxs-lookup"><span data-stu-id="86059-112">MED-V uses **SetFtsState** to set the first time setup state.</span></span>

<span data-ttu-id="86059-113">このクラスには、次のプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="86059-113">The class contains the following properties.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="86059-114">プロパティ</span><span class="sxs-lookup"><span data-stu-id="86059-114">Property</span></span></th>
<th align="left"><span data-ttu-id="86059-115">説明</span><span class="sxs-lookup"><span data-stu-id="86059-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="86059-116">コンピューター</span><span class="sxs-lookup"><span data-stu-id="86059-116">Machine</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="86059-117">読み取り専用 </strong> プロパティ。このプロパティには、初回セットアップでプロビジョニングされたゲスト仮想マシンの名前が含まれます。</span><span class="sxs-lookup"><span data-stu-id="86059-117">Read Only</strong> property that contains the name of the guest virtual machine provisioned by first time setup.</span></span> <span data-ttu-id="86059-118">このキーには、ゲストが初めてセットアップに失敗したときに使用した名前が含まれています。</span><span class="sxs-lookup"><span data-stu-id="86059-118">This key contains the name that the guest would have had on first time setup failure.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="86059-119">StatusCode</span><span class="sxs-lookup"><span data-stu-id="86059-119">StatusCode</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="86059-120"></strong>初めてセットアップに成功した場合は、0を含む読み取り専用プロパティ。</span><span class="sxs-lookup"><span data-stu-id="86059-120">Read Only</strong> property that contains zero if first time setup succeeded.</span></span> <span data-ttu-id="86059-121">返されるその他の値は、ログに記録されるエラーのイベント ID に相当します。</span><span class="sxs-lookup"><span data-stu-id="86059-121">Any other value returned equals the event ID for the error that is logged.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="86059-122">Time</span><span class="sxs-lookup"><span data-stu-id="86059-122">Time</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="86059-123">初めてセットアップが完了した UTC 時刻。</span><span class="sxs-lookup"><span data-stu-id="86059-123">The UTC time that first time setup completed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="86059-124">ユーザー</span><span class="sxs-lookup"><span data-stu-id="86059-124">User</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="86059-125">初めてのセットアップが実行されたユーザー。</span><span class="sxs-lookup"><span data-stu-id="86059-125">The user for which first time setup was run.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="86059-126">次のコードは、 **FTS \ _Status**クラスを定義するマネージオブジェクト形式 (MOF) ファイルを示しています。</span><span class="sxs-lookup"><span data-stu-id="86059-126">The following code shows the Managed Object Format (MOF) file that defines the **FTS\_Status** class.</span></span>

``` syntax
[dynamic: ToInstance, provider("MedvWmi, Version=2.0.258.0, Culture=neutral, PublicKeyToken=14986c3f172d1c2c")]
class FTS_Status
{
[read, key] string User;
[read] string Machine;
[read] sint32 StatusCode;
[read] datetime Time;
[static, implemented] void SetFtsState([in] sint32 statusCode, [in] string machine);
};
```

<span data-ttu-id="86059-127">最も重要なのは、初回のセットアップが正常に完了していない MED-V のワークスペースであると考えられるため、最初にセットアップに失敗したユーザーのみを返すようにクエリを作成できます。たとえば、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="86059-127">Because your main concern is most likely those MED-V workspaces for which first time setup was not completed successfully, you can write your query to only return those that failed first time setup, for example:</span></span>

``` syntax
Select * from FTS_Status where StatusCode != 0
```

<span data-ttu-id="86059-128">この場合、監視機能によって、最初のセットアップに失敗した MED-V ワークスペースのリストが返されます。これは、エラーを解決するために適切な操作を実行するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="86059-128">In this case, the monitoring feature returns a list of those MED-V workspaces that failed first time setup, which you can use to take the appropriate actions to resolve the failure.</span></span>

## <span data-ttu-id="86059-129">関連トピック</span><span class="sxs-lookup"><span data-stu-id="86059-129">Related topics</span></span>


[<span data-ttu-id="86059-130">MED-V ワークスペースを監視する</span><span class="sxs-lookup"><span data-stu-id="86059-130">Monitor MED-V Workspaces</span></span>](monitor-med-v-workspaces.md)

[<span data-ttu-id="86059-131">初回使用時のセットアップの設定を確認する方法</span><span class="sxs-lookup"><span data-stu-id="86059-131">How to Verify First Time Setup Settings</span></span>](how-to-verify-first-time-setup-settings.md)

 

 





