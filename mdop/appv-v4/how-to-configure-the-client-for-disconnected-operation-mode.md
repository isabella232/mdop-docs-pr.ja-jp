---
title: 非接続操作モードのクライアントを構成する方法
description: 非接続操作モードのクライアントを構成する方法
author: dansimp
ms.assetid: 3b48464a-b8b4-494b-93e3-9a6d9bd74652
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1c917d87996a26b330551deb04b1828c31fd3c73
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817817"
---
# <span data-ttu-id="018ef-103">非接続操作モードのクライアントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="018ef-103">How to Configure the Client for Disconnected Operation Mode</span></span>


<span data-ttu-id="018ef-104">切断された操作モードでは、Application Virtualization (App-v) Desktop クライアントまたはリモートデスクトップサービス (以前のターミナルサービス) の Application Virtualization (App-v) クライアントを使用して、クライアントが App-v Management Server に接続できない場合に、クライアントのファイルシステムキャッシュに保存されているアプリケーションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="018ef-104">The disconnected operation mode enables the Application Virtualization (App-V) Desktop Client or the Application Virtualization (App-V) Client for Remote Desktop Services (formerly Terminal Services) to run applications that are stored in the file system cache of the client when the client cannot connect to the App-V Management Server.</span></span>

<span data-ttu-id="018ef-105">**重要** 多数のユーザーをサポートするために複数のリモートデスクトップセッションホスト (RD 度セッションホスト) サーバー (旧ターミナルサーバー) がファーム内にリンクされている大規模な組織では、1つのアプリをサポートするために単一のアプリを使用することで、1つの障害点が示されます。</span><span class="sxs-lookup"><span data-stu-id="018ef-105">**Important** In a large organization where multiple Remote Desktop Session Host (RD°Session Host) servers (formerly Terminal Servers) are linked in a farm to support many users, using a single App-V Management Server to support the farm represents a single point of failure.</span></span> <span data-ttu-id="018ef-106">RDSession ホストファームをサポートするために高可用性を実現するには、2つ以上の App-v 管理サーバーをリンクして、同じデータベースを使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="018ef-106">To provide high availability to support the RDSession Host farm, consider linking two or more App-V Management Servers to use the same database.</span></span>

 

**<span data-ttu-id="018ef-107">切断された操作モードを有効にするには</span><span class="sxs-lookup"><span data-stu-id="018ef-107">To enable disconnected operation mode</span></span>**

-   <span data-ttu-id="018ef-108">切断された操作モードを有効にするには、次のレジストリキーの値を1に設定します。</span><span class="sxs-lookup"><span data-stu-id="018ef-108">Set the following registry key value equal to 1 to enable disconnected operation mode:</span></span>

    <span data-ttu-id="018ef-109">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\AllowDisconnectedOperation</span><span class="sxs-lookup"><span data-stu-id="018ef-109">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\AllowDisconnectedOperation</span></span>

**<span data-ttu-id="018ef-110">切断された操作モードの使用制限時間を設定するには</span><span class="sxs-lookup"><span data-stu-id="018ef-110">To set a time limit on disconnected operation mode use</span></span>**

1.  <span data-ttu-id="018ef-111">次のレジストリキー値を1に設定します。</span><span class="sxs-lookup"><span data-stu-id="018ef-111">Set the following registry key value to 1:</span></span>

    <span data-ttu-id="018ef-112">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\LimitDisconnectedOperation</span><span class="sxs-lookup"><span data-stu-id="018ef-112">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\LimitDisconnectedOperation</span></span>

2.  <span data-ttu-id="018ef-113">次のレジストリキー値を、切断操作モードを制限する分単位の時間に設定します。</span><span class="sxs-lookup"><span data-stu-id="018ef-113">Set the following registry key value to the number of minutes you want to limit disconnected operation mode.</span></span> <span data-ttu-id="018ef-114">値の有効な範囲は 1 ~ 999999 です。</span><span class="sxs-lookup"><span data-stu-id="018ef-114">The valid range of values is 1–999999.</span></span> <span data-ttu-id="018ef-115">既定値は、90日または129600分です。</span><span class="sxs-lookup"><span data-stu-id="018ef-115">The default value is 90 days or 129,600 minutes.</span></span>

    <span data-ttu-id="018ef-116">HKEY \ _LOCAL \ _MACHINE ¥ $ ¥ (英語) \ すべてのソフトウェア \ ネットワーク \\ dotimeoutminutes</span><span class="sxs-lookup"><span data-stu-id="018ef-116">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\DOTimeoutMinutes</span></span>

**<span data-ttu-id="018ef-117">接続されていない操作モード用にリモートデスクトップサービスのクライアントを構成するには</span><span class="sxs-lookup"><span data-stu-id="018ef-117">To configure the Client for Remote Desktop Services for disconnected operation mode</span></span>**

1.  <span data-ttu-id="018ef-118">切断された操作モードを有効にするには、次のレジストリキー値を1に設定します。</span><span class="sxs-lookup"><span data-stu-id="018ef-118">Set the following registry key value to 1 to enable disconnected operation mode:</span></span>

    <span data-ttu-id="018ef-119">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\AllowDisconnectedOperation</span><span class="sxs-lookup"><span data-stu-id="018ef-119">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\AllowDisconnectedOperation</span></span>

2.  <span data-ttu-id="018ef-120">切断された操作モードの無制限の使用を許可するには、次のレジストリキー値を 0 (ゼロ) に設定します。</span><span class="sxs-lookup"><span data-stu-id="018ef-120">Set the following registry key value to 0 (zero) to allow unlimited use of disconnected operation mode:</span></span>

    <span data-ttu-id="018ef-121">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\LimitDisconnectedOperation</span><span class="sxs-lookup"><span data-stu-id="018ef-121">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\LimitDisconnectedOperation</span></span>

3.  <span data-ttu-id="018ef-122">パフォーマンスを向上させるために、すべてのパッケージがキャッシュに事前に読み込まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="018ef-122">Ensure that all packages are preloaded into the cache to improve performance.</span></span>

## <span data-ttu-id="018ef-123">関連トピック</span><span class="sxs-lookup"><span data-stu-id="018ef-123">Related topics</span></span>


[<span data-ttu-id="018ef-124">非接続操作モード</span><span class="sxs-lookup"><span data-stu-id="018ef-124">Disconnected Operation Mode</span></span>](disconnected-operation-mode.md)

[<span data-ttu-id="018ef-125">コマンド ラインを使用して App-V Client レジストリ設定を構成する方法</span><span class="sxs-lookup"><span data-stu-id="018ef-125">How to Configure the App-V Client Registry Settings by Using the Command Line</span></span>](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

 

 





