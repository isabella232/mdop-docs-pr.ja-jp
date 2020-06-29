---
title: 仮想環境について
description: 仮想環境について
author: dansimp
ms.assetid: e03a8c72-56c1-4ae9-aa45-0283c50a154c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 15f3ae29ae8d5586f83baa98ea6821e09ae5c305
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822394"
---
# <span data-ttu-id="c6ddf-103">仮想環境について</span><span class="sxs-lookup"><span data-stu-id="c6ddf-103">About Virtual Environments</span></span>


<span data-ttu-id="c6ddf-104">仮想アプリケーションは仮想環境で実行されます。</span><span class="sxs-lookup"><span data-stu-id="c6ddf-104">Virtual applications run in virtual environments.</span></span> <span data-ttu-id="c6ddf-105">仮想環境では、デスクトップ、ノート pc、リモートデスクトップセッションホスト (RDSession Host) サーバーで、各アプリケーションをインストールしなくても、ホストオペレーティングシステムのインストールや変更なしに実行できます。</span><span class="sxs-lookup"><span data-stu-id="c6ddf-105">Virtual environments enable each application to run on a desktop, laptop, or Remote Desktop Session Host (RDSession Host) server without installation and alteration of the host operating system.</span></span> <span data-ttu-id="c6ddf-106">各アプリケーションは、仮想環境で独自の構成情報を保持します。</span><span class="sxs-lookup"><span data-stu-id="c6ddf-106">Each application carries its own configuration information in the virtual environment.</span></span> <span data-ttu-id="c6ddf-107">結果として、多くのアプリケーションは同じコンピューター上の他のアプリケーションと並行して動作しますが、競合は発生しません。</span><span class="sxs-lookup"><span data-stu-id="c6ddf-107">As a result, many applications run side by side with other applications on the same computer without any conflicts.</span></span>

<span data-ttu-id="c6ddf-108">仮想アプリケーションはローカルで実行されるため、ローカルにインストールされているアプリケーションから期待されるように、完全なパフォーマンス、機能、ローカルサービスへのアクセスが実行されます。</span><span class="sxs-lookup"><span data-stu-id="c6ddf-108">Virtual applications run locally, so they run with the full performance, functionality, and access to local services that you would expect from any application installed locally.</span></span>

<span data-ttu-id="c6ddf-109">各アプリケーションは仮想環境で実行されるため、次の問題が軽減されます。</span><span class="sxs-lookup"><span data-stu-id="c6ddf-109">Because each application runs in a virtual environment, the following problems are reduced:</span></span>

-   <span data-ttu-id="c6ddf-110">アプリケーションの競合—アプリケーションの仮想化を使用していない環境では、すべてのアプリケーションを徹底的にテストして、インストールされている他のアプリケーションと干渉しないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6ddf-110">Application conflicts—In environments that do not use Application Virtualization, you must thoroughly test every application to ensure that it does not interfere with other installed applications.</span></span>

-   <span data-ttu-id="c6ddf-111">回帰テスト: アプリケーションは基になるオペレーティングシステムを変更しないため、時間のかかる回帰テストは不要です。</span><span class="sxs-lookup"><span data-stu-id="c6ddf-111">Regression testing—Because the application does not change the underlying operating system, lengthy regression testing is eliminated.</span></span>

-   <span data-ttu-id="c6ddf-112">バージョンの非互換性—同じアプリケーションの異なるバージョンを同じコンピューターで同時に実行できます。</span><span class="sxs-lookup"><span data-stu-id="c6ddf-112">Version incompatibilities—Different versions of the same application can run simultaneously on the same computer.</span></span>

-   <span data-ttu-id="c6ddf-113">マルチユーザーアクセス: マルチユーザーモードで実行されていないアプリケーションであり、RDSession ホスト内で実行できないため、単一の RDSession ホスト上で複数のユーザーに対して正しく機能するようになりました。</span><span class="sxs-lookup"><span data-stu-id="c6ddf-113">Multiuser access—Applications that do not run in multiuser mode, and therefore cannot run within an RDSession Host, can now do so and function correctly for multiple users on a single RDSession Host.</span></span>

-   <span data-ttu-id="c6ddf-114">Multitenancy の問題: 異なる構成を使用する同じアプリケーションの2つのインスタンスを、同じコンピューターで同時に実行できます。</span><span class="sxs-lookup"><span data-stu-id="c6ddf-114">Multitenancy issues—Two instances of the same application that use different configurations can run on the same computer at the same time.</span></span>

-   <span data-ttu-id="c6ddf-115">サーバー siloing-多くの個別のサーバーファームの必要性が排除されます。</span><span class="sxs-lookup"><span data-stu-id="c6ddf-115">Server siloing—The need for many separate server farms is eliminated.</span></span>

<span data-ttu-id="c6ddf-116">仮想環境には、各アプリケーションの仮想レジストリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c6ddf-116">Virtual environments include a virtual registry for each application.</span></span> <span data-ttu-id="c6ddf-117">1つのアプリケーションによって作成されたレジストリ設定は、他のアプリケーションや、Regedit などのユーティリティから表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="c6ddf-117">Registry settings created by one application cannot be seen by other applications or utilities such as Regedit.</span></span> <span data-ttu-id="c6ddf-118">レジストリ全体をコピーするのではなく、仮想レジストリで*オーバーレイ*メソッドを使います。</span><span class="sxs-lookup"><span data-stu-id="c6ddf-118">Rather than copying the entire registry, the virtual registry uses an *overlay* method.</span></span> <span data-ttu-id="c6ddf-119">クライアントレジストリの項目は、そのレジストリ項目の仮想コピーが仮想レジストリに含まれていない限り、アプリケーションで読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="c6ddf-119">Items in the client registry can be read by the application as long as a virtual copy of that registry item is not included in the virtual registry.</span></span> <span data-ttu-id="c6ddf-120">レジストリへのすべてのアプリケーションの書き込みは、仮想レジストリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="c6ddf-120">All application writes to the registry are contained in the virtual registry.</span></span>

<span data-ttu-id="c6ddf-121">仮想環境には、仮想ファイルシステムやその他の仮想コンポーネントも含まれます。仮想サービスや仮想 COM などの仮想コンポーネントも含まれます。</span><span class="sxs-lookup"><span data-stu-id="c6ddf-121">Virtual environments also include a virtual file system and other virtual components, including virtual services and virtual COM.</span></span>

## <span data-ttu-id="c6ddf-122">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c6ddf-122">Related topics</span></span>


[<span data-ttu-id="c6ddf-123">Application Virtualization Client Management Console の概要</span><span class="sxs-lookup"><span data-stu-id="c6ddf-123">Application Virtualization Client Management Console Overview</span></span>](application-virtualization-client-management-console-overview.md)

 

 





