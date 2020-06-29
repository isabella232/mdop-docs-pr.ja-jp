---
title: SFTMIME コマンドリファレンス
description: SFTMIME コマンドリファレンス
author: dansimp
ms.assetid: a4a69228-9dd3-4623-b773-899d03c0cf10
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 47aac9110febaf3f349461d74fef840326b1c6e4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815347"
---
# <span data-ttu-id="a38fc-103">SFTMIME コマンドリファレンス</span><span class="sxs-lookup"><span data-stu-id="a38fc-103">SFTMIME Command Reference</span></span>


<span data-ttu-id="a38fc-104">SFTMIME は、多くのクライアント構成の詳細を管理できるアプリケーションの仮想化 (App-v) によって使用されるコマンドラインインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="a38fc-104">SFTMIME is a command-line interface used by Application Virtualization (App-V) that enables you to manage many client configuration details.</span></span> <span data-ttu-id="a38fc-105">このセクションには、すべてのコマンドとそのパラメーターが含まれており、それぞれについて簡単に説明しています。</span><span class="sxs-lookup"><span data-stu-id="a38fc-105">This section contains all the commands and their parameters, with a brief description of each.</span></span>

**<span data-ttu-id="a38fc-106">重要</span><span class="sxs-lookup"><span data-stu-id="a38fc-106">Important</span></span>**  
-   <span data-ttu-id="a38fc-107">バックスラッシュ文字は必ず前にバックスラッシュを使ってエスケープする必要があります。それ以外の場合は、パスが正しく解析されません。</span><span class="sxs-lookup"><span data-stu-id="a38fc-107">All backslash characters must be escaped using a preceding backslash, or the path will not be parsed correctly.</span></span>

-   <span data-ttu-id="a38fc-108">呼び出しプログラムを使って、 **CreateProcess**を使って SFTMIME を呼び出す場合は、最初のパラメーターが sftmime.exe のパスであることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a38fc-108">If you are using a calling program to invoke SFTMIME with **CreateProcess**, you must ensure that the first parameter is the path to sftmime.exe.</span></span>

-   <span data-ttu-id="a38fc-109">SFTMIME **QUERY OBJ**コマンドの出力を、 **findstr**コマンドにパイプして文字列を検索することはできません。</span><span class="sxs-lookup"><span data-stu-id="a38fc-109">The output of the SFTMIME **QUERY OBJ** command cannot be piped to the **findstr** command to search for a string.</span></span>

-   <span data-ttu-id="a38fc-110">**グローバル**スイッチを使用するには、ローカル管理者の権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="a38fc-110">Use of the **GLOBAL** switch requires local administrator rights.</span></span>

-   <span data-ttu-id="a38fc-111">短いパスと相対パスを使用すると、予期しない結果になる可能性があるため、回避する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a38fc-111">Use of short paths and relative paths can lead to unexpected results and should be avoided.</span></span> <span data-ttu-id="a38fc-112">常に完全なパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="a38fc-112">Always use full paths.</span></span>

 

## <span data-ttu-id="a38fc-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a38fc-113">In This Section</span></span>


[<span data-ttu-id="a38fc-114">ADD APP</span><span class="sxs-lookup"><span data-stu-id="a38fc-114">ADD APP</span></span>](add-app.md)

[<span data-ttu-id="a38fc-115">ADD PACKAGE</span><span class="sxs-lookup"><span data-stu-id="a38fc-115">ADD PACKAGE</span></span>](add-package.md)

[<span data-ttu-id="a38fc-116">ADD SERVER</span><span class="sxs-lookup"><span data-stu-id="a38fc-116">ADD SERVER</span></span>](add-server.md)

[<span data-ttu-id="a38fc-117">ADD TYPE</span><span class="sxs-lookup"><span data-stu-id="a38fc-117">ADD TYPE</span></span>](add-type.md)

[<span data-ttu-id="a38fc-118">CLEAR APP</span><span class="sxs-lookup"><span data-stu-id="a38fc-118">CLEAR APP</span></span>](clear-app.md)

[<span data-ttu-id="a38fc-119">CLEAR OBJ</span><span class="sxs-lookup"><span data-stu-id="a38fc-119">CLEAR OBJ</span></span>](clear-obj.md)

