---
title: MED-V 1.0 リリース ノート
description: MED-V 1.0 リリース ノート
author: dansimp
ms.assetid: 006a3537-5c5b-43b5-8df8-4bf6ddd3cd2f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 683056f768a3d547828996a9b191d58337c21ad6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826594"
---
# <span data-ttu-id="916b9-103">MED-V 1.0 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="916b9-103">MED-V 1.0 Release Notes</span></span>


## <span data-ttu-id="916b9-104">MED-V の既知の問題</span><span class="sxs-lookup"><span data-stu-id="916b9-104">Known Issues with MED-V</span></span>


<span data-ttu-id="916b9-105">このセクションでは、Microsoft Enterprise Desktop Virtualization (MED-V) プラットフォームの一般的な問題に関する最新情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="916b9-105">This section provides the most up-to-date information about general issues with the Microsoft Enterprise Desktop Virtualization (MED-V) platform.</span></span> <span data-ttu-id="916b9-106">これらの問題は製品ドキュメントには記載されていないため、場合によっては、既存の製品ドキュメントに矛盾が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="916b9-106">These issues do not appear in the product documentation and in some cases might contradict existing product documentation.</span></span> <span data-ttu-id="916b9-107">この問題は、可能な限り将来のリリースで解決されます。</span><span class="sxs-lookup"><span data-stu-id="916b9-107">Whenever possible, these issues will be addressed in later releases.</span></span>

### <span data-ttu-id="916b9-108">ファイルのダウンロードが Web リダイレクションルールに従っていない</span><span class="sxs-lookup"><span data-stu-id="916b9-108">File downloads do not follow Web redirection rules</span></span>

<span data-ttu-id="916b9-109">ファイルのダウンロードは、MED-V ワークスペースポリシーで設定された Web リダイレクションルールに従いません。</span><span class="sxs-lookup"><span data-stu-id="916b9-109">File downloads do not follow Web redirection rules set in a MED-V workspace policy.</span></span>

### <span data-ttu-id="916b9-110">コンソールで公開されたアプリケーションウィンドウを全画面表示に拡張すると、表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="916b9-110">When expanding a console-published application window to full screen, it disappears</span></span>

<span data-ttu-id="916b9-111">シームレスな統合モードで構成されている MED-V ワークスペース内で本体に公開されたアプリケーション (cmd.exe など) ウィンドウを展開すると、アプリケーションウィンドウが表示されなくなったり、応答しなくなったりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="916b9-111">If you expand a console-published application (such as cmd.exe) window to full screen inside a MED-V workspace configured in seamless integration mode, the application window might disappear or not respond.</span></span>

### <span data-ttu-id="916b9-112">デスクトップの全モードで作業している場合、デスクトップ上のアイコンの場所が保存されません。</span><span class="sxs-lookup"><span data-stu-id="916b9-112">When working in full desktop mode, icon locations on the desktop are not saved</span></span>

<span data-ttu-id="916b9-113">デスクトップのフルモードで作業している場合、デスクトップ上のアイコンを手動で変更すると、MED-V ワークスペースセッション間では保存されません。</span><span class="sxs-lookup"><span data-stu-id="916b9-113">When working in full desktop mode, manual location changes of icons on the desktop are not saved between MED-V workspace sessions.</span></span>

### <span data-ttu-id="916b9-114">同じ名前のローカルイメージとテストイメージが同じドメイン内に存在することはできません。</span><span class="sxs-lookup"><span data-stu-id="916b9-114">A local image and a test image with the same name cannot exist in the same domain</span></span>

<span data-ttu-id="916b9-115">ローカルイメージがドメインに参加していて、管理者がテストイメージと同じコンピューター名で同じイメージの新しいバージョンを作成した場合、そのテストイメージがドメインに参加したときに、ドメインへの参加アクションが失敗するか、またはローカルイメージがドメインから削除されます。</span><span class="sxs-lookup"><span data-stu-id="916b9-115">If a local image is joined to the domain and the administrator creates a new version of the same image with the same computer name as a test image, when the test image joins the domain, either the join domain action fails or it succeeds and the local image is removed from the domain.</span></span>

### <span data-ttu-id="916b9-116">MED は Windows Aero 機能をサポートしていません</span><span class="sxs-lookup"><span data-stu-id="916b9-116">MED-V does not support Windows Aero features</span></span>

<span data-ttu-id="916b9-117">MED-V は Windows Aero 機能 (Aero フリップ3D など) をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="916b9-117">MED-V does not support Windows Aero features (such as Aero Flip 3D).</span></span>

### <span data-ttu-id="916b9-118">管理コンソールは、コンピューターごとに1つの Windows ユーザーに対してのみ使うことができます。</span><span class="sxs-lookup"><span data-stu-id="916b9-118">The management console can be used by only one Windows user per computer</span></span>

<span data-ttu-id="916b9-119">MED-V 管理コンソールは、管理者と、管理アプリケーションをインストールした Windows ユーザーのみが使用できます。</span><span class="sxs-lookup"><span data-stu-id="916b9-119">The MED-V management console can be used only by administrators and the Windows user who installed the management application.</span></span>

### <span data-ttu-id="916b9-120">MED-V サーバー構成ユーティリティは、MED-V Server サービスコンテキストではなく、ユーザーコンテキストの下で Microsoft SQL Server の接続性をテストします</span><span class="sxs-lookup"><span data-stu-id="916b9-120">The MED-V Server configuration utility tests Microsoft SQL Server connectivity under user context rather than under MED-V Server service context</span></span>

<span data-ttu-id="916b9-121">MED は、MED-V Server サービスコンテキストを使って、Microsoft SQL Server レポートデータベースからレポートを収集します。</span><span class="sxs-lookup"><span data-stu-id="916b9-121">MED-V uses MED-V Server service context to collect reports from the Microsoft SQL Server reports database.</span></span> <span data-ttu-id="916b9-122">MED-V サーバー構成ユーティリティは、データベースを確認し、データベース接続文字列をテストします。</span><span class="sxs-lookup"><span data-stu-id="916b9-122">The MED-V Server configuration utility verifies the database and tests the database connection string.</span></span> <span data-ttu-id="916b9-123">この方法では、データベースへの MED-V Server サービスへのアクセスは検証されません。</span><span class="sxs-lookup"><span data-stu-id="916b9-123">It does not validate the access of MED-V Server service to the database.</span></span>

 

 





