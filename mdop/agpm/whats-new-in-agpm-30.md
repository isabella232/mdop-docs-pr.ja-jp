---
title: AGPM 3.0 の新機能
description: AGPM 3.0 の新機能
author: dansimp
ms.assetid: 0d082b86-63c5-45ce-9529-6e5f37254f9d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 811a19798e6669ef1cdaf8a53493dbbc2faa007e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818164"
---
# <span data-ttu-id="fc8fe-103">AGPM 3.0 の新機能</span><span class="sxs-lookup"><span data-stu-id="fc8fe-103">What's New in AGPM 3.0</span></span>


<span data-ttu-id="fc8fe-104">Microsoft Advanced グループポリシー管理 (AGPM) 3.0 には、次の新しい機能と変更された機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fc8fe-104">Microsoft Advanced Group Policy Management (AGPM)3.0 includes the following new or changed features:</span></span>

-   <span data-ttu-id="fc8fe-105">32ビットと64ビットのバージョンを含む Service Pack 1 での WindowsServer2008 と WindowsVista のサポート</span><span class="sxs-lookup"><span data-stu-id="fc8fe-105">Support for WindowsServer2008 and WindowsVista with Service Pack 1 that includes 32-bit and 64-bit versions</span></span>

-   <span data-ttu-id="fc8fe-106">インストールプロセスの改善</span><span class="sxs-lookup"><span data-stu-id="fc8fe-106">Improved installation process</span></span>

-   <span data-ttu-id="fc8fe-107">AGPM サーバーがリッスンするポートを変更するための簡素化された手順</span><span class="sxs-lookup"><span data-stu-id="fc8fe-107">Simplified procedure for modifying the port on which the AGPM Server listens</span></span>

-   <span data-ttu-id="fc8fe-108">各 GPO の履歴の詳細情報</span><span class="sxs-lookup"><span data-stu-id="fc8fe-108">More detailed information in the History of each GPO</span></span>

-   <span data-ttu-id="fc8fe-109">AGPM から運用環境へのアクセスを委任する機能</span><span class="sxs-lookup"><span data-stu-id="fc8fe-109">Ability to delegate access to the production environment from AGPM</span></span>

-   <span data-ttu-id="fc8fe-110">アーカイブに保存されている GPO バージョンの数を制限する機能</span><span class="sxs-lookup"><span data-stu-id="fc8fe-110">Ability to limit the number of GPO versions stored in the archive</span></span>

-   <span data-ttu-id="fc8fe-111">AGPM の電子メールセキュリティを構成する機能</span><span class="sxs-lookup"><span data-stu-id="fc8fe-111">Ability to configure e-mail security for AGPM</span></span>

-   <span data-ttu-id="fc8fe-112">AGPM ポリシー設定のわかりやすい名前</span><span class="sxs-lookup"><span data-stu-id="fc8fe-112">Friendlier names for AGPM policy settings</span></span>

-   <span data-ttu-id="fc8fe-113">編集者ロールには、アーカイブから Gpo を削除する権限が必要になりました</span><span class="sxs-lookup"><span data-stu-id="fc8fe-113">The Editor role now requires permission to delete GPOs from the archive</span></span>

<span data-ttu-id="fc8fe-114">さらに、AGPM 3.0 は、次の言語にローカライズされます。</span><span class="sxs-lookup"><span data-stu-id="fc8fe-114">Additionally, AGPM3.0 is localized for the following languages:</span></span>

-   <span data-ttu-id="fc8fe-115">簡体字中国語</span><span class="sxs-lookup"><span data-stu-id="fc8fe-115">Chinese (Simplified)</span></span>

-   <span data-ttu-id="fc8fe-116">中国語 (台湾)</span><span class="sxs-lookup"><span data-stu-id="fc8fe-116">Chinese (Taiwan)</span></span>

-   <span data-ttu-id="fc8fe-117">英語 (米国)</span><span class="sxs-lookup"><span data-stu-id="fc8fe-117">English (U.S.)</span></span>

-   <span data-ttu-id="fc8fe-118">フランス語</span><span class="sxs-lookup"><span data-stu-id="fc8fe-118">French</span></span>

-   <span data-ttu-id="fc8fe-119">ドイツ語</span><span class="sxs-lookup"><span data-stu-id="fc8fe-119">German</span></span>

-   <span data-ttu-id="fc8fe-120">イタリア語</span><span class="sxs-lookup"><span data-stu-id="fc8fe-120">Italian</span></span>

-   <span data-ttu-id="fc8fe-121">日本語</span><span class="sxs-lookup"><span data-stu-id="fc8fe-121">Japanese</span></span>

-   <span data-ttu-id="fc8fe-122">韓国語</span><span class="sxs-lookup"><span data-stu-id="fc8fe-122">Korean</span></span>

-   <span data-ttu-id="fc8fe-123">ポルトガル語 (ブラジル)</span><span class="sxs-lookup"><span data-stu-id="fc8fe-123">Portuguese (Brazil)</span></span>

-   <span data-ttu-id="fc8fe-124">ロシア語</span><span class="sxs-lookup"><span data-stu-id="fc8fe-124">Russian</span></span>

-   <span data-ttu-id="fc8fe-125">スペイン語</span><span class="sxs-lookup"><span data-stu-id="fc8fe-125">Spanish</span></span>

### <span data-ttu-id="fc8fe-126">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="fc8fe-126">Additional considerations</span></span>

<span data-ttu-id="fc8fe-127">AGPM 3.0 では、Windows Server2008 と WindowsVista SP1 がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="fc8fe-127">AGPM3.0 supports Windows Server2008 and WindowsVista with SP1.</span></span> <span data-ttu-id="fc8fe-128">サービスパックがインストールされていない WindowsServer2003 または WindowsVista はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="fc8fe-128">It does not support WindowsServer2003 or WindowsVista with no service packs installed.</span></span> <span data-ttu-id="fc8fe-129">AGPM 2.5 では、これらの環境がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="fc8fe-129">AGPM2.5 supports those environments.</span></span> <span data-ttu-id="fc8fe-130">詳細については、「[インストールする AGPM のバージョンを選択する](choosing-which-version-of-agpm-to-install.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc8fe-130">For more information, see [Choosing Which Version of AGPM to Install](choosing-which-version-of-agpm-to-install.md).</span></span>

 

 





