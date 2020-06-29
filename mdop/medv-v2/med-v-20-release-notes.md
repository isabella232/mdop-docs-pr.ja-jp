---
title: MED-V 2.0 リリース ノート
description: MED-V 2.0 リリース ノート
author: dansimp
ms.assetid: b8f7d938-566e-434c-b4b8-28b67cdfd0b1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: b4268b7bac6505d315ed0f23d657d2b299b7ab93
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826094"
---
# <span data-ttu-id="b6f44-103">MED-V 2.0 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="b6f44-103">MED-V 2.0 Release Notes</span></span>


<span data-ttu-id="b6f44-104">更新: 2011 年3月10日</span><span class="sxs-lookup"><span data-stu-id="b6f44-104">Updated: March 10, 2011</span></span>

**<span data-ttu-id="b6f44-105">これらのリリースノートを検索するには、CTRL キーを押しながら F キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b6f44-105">To search these release notes, press CTRL+F.</span></span>**

<span data-ttu-id="b6f44-106">Microsoft Enterprise デスクトップ仮想化 (MED-V) 2.0 プラットフォームをインストールする前に、これらのリリースノートをよくお読みください。</span><span class="sxs-lookup"><span data-stu-id="b6f44-106">Read these release notes thoroughly before you install the Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 platform.</span></span> <span data-ttu-id="b6f44-107">これらのリリースノートには、MED-V 2.0 を正常にインストールするために必要な情報が含まれており、製品のドキュメントでは提供されていない情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b6f44-107">These release notes contain information that is required to successfully install MED-V 2.0and contain information that is not available in the product documentation.</span></span> <span data-ttu-id="b6f44-108">リリースノートとその他の MED-V platform のドキュメントの間に違いがある場合は、最新の変更を、権限のあるものとして扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6f44-108">If there is a difference between these release notes and other MED-V platform documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="b6f44-109">これらのリリースノートは、この製品に含まれているコンテンツに置き換わるものです。</span><span class="sxs-lookup"><span data-stu-id="b6f44-109">These release notes supersede the content included with this product.</span></span>

## <span data-ttu-id="b6f44-110">製品ドキュメントについて</span><span class="sxs-lookup"><span data-stu-id="b6f44-110">About the Product Documentation</span></span>


