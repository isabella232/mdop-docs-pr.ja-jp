---
title: Client Management Console でアプリケーションを管理する方法
description: Client Management Console でアプリケーションを管理する方法
author: dansimp
ms.assetid: 15cb5133-539b-499d-adca-ed02da20194a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f29c26c972017eb9ba0dfd2d934c4fd07f2fae29
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817184"
---
# <span data-ttu-id="3642c-103">Client Management Console でアプリケーションを管理する方法</span><span class="sxs-lookup"><span data-stu-id="3642c-103">How to Manage Applications in the Client Management Console</span></span>


<span data-ttu-id="3642c-104">Application Virtualization クライアント管理コンソールを使用して、リモートデスクトップサービス (以前のターミナルサービス) キャッシュ向けの Application Virtualization デスクトップクライアントまたはクライアントで仮想アプリケーションを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="3642c-104">You can use the Application Virtualization Client Management Console to manage virtual applications in the Application Virtualization Desktop Client or Client for Remote Desktop Services (formerly Terminal Services) cache.</span></span> <span data-ttu-id="3642c-105">アプリケーションの仮想化のコンテキストでは、キャッシュは、仮想アプリケーションを保存するために予約されているクライアントコンピューター上の領域です。</span><span class="sxs-lookup"><span data-stu-id="3642c-105">In the context of application virtualization, the cache is the area on the client computer reserved to store virtual applications.</span></span>

## <span data-ttu-id="3642c-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3642c-106">In This Section</span></span>


<a href="" id="how-to-load-or-unload-an-application"></a>[<span data-ttu-id="3642c-107">アプリケーションの読み込みまたはアンロードを行う方法</span><span class="sxs-lookup"><span data-stu-id="3642c-107">How to Load or Unload an Application</span></span>](how-to-load-or-unload-an-application.md)  
<span data-ttu-id="3642c-108">クライアントキャッシュとの間でのアプリケーションの読み込みまたはアンロードの手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="3642c-108">Provides procedures for loading or unloading an application into or from the client cache.</span></span>

<a href="" id="how-to-clear-an-application"></a>[<span data-ttu-id="3642c-109">アプリケーションをクリアする方法</span><span class="sxs-lookup"><span data-stu-id="3642c-109">How to Clear an Application</span></span>](how-to-clear-an-application.md)  
<span data-ttu-id="3642c-110">リモートデスクトップサービスのアプリケーションの仮想化デスクトップクライアントまたはクライアントから、設定、ファイルの種類の関連付け、ショートカットをクリアするために使用できる手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="3642c-110">Provides a procedure you can use to clear the settings, file type associations, and shortcuts from the Application Virtualization Desktop Client or Client for Remote Desktop Services.</span></span>

<a href="" id="how-to-repair-an-application"></a>[<span data-ttu-id="3642c-111">アプリケーションを修復する方法</span><span class="sxs-lookup"><span data-stu-id="3642c-111">How to Repair an Application</span></span>](how-to-repair-an-application.md)  
<span data-ttu-id="3642c-112">アプリケーションの仮想化デスクトップクライアントまたはリモートデスクトップサービスのクライアントからアプリケーションを修復するための手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="3642c-112">Provides a procedure for repairing an application from the Application Virtualization Desktop Client or Client for Remote Desktop Services.</span></span>

<a href="" id="how-to-import-an-application"></a>[<span data-ttu-id="3642c-113">アプリケーションをインポートする方法</span><span class="sxs-lookup"><span data-stu-id="3642c-113">How to Import an Application</span></span>](how-to-import-an-application.md)  
<span data-ttu-id="3642c-114">新しいアプリケーションを、リモートデスクトップサービス用の Application Virtualization デスクトップクライアントまたはクライアントに追加するために使用できる手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="3642c-114">Provides a procedure you can use to add a new application to the Application Virtualization Desktop Client or Client for Remote Desktop Services.</span></span>

<a href="" id="how-to-lock-or-unlock-an-application"></a>[<span data-ttu-id="3642c-115">アプリケーションをロックまたはロック解除する方法</span><span class="sxs-lookup"><span data-stu-id="3642c-115">How to Lock or Unlock an Application</span></span>](how-to-lock-or-unlock-an-application.md)  
<span data-ttu-id="3642c-116">キャッシュ内のアプリケーションをロックまたはロック解除する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="3642c-116">Provides procedures for locking or unlocking an application in the cache.</span></span>

<a href="" id="how-to-delete-an-application"></a>[<span data-ttu-id="3642c-117">アプリケーションを削除する方法</span><span class="sxs-lookup"><span data-stu-id="3642c-117">How to Delete an Application</span></span>](how-to-delete-an-application.md)  
<span data-ttu-id="3642c-118">ファイルシステムキャッシュからアプリケーションを削除するために使用できる手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="3642c-118">Provides a procedure you can use to remove an application from the file system cache.</span></span>

<a href="" id="how-to-change-an-application-icon"></a>[<span data-ttu-id="3642c-119">アプリケーション アイコンを変更する方法</span><span class="sxs-lookup"><span data-stu-id="3642c-119">How to Change an Application Icon</span></span>](how-to-change-an-application-icon.md)  
<span data-ttu-id="3642c-120">選択したアプリケーションに関連付けられているアイコンを変更するために使用できる手順を紹介します。</span><span class="sxs-lookup"><span data-stu-id="3642c-120">Provides a procedure you can use to change the icon associated with the selected application.</span></span>

## <span data-ttu-id="3642c-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3642c-121">Related topics</span></span>


[<span data-ttu-id="3642c-122">Application Virtualization Client Management Console</span><span class="sxs-lookup"><span data-stu-id="3642c-122">Application Virtualization Client Management Console</span></span>](application-virtualization-client-management-console.md)

 

 