[<span data-ttu-id="a38fc-120">CONFIGURE APP</span><span class="sxs-lookup"><span data-stu-id="a38fc-120">CONFIGURE APP</span></span>](configure-app.md)

[<span data-ttu-id="a38fc-121">CONFIGURE PACKAGE</span><span class="sxs-lookup"><span data-stu-id="a38fc-121">CONFIGURE PACKAGE</span></span>](configure-package.md)

[<span data-ttu-id="a38fc-122">CONFIGURE SERVER</span><span class="sxs-lookup"><span data-stu-id="a38fc-122">CONFIGURE SERVER</span></span>](configure-server.md)

[<span data-ttu-id="a38fc-123">CONFIGURE TYPE</span><span class="sxs-lookup"><span data-stu-id="a38fc-123">CONFIGURE TYPE</span></span>](configure-type.md)

[<span data-ttu-id="a38fc-124">DELETE APP</span><span class="sxs-lookup"><span data-stu-id="a38fc-124">DELETE APP</span></span>](delete-app.md)

[<span data-ttu-id="a38fc-125">DELETE OBJ</span><span class="sxs-lookup"><span data-stu-id="a38fc-125">DELETE OBJ</span></span>](delete-obj.md)

[<span data-ttu-id="a38fc-126">DELETE PACKAGE</span><span class="sxs-lookup"><span data-stu-id="a38fc-126">DELETE PACKAGE</span></span>](delete-package.md)

[<span data-ttu-id="a38fc-127">DELETE SERVER</span><span class="sxs-lookup"><span data-stu-id="a38fc-127">DELETE SERVER</span></span>](delete-server.md)

[<span data-ttu-id="a38fc-128">DELETE TYPE</span><span class="sxs-lookup"><span data-stu-id="a38fc-128">DELETE TYPE</span></span>](delete-type.md)

[<span data-ttu-id="a38fc-129">HELP</span><span class="sxs-lookup"><span data-stu-id="a38fc-129">HELP</span></span>](help.md)

[<span data-ttu-id="a38fc-130">LOAD APP</span><span class="sxs-lookup"><span data-stu-id="a38fc-130">LOAD APP</span></span>](load-app.md)

[<span data-ttu-id="a38fc-131">LOAD PACKAGE</span><span class="sxs-lookup"><span data-stu-id="a38fc-131">LOAD PACKAGE</span></span>](load-package.md)

[<span data-ttu-id="a38fc-132">LOCK APP</span><span class="sxs-lookup"><span data-stu-id="a38fc-132">LOCK APP</span></span>](lock-app.md)

[<span data-ttu-id="a38fc-133">PUBLISH APP</span><span class="sxs-lookup"><span data-stu-id="a38fc-133">PUBLISH APP</span></span>](publish-app.md)

[<span data-ttu-id="a38fc-134">PUBLISH PACKAGE</span><span class="sxs-lookup"><span data-stu-id="a38fc-134">PUBLISH PACKAGE</span></span>](publish-package.md)

[<span data-ttu-id="a38fc-135">QUERY OBJ</span><span class="sxs-lookup"><span data-stu-id="a38fc-135">QUERY OBJ</span></span>](query-obj.md)

[<span data-ttu-id="a38fc-136">REFRESH SERVER</span><span class="sxs-lookup"><span data-stu-id="a38fc-136">REFRESH SERVER</span></span>](refresh-server.md)

[<span data-ttu-id="a38fc-137">REPAIR APP</span><span class="sxs-lookup"><span data-stu-id="a38fc-137">REPAIR APP</span></span>](repair-app.md)

[<span data-ttu-id="a38fc-138">UNLOAD APP</span><span class="sxs-lookup"><span data-stu-id="a38fc-138">UNLOAD APP</span></span>](unload-app.md)

[<span data-ttu-id="a38fc-139">UNLOAD PACKAGE</span><span class="sxs-lookup"><span data-stu-id="a38fc-139">UNLOAD PACKAGE</span></span>](unload-package.md)

[<span data-ttu-id="a38fc-140">UNLOCK APP</span><span class="sxs-lookup"><span data-stu-id="a38fc-140">UNLOCK APP</span></span>](unlock-app.md)

[<span data-ttu-id="a38fc-141">UNPUBLISH PACKAGE</span><span class="sxs-lookup"><span data-stu-id="a38fc-141">UNPUBLISH PACKAGE</span></span>](unpublish-package.md)

 

 





