---
title: サーバー管理コンソールでアプリケーション ライセンスを管理する方法
description: サーバー管理コンソールでアプリケーション ライセンスを管理する方法
author: dansimp
ms.assetid: 48503b04-0de7-48de-98ee-4623a712a341
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ca9ab54c8b4cee06e0b17d8b5dee3d3ca7ce69c5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817224"
---
# <span data-ttu-id="b9fb3-103">サーバー管理コンソールでアプリケーション ライセンスを管理する方法</span><span class="sxs-lookup"><span data-stu-id="b9fb3-103">How to Manage Application Licenses in the Server Management Console</span></span>


<span data-ttu-id="b9fb3-104">Application Virtualization Server 管理コンソールは、Application Virtualization プラットフォームを管理するために使用するインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="b9fb3-104">The Application Virtualization Server Management Console is the interface you use to manage the Application Virtualization platform.</span></span> <span data-ttu-id="b9fb3-105">この場合、アプリケーションライセンスグループの追加、削除、構成、および制御を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b9fb3-105">From it, you can add, remove, configure, and control application license groups.</span></span>

<span data-ttu-id="b9fb3-106">**重要** App-v クライアントアプリケーションのソースルート (ASR) 設定が、管理サーバー以外の任意の種類のストリーミングソース (ストリーミングサーバー、IIS サーバー、ファイルサーバーなど) を使用するように構成されている場合、管理サーバーはライセンスポリシーを適用できません。</span><span class="sxs-lookup"><span data-stu-id="b9fb3-106">**Important** If the App-V client Application Source Root (ASR) setting is configured to use any type of streaming source other than the Management Server, for example a Streaming Server, an IIS server, or a File server, then the Management Server is unable to enforce its licensing policy.</span></span>

 

## <span data-ttu-id="b9fb3-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b9fb3-107">In This Section</span></span>


<a href="" id="how-to-create-an-application-license-group"></a>[<span data-ttu-id="b9fb3-108">アプリケーション ライセンス グループを作成する方法</span><span class="sxs-lookup"><span data-stu-id="b9fb3-108">How to Create an Application License Group</span></span>](how-to-create-an-application-license-group.md)  
<span data-ttu-id="b9fb3-109">ライセンスグループで新しいアプリケーションを作成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="b9fb3-109">Provides a procedure for creating a new application in a license group.</span></span>

<a href="" id="how-to-associate-an-application-with-a-license-group"></a>[<span data-ttu-id="b9fb3-110">アプリケーションをライセンス グループに関連付ける方法</span><span class="sxs-lookup"><span data-stu-id="b9fb3-110">How to Associate an Application with a License Group</span></span>](how-to-associate-an-application-with-a-license-group.md)  
<span data-ttu-id="b9fb3-111">ライセンスグループにアプリケーションを追加するための手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="b9fb3-111">Provides a procedure for adding an application to a license group.</span></span>

<a href="" id="how-to-remove-an-application-from-a-license-group"></a>[<span data-ttu-id="b9fb3-112">ライセンス グループからアプリケーションを削除する方法</span><span class="sxs-lookup"><span data-stu-id="b9fb3-112">How to Remove an Application from a License Group</span></span>](how-to-remove-an-application-from-a-license-group.md)  
<span data-ttu-id="b9fb3-113">ライセンスグループからアプリケーションを削除する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="b9fb3-113">Provides a procedure for removing an application from a license group.</span></span>

<a href="" id="how-to-remove-an-application-license-group"></a>[<span data-ttu-id="b9fb3-114">アプリケーション ライセンス グループを削除する方法</span><span class="sxs-lookup"><span data-stu-id="b9fb3-114">How to Remove an Application License Group</span></span>](how-to-remove-an-application-license-group.md)  
<span data-ttu-id="b9fb3-115">このセクションでは、アプリケーションライセンスグループを削除するために必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="b9fb3-115">This section includes the steps necessary to delete an application license group.</span></span>

<a href="" id="how-to-set-up-an-unlimited-license-group"></a>[<span data-ttu-id="b9fb3-116">無制限ライセンス グループをセットアップする方法</span><span class="sxs-lookup"><span data-stu-id="b9fb3-116">How to Set Up an Unlimited License Group</span></span>](how-to-set-up-an-unlimited-license-group.md)  
<span data-ttu-id="b9fb3-117">実質無制限のライセンスグループを作成して、グループ内のアプリケーションに無制限のユーザーがアクセスできるようにする手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="b9fb3-117">Provides a procedure for creating a new unlimited license group, allowing an unlimited number of users to access the applications in the group.</span></span>

<a href="" id="how-to-set-up-a-concurrent-license-group"></a>[<span data-ttu-id="b9fb3-118">同時使用ライセンス グループをセットアップする方法</span><span class="sxs-lookup"><span data-stu-id="b9fb3-118">How to Set Up a Concurrent License Group</span></span>](how-to-set-up-a-concurrent-license-group.md)  
<span data-ttu-id="b9fb3-119">新しい同時ライセンスグループを作成するための手順について説明します。これにより、特定の数の同時ユーザーがグループ内のアプリケーションにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="b9fb3-119">Provides a procedure for creating a new concurrent license group, allowing a specific number of concurrent users to access the applications in the group.</span></span>

<a href="" id="how-to-set-up-a-named-license-group"></a>[<span data-ttu-id="b9fb3-120">名前付きライセンス グループをセットアップする方法</span><span class="sxs-lookup"><span data-stu-id="b9fb3-120">How to Set Up a Named License Group</span></span>](how-to-set-up-a-named-license-group.md)  
<span data-ttu-id="b9fb3-121">ライセンスグループを新規作成して、特定のユーザーがグループ内のアプリケーションにアクセスできるようにする手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="b9fb3-121">Provides a procedure for creating a new unlimited license group, allowing specific users to access the applications in the group.</span></span>

## <span data-ttu-id="b9fb3-122">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b9fb3-122">Related topics</span></span>


[<span data-ttu-id="b9fb3-123">Application Virtualization サーバー管理コンソールで管理タスクを実行する方法</span><span class="sxs-lookup"><span data-stu-id="b9fb3-123">How to Perform Administrative Tasks in the Application Virtualization Server Management Console</span></span>](how-to-perform-administrative-tasks-in-the-application-virtualization-server-management-console.md)

 

 