<span data-ttu-id="b6f44-111">Microsoft Enterprise デスクトップ仮想化 (MED-V) 2.0 のドキュメントは製品と共に配布され、 [Microsoft Enterprise Desktop Virtualization 2.0](https://go.microsoft.com/fwlink/?LinkID=207065) () にも含まれてい https://go.microsoft.com/fwlink/?LinkId=207065) ます。</span><span class="sxs-lookup"><span data-stu-id="b6f44-111">Documentation for Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 is distributed with the product and is also located at [Microsoft Enterprise Desktop Virtualization 2.0](https://go.microsoft.com/fwlink/?LinkID=207065) (https://go.microsoft.com/fwlink/?LinkId=207065).</span></span>

## <span data-ttu-id="b6f44-112">セキュリティの脆弱性とウイルスから保護する</span><span class="sxs-lookup"><span data-stu-id="b6f44-112">Protect Against Security Vulnerabilities and Viruses</span></span>


<span data-ttu-id="b6f44-113">セキュリティの脆弱性やウイルスから保護するために、インストールされている新しいソフトウェアには、使用可能な最新のセキュリティ更新プログラムをインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b6f44-113">To help protect against security vulnerabilities and viruses, we recommend that you install the latest available security updates for any new software being installed.</span></span> <span data-ttu-id="b6f44-114">詳細については、「 [Microsoft セキュリティ](https://go.microsoft.com/fwlink/?LinkId=3482)(」を参照してください https://go.microsoft.com/fwlink/?LinkId=3482) 。</span><span class="sxs-lookup"><span data-stu-id="b6f44-114">For more information, see [Microsoft Security](https://go.microsoft.com/fwlink/?LinkId=3482) (https://go.microsoft.com/fwlink/?LinkId=3482).</span></span>

## <span data-ttu-id="b6f44-115">MED-V 2.0 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="b6f44-115">Known Issues with MED-V 2.0</span></span>


<span data-ttu-id="b6f44-116">このセクションでは、Microsoft Enterprise デスクトップ仮想化 (MED-V) 2.0 プラットフォームの問題に関する最新情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="b6f44-116">This section provides the most up-to-date information about issues with the Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 platform.</span></span> <span data-ttu-id="b6f44-117">これらの問題は製品ドキュメントには記載されていないため、場合によっては、既存の製品ドキュメントに矛盾が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="b6f44-117">These issues do not appear in the product documentation and in some cases might contradict existing product documentation.</span></span> <span data-ttu-id="b6f44-118">可能であれば、以降のリリースでこの問題に対処します。</span><span class="sxs-lookup"><span data-stu-id="b6f44-118">When it is possible, these issues will be addressed in later releases.</span></span>

<span data-ttu-id="b6f44-119">**注** 現在、MED-V 2.0 には既知の問題はありません。</span><span class="sxs-lookup"><span data-stu-id="b6f44-119">**Note** There are currently no known issues with MED-V 2.0.</span></span>

 

## <span data-ttu-id="b6f44-120">リリースノートの著作権情報</span><span class="sxs-lookup"><span data-stu-id="b6f44-120">Release Notes Copyright Information</span></span>


<span data-ttu-id="b6f44-121">このドキュメントは "現在のところ" として提供されています。</span><span class="sxs-lookup"><span data-stu-id="b6f44-121">This document is provided “as-is”.</span></span> <span data-ttu-id="b6f44-122">このドキュメントで説明されている情報とビュー (URL などのインターネット web サイトの参照を含む) は、予告なしに変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b6f44-122">Information and views expressed in this document, including URL and other Internet website references, may change without notice.</span></span> <span data-ttu-id="b6f44-123">使用のリスクを負うことができます。</span><span class="sxs-lookup"><span data-stu-id="b6f44-123">You bear the risk of using it.</span></span>

<span data-ttu-id="b6f44-124">ここに示すいくつかの例は、例示のためだけに用意されており、架空のものでもあります。</span><span class="sxs-lookup"><span data-stu-id="b6f44-124">Some examples depicted herein are provided for illustration only and are fictitious.</span></span><span data-ttu-id="b6f44-125">実際の関連付けや接続は意図していないか、または推定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6f44-125">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="b6f44-126">このドキュメントは、マイクロソフト製品に含まれる知的財産に対していかなる法的権利も付与しません。</span><span class="sxs-lookup"><span data-stu-id="b6f44-126">This document does not provide you with any legal rights to any intellectual property in any Microsoft product.</span></span> <span data-ttu-id="b6f44-127">このドキュメントは、Microsoft にとって社外秘であり、所有権を持っています。</span><span class="sxs-lookup"><span data-stu-id="b6f44-127">This document is confidential and proprietary to Microsoft.</span></span> <span data-ttu-id="b6f44-128">このサービスは公開されており、守秘義務契約に基づいてのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6f44-128">It is disclosed and can be used only pursuant to a nondisclosure agreement.</span></span>



<span data-ttu-id="b6f44-129">Microsoft、Active Directory、ActiveSync、MS-DOS、Windows、WindowsServer、Windows Vista は、Microsoft の会社グループの商標です。</span><span class="sxs-lookup"><span data-stu-id="b6f44-129">Microsoft, Active Directory, ActiveSync, MS-DOS, Windows, WindowsServer, and Windows Vista are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="b6f44-130">その他のすべての商標は、該当する所有者に帰属します。</span><span class="sxs-lookup"><span data-stu-id="b6f44-130">All other trademarks are property of their respective owners.</span></span>

 

 





