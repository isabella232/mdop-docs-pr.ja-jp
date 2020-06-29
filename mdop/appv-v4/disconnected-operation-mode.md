---
title: 非接続操作モード
description: 非接続操作モード
author: dansimp
ms.assetid: 3f9849ea-ba53-4c68-85d3-87a4218f59c6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6e9534b93f23b17e5258ef5e2d548eb93213f2f8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821624"
---
# <span data-ttu-id="26871-103">非接続操作モード</span><span class="sxs-lookup"><span data-stu-id="26871-103">Disconnected Operation Mode</span></span>


<span data-ttu-id="26871-104">切断された操作モードの設定:**アプリケーション仮想化**ノードを右クリックし、[**プロパティ**] を選び、[**接続**] タブをクリックすると、クライアントが application virtualization Management Server に接続できないときに、クライアントのファイルシステムキャッシュに保存されているアプリケーションを実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="26871-104">The disconnected operation mode settings—accessible by right-clicking the **Application Virtualization** node, selecting **Properties**, and clicking the **Connectivity** tab—enables the Application Virtualization Desktop Client or Client for Remote Desktop Services (formerly Terminal Services) to run applications that are stored in the file system cache of the client when the client is unable to connect to the Application Virtualization Management Server.</span></span>

<span data-ttu-id="26871-105">サーバーへの接続に失敗した理由として、サーバーの失敗、ネットワークの停止、ネットワークからの切断などがあります。</span><span class="sxs-lookup"><span data-stu-id="26871-105">Reasons for failure to connect to the server include server failure, network outage, or disconnection from the network.</span></span> <span data-ttu-id="26871-106">障害が発生した場合、クライアントは自動的に切断された操作に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="26871-106">If any failure occurs, the client will automatically switch to disconnected operation.</span></span> <span data-ttu-id="26871-107">接続が切断された後、クライアントでサーバーから追加のデータが要求され、アプリケーションの実行が続行される場合、または切断された操作のタイムアウトが経過した場合、クライアントはサーバーに再接続しようとします。</span><span class="sxs-lookup"><span data-stu-id="26871-107">After it is disconnected, if the client needs additional data from the server to continue to run an application or if the disconnected operation time-out expires, the client will attempt to reconnect to the server.</span></span> <span data-ttu-id="26871-108">この接続が失敗すると、アプリケーションはシャットダウンされます。</span><span class="sxs-lookup"><span data-stu-id="26871-108">If this connection attempt fails, the application will be shut down.</span></span>

<span data-ttu-id="26871-109">既定では、切断された操作は有効になっていますが、タイムアウトは90日間に設定されています。</span><span class="sxs-lookup"><span data-stu-id="26871-109">By default, disconnected operation is enabled and the time-out is set to 90 days.</span></span> <span data-ttu-id="26871-110">タイムアウト値は、切断操作モードを制限する日数として指定され、1 ~ 999 の値を入力することができます。</span><span class="sxs-lookup"><span data-stu-id="26871-110">The time-out value is specified as the number of days you want to limit disconnected operation mode, and you can enter a value from 1–999.</span></span>

## <span data-ttu-id="26871-111">関連トピック</span><span class="sxs-lookup"><span data-stu-id="26871-111">Related topics</span></span>


[<span data-ttu-id="26871-112">非接続操作モード設定を無効化または変更する方法</span><span class="sxs-lookup"><span data-stu-id="26871-112">How to Disable or Modify Disconnected Operation Mode Settings</span></span>](how-to-disable-or-modify-disconnected-operation-mode-settings.md)

 

 





