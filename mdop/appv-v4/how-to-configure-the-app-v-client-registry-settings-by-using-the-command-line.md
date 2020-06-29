---
title: コマンド ラインを使用して App-V Client レジストリ設定を構成する方法
description: コマンド ラインを使用して App-V Client レジストリ設定を構成する方法
author: dansimp
ms.assetid: 3e3d873f-13d2-402f-97b4-f62d0c399171
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c424f39c8209ca641f6073838ebcb8726acc9e25
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817897"
---
# <span data-ttu-id="e99cc-103">コマンド ラインを使用して App-V Client レジストリ設定を構成する方法</span><span class="sxs-lookup"><span data-stu-id="e99cc-103">How to Configure the App-V Client Registry Settings by Using the Command Line</span></span>


<span data-ttu-id="e99cc-104">コマンドラインを使用してインストール中に Application Virtualization (App-v) クライアントを展開して構成した後、1つ以上のクライアント構成の設定を変更する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="e99cc-104">After the Application Virtualization (App-V) Client has been deployed and configured during the installation by using the command line, it might be necessary to change one or more client configuration settings.</span></span> <span data-ttu-id="e99cc-105">これは、次のいずれかの方法を使用して、適切なレジストリキーを編集することで実現されます。</span><span class="sxs-lookup"><span data-stu-id="e99cc-105">This is accomplished by editing the appropriate registry keys, using one of the following methods:</span></span>

-   <span data-ttu-id="e99cc-106">レジストリエディターを直接使用する</span><span class="sxs-lookup"><span data-stu-id="e99cc-106">Using the Registry Editor directly</span></span>

-   <span data-ttu-id="e99cc-107">.Reg ファイルを使用する</span><span class="sxs-lookup"><span data-stu-id="e99cc-107">Using a .reg file</span></span>

-   <span data-ttu-id="e99cc-108">VBScript または Windows PowerShell などのスクリプト言語を使用する</span><span class="sxs-lookup"><span data-stu-id="e99cc-108">Using a scripting language such as VBScript or Windows PowerShell</span></span>

<span data-ttu-id="e99cc-109">また、使用できる ADM テンプレートもあります。</span><span class="sxs-lookup"><span data-stu-id="e99cc-109">There is also an ADM template that you can use.</span></span> <span data-ttu-id="e99cc-110">ADM テンプレートの詳細については、を参照してください <https://go.microsoft.com/fwlink/?LinkId=121835> 。</span><span class="sxs-lookup"><span data-stu-id="e99cc-110">For more information about the ADM template, see <https://go.microsoft.com/fwlink/?LinkId=121835>.</span></span>

<span data-ttu-id="e99cc-111">**注意** エラーによりコンピューターが不安定な状態になる可能性があるため、レジストリを編集するときは注意してください。</span><span class="sxs-lookup"><span data-stu-id="e99cc-111">**Caution** Use care when you edit the registry because errors can leave the computer in an unusable state.</span></span> <span data-ttu-id="e99cc-112">レジストリの編集に関連する標準のビジネスプラクティスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="e99cc-112">Be sure to follow your standard business practices that relate to registry edits.</span></span> <span data-ttu-id="e99cc-113">テスト環境で提案されたすべての変更を、運用コンピューターに展開する前に徹底的にテストします。</span><span class="sxs-lookup"><span data-stu-id="e99cc-113">Thoroughly test all proposed changes in a test environment before you deploy them to production computers.</span></span>

 

## <span data-ttu-id="e99cc-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e99cc-114">In This Section</span></span>


<span data-ttu-id="e99cc-115">**重要** 64ビットのコンピューターでは、次のセクションに記載されているキーと値は、HKEY \ _LOCAL \ _MACHINE ¥ pc \\ wow6432node¥の各デバイスにあります。</span><span class="sxs-lookup"><span data-stu-id="e99cc-115">**Important** On a 64-bit computer, the keys and values described in the following sections will be under HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\Client.</span></span>

 

<a href="" id="how-to-reset-the-filesystem-cache"></a>[<span data-ttu-id="e99cc-116">FileSystem キャッシュをリセットする方法</span><span class="sxs-lookup"><span data-stu-id="e99cc-116">How to Reset the FileSystem Cache</span></span>](how-to-reset-the-filesystem-cache.md)  
<span data-ttu-id="e99cc-117">ファイルシステムキャッシュをリセットするために必要な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="e99cc-117">Provides the information that is required to reset the FileSystem cache.</span></span>

