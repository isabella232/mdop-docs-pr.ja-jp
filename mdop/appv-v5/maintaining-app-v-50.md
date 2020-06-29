---
title: App-V 5.0 の保守
description: App-V 5.0 の保守
author: dansimp
ms.assetid: 66851ec3-c674-493b-ad6d-db8fcbf1956c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3445bfe00ba7703a66fa3da2f9d7089990dd3854
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813618"
---
# <span data-ttu-id="3484d-103">App-V 5.0 の保守</span><span class="sxs-lookup"><span data-stu-id="3484d-103">Maintaining App-V 5.0</span></span>


<span data-ttu-id="3484d-104">必要な計画をすべて完了した後、App-v 5.0 の展開を完了したら、次の情報を使用して、App-v 5.0 インフラストラクチャを維持することができます。</span><span class="sxs-lookup"><span data-stu-id="3484d-104">After you have completed all the necessary planning, and then deployment of App-V 5.0, you can use the following information to maintain the App-V 5.0 infrastructure.</span></span>

## <a href="" id="move-the-app-v-5-0-server-"></a><span data-ttu-id="3484d-105">App-v 5.0 サーバーを移動する</span><span class="sxs-lookup"><span data-stu-id="3484d-105">Move the App-V 5.0 Server</span></span>


<span data-ttu-id="3484d-106">App-v 5.0 サーバーは、app-v 5.0 データベースに接続します。</span><span class="sxs-lookup"><span data-stu-id="3484d-106">The App-V 5.0 server connects to the App-V 5.0 database.</span></span> <span data-ttu-id="3484d-107">そのため、ネットワーク上の任意のコンピューターに管理コンポーネントをインストールして、それを App-v 5.0 データベースに接続することができます。</span><span class="sxs-lookup"><span data-stu-id="3484d-107">Therefore you can install the management component to any computer on the network and then connect it to the App-V 5.0 database.</span></span>

[<span data-ttu-id="3484d-108">APP-V サーバーを別のコンピューターに移動する方法</span><span class="sxs-lookup"><span data-stu-id="3484d-108">How to Move the App-V Server to Another Computer</span></span>](how-to-move-the-app-v-server-to-another-computer.md)

## <a href="" id="determine-if-an-app-v-5-0-application-is-running-virtualized-"></a><span data-ttu-id="3484d-109">App-v 5.0 アプリケーションが仮想化されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="3484d-109">Determine if an App-V 5.0 Application is Running Virtualized</span></span>


<span data-ttu-id="3484d-110">アプリが、app-v 5.0 以降で実行されているかどうかを判断する独立系ソフトウェアベンダー (ISV) は、既定の名前\*\* &lt; &gt; 空間で AppVVirtual\*\*という名前のオブジェクトを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="3484d-110">Independent software vendors (ISV) who want to determine if an application is running virtualized with App-V 5.0 or above, should open a named object called **AppVVirtual-&lt;PID&gt;** in the default namespace.</span></span> <span data-ttu-id="3484d-111">たとえば、Windows API **Getcurrentprocessid ()** を使って、4052などの現在のプロセスの ID を取得できます。次に、 **4052 AppVVirtual**という名前のイベントオブジェクトを、読み取りアクセスの既定の名前空間で**openevent ()** を使って正常に開くことができます。その場合、アプリケーションは仮想です。</span><span class="sxs-lookup"><span data-stu-id="3484d-111">For example, Windows API **GetCurrentProcessId()** can be used to obtain the current process's ID, for example 4052, and then if a named Event object called **AppVVirtual-4052** can be successfully opened using **OpenEvent()** in the default namespace for read access, then the application is virtual.</span></span> <span data-ttu-id="3484d-112">**Openevent ()** 呼び出しに失敗した場合、アプリケーションは仮想ではありません。</span><span class="sxs-lookup"><span data-stu-id="3484d-112">If the **OpenEvent()** call fails, the application is not virtual.</span></span>

<span data-ttu-id="3484d-113">さらに、特定の API の呼び出しを明示的に仮想化したい場合や、特定の 5.0 API で呼び出さない場合は、AppEntSubsystems32.dll モジュールに実装されている**VirtualizeCurrentThread () 関数と Current** **adis**関数を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="3484d-113">Additionally, ISV’s who want to explicitly virtualize or not virtualize calls on specific API’s with App-V 5.0 and above, can use the **VirtualizeCurrentThread()** and **CurrentThreadIsVirtualized()** functions implemented in the AppEntSubsystems32.dll module.</span></span> <span data-ttu-id="3484d-114">これは、その呼び出しが仮想化されている必要があるかどうかを示す、下流のコンポーネントのヒントを提供します。</span><span class="sxs-lookup"><span data-stu-id="3484d-114">These provide a way of hinting at a downstream component that the call should or should not be virtualized.</span></span>






## <span data-ttu-id="3484d-115">App-v 5.0 を管理するためのその他のリソース</span><span class="sxs-lookup"><span data-stu-id="3484d-115">Other resources for maintaining App-V 5.0</span></span>


[<span data-ttu-id="3484d-116">APP-V 5.0 の操作</span><span class="sxs-lookup"><span data-stu-id="3484d-116">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





