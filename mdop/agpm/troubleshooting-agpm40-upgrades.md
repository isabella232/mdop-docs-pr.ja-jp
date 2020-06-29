---
title: AGPM のアップグレードのトラブルシューティング
description: AGPM のアップグレードのトラブルシューティング
author: dansimp
ms.assetid: 1abbf0c1-fd32-46a8-a3ba-c005f066523d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2089eac51803dca60da51f61ebdb112fbf0bda08
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818247"
---
# <span data-ttu-id="96e40-103">AGPM のアップグレードのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="96e40-103">Troubleshooting AGPM Upgrades</span></span>

<span data-ttu-id="96e40-104">このセクションでは、高度なグループポリシー管理 (AGPM) サーバーを新しいバージョン (AGPM 4.0 から AGPM 4.3) にアップグレードするときに発生する可能性がある一般的な問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="96e40-104">This section lists common issues that you may encounter when you upgrade your Advanced Group Policy Management (AGPM) server to a newer version (e.g. AGPM 4.0 to AGPM 4.3).</span></span> <span data-ttu-id="96e40-105">ここに記載されていない問題を診断するには、[トラブルシューティング](troubleshooting-agpm-agpm40.md)のヒントを表示するか、Agpm 管理者 (フルコントロール) でログとトレースを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="96e40-105">To diagnose issues not listed here, it may be helpful to view the [Troubleshooting AGPM](troubleshooting-agpm-agpm40.md) or for an AGPM Administrator (Full Control) to use logging and tracing.</span></span> <span data-ttu-id="96e40-106">詳細については、「[ログとトレースを構成する](configure-logging-and-tracing-agpm40.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96e40-106">For more information, see [Configure Logging and Tracing](configure-logging-and-tracing-agpm40.md).</span></span>

## <span data-ttu-id="96e40-107">どのような問題が発生していますか?</span><span class="sxs-lookup"><span data-stu-id="96e40-107">What problems are you having?</span></span>

-   [<span data-ttu-id="96e40-108">HTML GPO の相違レポートを生成できませんでした (エラーコード 80004003)</span><span class="sxs-lookup"><span data-stu-id="96e40-108">Failed to generate a HTML GPO difference report (Error code 80004003)</span></span>](#bkmk-error-80004003)

### <a href="" id="bkmk-error-80004003"></a><span data-ttu-id="96e40-109">HTML GPO の相違レポートを生成できませんでした (エラーコード 80004003)</span><span class="sxs-lookup"><span data-stu-id="96e40-109">Failed to generate a HTML GPO difference report (Error code 80004003)</span></span>

-   <span data-ttu-id="96e40-110">**原因**: 不適切なアカウントで AGPM アップグレードパッケージをインストールしている。</span><span class="sxs-lookup"><span data-stu-id="96e40-110">**Cause**: You have installed the AGPM upgrade package with an incorrect account.</span></span>

-   <span data-ttu-id="96e40-111">**解決策**: この問題を解決するには、AGPM 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="96e40-111">**Solution**: You will need to be an AGPM administrator in order to fix this issue.</span></span>
    
    -   <span data-ttu-id="96e40-112">**AGPM サービスアカウント**のユーザー名 & パスワードがわかっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="96e40-112">Ensure you know the username & password of your **AGPM service account**.</span></span>

    -   <span data-ttu-id="96e40-113">Agpm サービスアカウントとして、AGPM サーバーに対話的にログオンします。</span><span class="sxs-lookup"><span data-stu-id="96e40-113">Log onto your AGPM server interactively as your AGPM service account.</span></span>
        
        -   <span data-ttu-id="96e40-114">別のアカウントを使用するとインストールが失敗するため、これは非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="96e40-114">This is critically important, as the install will fail if you use a different account.</span></span>

    -   <span data-ttu-id="96e40-115">AGPM サービスをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="96e40-115">Shutdown the AGPM service.</span></span>
    
    -   <span data-ttu-id="96e40-116">必要な修正プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="96e40-116">Install the required hotfix.</span></span>
    
    -   <span data-ttu-id="96e40-117">AGPM クライアントを使って AGPM に接続し、差異レポートが機能していることをテストします。</span><span class="sxs-lookup"><span data-stu-id="96e40-117">Connect to AGPM using an AGPM client to test that your difference reports are now functioning.</span></span>
    
## <span data-ttu-id="96e40-118">Microsoft Advanced グループポリシー管理 4.0 SP3 の修正プログラムパッケージ1をインストールする</span><span class="sxs-lookup"><span data-stu-id="96e40-118">Install Hotfix Package 1 for Microsoft Advanced Group Policy Management 4.0 SP3</span></span>
    
<span data-ttu-id="96e40-119">**この修正プログラムで修正**された問題: AGPM で、新しいグループポリシーオブジェクト (gpo) を制御または管理するときに、差分レポートを生成できません。</span><span class="sxs-lookup"><span data-stu-id="96e40-119">**Issue fixed in this hotfix**: AGPM can't generate difference reports when it controls or manages new Group Policy Objects (GPOs).</span></span>

<span data-ttu-id="96e40-120">**この更新プログラムの入手方法**: 最新バージョンの Microsoft デスクトップ最適化パック ([2017 年3月のサービスリリース](https://www.microsoft.com/download/details.aspx?id=54967)) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="96e40-120">**How to get this update**: Install the latest version of Microsoft Desktop Optimization Pack ([March 2017 Servicing Release](https://www.microsoft.com/download/details.aspx?id=54967)).</span></span> <span data-ttu-id="96e40-121">詳細については、 [KB 4014009](https://support.microsoft.com/help/4014009/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96e40-121">See [KB 4014009](https://support.microsoft.com/help/4014009/) for more information.</span></span>

<span data-ttu-id="96e40-122">具体的には、[ `AGPM4.0SP1_Server_X64_KB4014009.exe` ダウンロード] ボタンを押した後に表示されるリストから、最初のファイルのみをダウンロードすることを選択できます。</span><span class="sxs-lookup"><span data-stu-id="96e40-122">More specifically, you can choose to download only the first file, `AGPM4.0SP1_Server_X64_KB4014009.exe`, from the list presented after pressing the download button.</span></span>
      
<span data-ttu-id="96e40-123">Microsoft デスクトップ最適化パック (2017 年3月のサービスリリース) へのダウンロードリンクは、[ここ](https://www.microsoft.com/download/details.aspx?id=54967)にあります。</span><span class="sxs-lookup"><span data-stu-id="96e40-123">The download link to the Microsoft Desktop Optimization Pack (March 2017 Servicing Release) can be found [here](https://www.microsoft.com/download/details.aspx?id=54967).</span></span>
      
      
## <span data-ttu-id="96e40-124">参照リンク</span><span class="sxs-lookup"><span data-stu-id="96e40-124">Reference link</span></span>
https://support.microsoft.com/help/3127165/hotfix-package-1-for-microsoft-advanced-group-policy-management-4-0-sp
      