<a href="" id="how-to-change-the-size-of-the-filesystem-cache"></a>[<span data-ttu-id="e99cc-118">FileSystem キャッシュのサイズを変更する方法</span><span class="sxs-lookup"><span data-stu-id="e99cc-118">How to Change the Size of the FileSystem Cache</span></span>](how-to-change-the-size-of-the-filesystem-cache.md)  
<span data-ttu-id="e99cc-119">キャッシュのサイズを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e99cc-119">Explains how you can change the size of the cache.</span></span>

<a href="" id="how-to-use-the-cache-space-management-feature"></a>[<span data-ttu-id="e99cc-120">キャッシュ領域管理機能を使用する方法</span><span class="sxs-lookup"><span data-stu-id="e99cc-120">How to Use the Cache Space Management Feature</span></span>](how-to-use-the-cache-space-management-feature.md)  
<span data-ttu-id="e99cc-121">キャッシュスペース管理機能を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e99cc-121">Describes how you can configure the cache space management feature.</span></span>

<a href="" id="how-to-configure-the-client-log-file"></a>[<span data-ttu-id="e99cc-122">クライアント ログ ファイルを構成する方法</span><span class="sxs-lookup"><span data-stu-id="e99cc-122">How to Configure the Client Log File</span></span>](how-to-configure-the-client-log-file.md)  
<span data-ttu-id="e99cc-123">クライアントログファイルを制御するさまざまなレジストリキーの値と、それらを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e99cc-123">Describes the various registry key values that control the client log file and how you can change them.</span></span>

<a href="" id="how-to-configure-user-permissions"></a>[<span data-ttu-id="e99cc-124">ユーザーのアクセス許可を構成する方法</span><span class="sxs-lookup"><span data-stu-id="e99cc-124">How to Configure User Permissions</span></span>](how-to-configure-user-permissions.md)  
<span data-ttu-id="e99cc-125">ユーザーのアクセス許可を制御するレジストリキーを識別し、いくつかのアクセス許可を変更する方法の例を示します。</span><span class="sxs-lookup"><span data-stu-id="e99cc-125">Identifies the registry key that controls the user permissions and gives examples of how you can change some permissions.</span></span>

<a href="" id="how-to-configure-the-client-for-application-package-retrieval"></a>[<span data-ttu-id="e99cc-126">アプリケーション パッケージを取得するためにクライアントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="e99cc-126">How to Configure the Client for Application Package Retrieval</span></span>](how-to-configure-the-client-for-application-package-retrieval.md)  
<span data-ttu-id="e99cc-127">さまざまなソースからパッケージコンテンツ、アイコン、ファイルの種類の関連付けを取得するようにクライアントを構成する方法について説明し、正しいパス形式の例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="e99cc-127">Explains how to configure the client to retrieve package content, icons, and file type associations from different sources, and provides several examples of the correct path format.</span></span>

<a href="" id="how-to-configure-the-client-for-disconnected-operation-mode"></a>[<span data-ttu-id="e99cc-128">非接続操作モードのクライアントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="e99cc-128">How to Configure the Client for Disconnected Operation Mode</span></span>](how-to-configure-the-client-for-disconnected-operation-mode.md)  
<span data-ttu-id="e99cc-129">切断された操作モードに関連するさまざまな設定を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e99cc-129">Provides information about how to configure the various settings associated with disconnected operations mode.</span></span>

<a href="" id="how-to-configure-shortcut-and-file-type-association-behavior"></a>[<span data-ttu-id="e99cc-130">ショートカットとファイルの種類の関連付け動作を構成する方法</span><span class="sxs-lookup"><span data-stu-id="e99cc-130">How to Configure Shortcut and File Type Association Behavior</span></span>](how-to-configure-shortcut-and-file-type-association-behavior-46-only.md)  
<span data-ttu-id="e99cc-131">App-v クライアントでのショートカットとファイルの種類の関連付けを制御するレジストリキーの値について説明し、その構成方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="e99cc-131">Describes the registry key values that control shortcuts and file type associations in the App-V client, and provides details on how to configure them.</span></span>

## <span data-ttu-id="e99cc-132">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e99cc-132">Related topics</span></span>


[<span data-ttu-id="e99cc-133">Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="e99cc-133">Application Virtualization Client</span></span>](application-virtualization-client.md)

 

 





