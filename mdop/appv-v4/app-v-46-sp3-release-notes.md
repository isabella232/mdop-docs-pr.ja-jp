---
title: App-V 4.6 SP3 リリース ノート
description: App-V 4.6 SP3 リリース ノート
author: dansimp
ms.assetid: 206fadeb-59cc-47b4-836f-191ab1c27ff8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: dd0b82c5e12cbe161066a7f4a4e0932cb92cca42
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819794"
---
# <span data-ttu-id="c3178-103">App-V 4.6 SP3 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="c3178-103">App-V 4.6 SP3 Release Notes</span></span>


<span data-ttu-id="c3178-104">これらのリリースノートを検索するには、CTRL キーを押しながら F キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c3178-104">To search these Release Notes, press CTRL+F.</span></span>

<span data-ttu-id="c3178-105">Microsoft Application Virtualization (App-v) 管理システムをインストールする前に、これらのリリースノートをよくお読みください。</span><span class="sxs-lookup"><span data-stu-id="c3178-105">Read these Release Notes thoroughly before you install the Microsoft Application Virtualization (App-V) Management System.</span></span> <span data-ttu-id="c3178-106">これらのリリースノートには、Application Virtualization (App-v) 4.6 SP3 を正常にインストールするために役立つ情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c3178-106">These Release Notes contain information that helps you successfully install Application Virtualization (App-V)4.6 SP3.</span></span> <span data-ttu-id="c3178-107">このドキュメントには、製品のドキュメントでは利用できない情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c3178-107">This document contains information that is not available in the product documentation.</span></span> <span data-ttu-id="c3178-108">これらのリリースノートと他の App-v のドキュメントの間に違いがある場合は、最新の変更を、権威を持つものとして扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3178-108">If there is a difference between these Release Notes and other App-V documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="c3178-109">これらのリリースノートは、この製品に含まれているコンテンツに代わるものです。</span><span class="sxs-lookup"><span data-stu-id="c3178-109">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="c3178-110">セキュリティの脆弱性とウイルスから保護する</span><span class="sxs-lookup"><span data-stu-id="c3178-110">Protect Against Security Vulnerabilities and Viruses</span></span>


<span data-ttu-id="c3178-111">セキュリティの脆弱性やウイルスから保護するために、インストールされている新しいソフトウェアに使用できる最新のセキュリティ更新プログラムをインストールすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="c3178-111">To help protect against security vulnerabilities and viruses, it is important to install the latest available security updates for any new software being installed.</span></span> <span data-ttu-id="c3178-112">詳細については、 [Microsoft セキュリティ web サイト](https://go.microsoft.com/fwlink/?LinkId=3482)() を参照してください https://go.microsoft.com/fwlink/?LinkId=3482) 。</span><span class="sxs-lookup"><span data-stu-id="c3178-112">For more information, see the [Microsoft Security website](https://go.microsoft.com/fwlink/?LinkId=3482) (https://go.microsoft.com/fwlink/?LinkId=3482).</span></span>

## <span data-ttu-id="c3178-113">Application Virtualization 4.6 SP3 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="c3178-113">Known Issues with Application Virtualization4.6 SP3</span></span>


<span data-ttu-id="c3178-114">このセクションでは、Microsoft Application Virtualization (App-v) 4.6 SP3 の問題に関する最新情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="c3178-114">This section provides the most up-to-date information about issues with Microsoft Application Virtualization (App-V)4.6SP3.</span></span> <span data-ttu-id="c3178-115">これらの問題は製品ドキュメントには記載されていないため、場合によっては、既存の製品ドキュメントに矛盾が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="c3178-115">These issues do not appear in the product documentation and in some cases might contradict existing product documentation.</span></span> <span data-ttu-id="c3178-116">可能であれば、以降のリリースでこの問題に対処します。</span><span class="sxs-lookup"><span data-stu-id="c3178-116">When it is possible, these issues will be addressed in later releases.</span></span>

### <span data-ttu-id="c3178-117">仮想環境内で Microsoft Windows 8.1 上のインターネット Explorer11 を使用してハイパーリンクを開くことができない</span><span class="sxs-lookup"><span data-stu-id="c3178-117">Unable to open hyperlinks using Internet Explorer11 on Microsoft Windows 8.1 within the Virtual Environment</span></span>

<span data-ttu-id="c3178-118">仮想環境内からハイパーリンクを開こうとすると、Windows 8.1 で Internet Explorer 11 を使用すると失敗します。</span><span class="sxs-lookup"><span data-stu-id="c3178-118">Attempting to open hyperlinks from within a virtual environment will fail on Windows 8.1 using Internet Explorer 11.</span></span> <span data-ttu-id="c3178-119">これは、Internet Explorer 11 が既定で有効になっている拡張保護モード (EPM) を使用するようになったためです。これにより、App-v は、必要なレジストリキー、ファイル、通信ポートオブジェクトにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="c3178-119">This is because Internet Explorer 11 now ships with the Enhanced Protection Mode (EPM) enabled by default and this causes App-V to be unable to access required registry keys, files and communication port objects.</span></span>

<span data-ttu-id="c3178-120">回避策: App-v パッケージを開く前に、インターネット Explorer11 の EPM を無効にします。</span><span class="sxs-lookup"><span data-stu-id="c3178-120">WORKAROUND: Disable EPM in Internet Explorer11 before opening an App-V package.</span></span> <span data-ttu-id="c3178-121">これにより、仮想環境内から Internet Explorer を開くことができるようになります。</span><span class="sxs-lookup"><span data-stu-id="c3178-121">This will allow you to open Internet Explorer from within the virtual environment.</span></span>

## <span data-ttu-id="c3178-122">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c3178-122">Related topics</span></span>


[<span data-ttu-id="c3178-123">Microsoft Application Virtualization 4.6 SP3 について</span><span class="sxs-lookup"><span data-stu-id="c3178-123">About Microsoft Application Virtualization 4.6 SP3</span></span>](about-microsoft-application-virtualization-46-sp3.md)

 

 





