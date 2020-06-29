---
title: MBAM 1.0 Language Release 更新プログラムの展開
description: MBAM 1.0 Language Release 更新プログラムの展開
author: dansimp
ms.assetid: 9dbd85c3-e470-4752-a90f-25754dd46dab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a819be81594efd9349e3f6c0f6559c2b810bdc9d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812826"
---
# <span data-ttu-id="70d8c-103">MBAM 1.0 Language Release 更新プログラムの展開</span><span class="sxs-lookup"><span data-stu-id="70d8c-103">Deploying the MBAM 1.0 Language Release Update</span></span>


<span data-ttu-id="70d8c-104">Microsoft BitLocker の管理と監視 (MBAM) 1.0 言語リリースは、MBAM の更新プログラムで、新しい言語のサポートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="70d8c-104">Microsoft BitLocker Administration and Monitoring (MBAM)1.0 Language Release is an update to MBAM and includes the support of new languages.</span></span> <span data-ttu-id="70d8c-105">新しい言語は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="70d8c-105">The new languages are:</span></span>

-   <span data-ttu-id="70d8c-106">英語 (en-us)</span><span class="sxs-lookup"><span data-stu-id="70d8c-106">English (en-us)</span></span>

-   <span data-ttu-id="70d8c-107">フランス語 (fr)</span><span class="sxs-lookup"><span data-stu-id="70d8c-107">French (fr)</span></span>

-   <span data-ttu-id="70d8c-108">イタリア語 (it)</span><span class="sxs-lookup"><span data-stu-id="70d8c-108">Italian (it)</span></span>

-   <span data-ttu-id="70d8c-109">ドイツ語 (de)</span><span class="sxs-lookup"><span data-stu-id="70d8c-109">German (de)</span></span>

-   <span data-ttu-id="70d8c-110">スペイン語 (es)</span><span class="sxs-lookup"><span data-stu-id="70d8c-110">Spanish (es)</span></span>

-   <span data-ttu-id="70d8c-111">韓国語 (ko)</span><span class="sxs-lookup"><span data-stu-id="70d8c-111">Korean (ko)</span></span>

-   <span data-ttu-id="70d8c-112">日本語 (ja)</span><span class="sxs-lookup"><span data-stu-id="70d8c-112">Japanese (ja)</span></span>

-   <span data-ttu-id="70d8c-113">ポルトガル語 (ブラジル) (pt-br)</span><span class="sxs-lookup"><span data-stu-id="70d8c-113">Brazilian Portuguese (pt-br)</span></span>

-   <span data-ttu-id="70d8c-114">ロシア語 (ru)</span><span class="sxs-lookup"><span data-stu-id="70d8c-114">Russian (ru)</span></span>

-   <span data-ttu-id="70d8c-115">繁体字中国語 (zh-cn&platform)</span><span class="sxs-lookup"><span data-stu-id="70d8c-115">Chinese Traditional (zh-tw)</span></span>

-   <span data-ttu-id="70d8c-116">簡体字中国語 (zh-cn&platform)</span><span class="sxs-lookup"><span data-stu-id="70d8c-116">Chinese Simplified (zh-cn)</span></span>

<span data-ttu-id="70d8c-117">MBAM 1.0 言語更新プログラムでは、バージョン番号が MBAM 1.0.1237.1 から MBAM 1.0.2001 に変更されます。</span><span class="sxs-lookup"><span data-stu-id="70d8c-117">The MBAM1.0 language update will change the version number from MBAM 1.0.1237.1 to MBAM 1.0.2001.</span></span>

<span data-ttu-id="70d8c-118">追加の言語を追加するために、すべての MBAM 機能を再インストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="70d8c-118">You do not need to reinstall all of the MBAM features in order to add these additional languages.</span></span> <span data-ttu-id="70d8c-119">このトピックでは、新しくサポートされる言語を追加するために必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="70d8c-119">This topic defines the steps required to add the newly supported languages.</span></span>

## <span data-ttu-id="70d8c-120">Mbam international release for MBAM Server 機能を導入する</span><span class="sxs-lookup"><span data-stu-id="70d8c-120">Deploy the MBAM international release to MBAM Server features</span></span>


<span data-ttu-id="70d8c-121">まず、次の MBAM サーバー機能を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70d8c-121">To begin, you must update the following MBAM server features:</span></span>

-   <span data-ttu-id="70d8c-122">コンプライアンスと監査レポート</span><span class="sxs-lookup"><span data-stu-id="70d8c-122">Compliance and Audit Report</span></span>

-   <span data-ttu-id="70d8c-123">管理と監視サーバー</span><span class="sxs-lookup"><span data-stu-id="70d8c-123">Administration and Monitoring Server</span></span>

-   <span data-ttu-id="70d8c-124">ポリシーテンプレート</span><span class="sxs-lookup"><span data-stu-id="70d8c-124">Policy Templates</span></span>

<span data-ttu-id="70d8c-125">次に、同じサーバー上で実行されている MBAM 機能を同時にアップグレードするには、 **MbamSetup.exe**を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70d8c-125">Then, you must run **MbamSetup.exe** to upgrade the MBAM features that run on the same server at the same time.</span></span>

[<span data-ttu-id="70d8c-126">単一サーバーに MBAM Language Update をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="70d8c-126">How to Install the MBAM Language Update on a Single Server</span></span>](how-to-install-the-mbam-language-update-on-a-single-server-mbam-1.md)

[<span data-ttu-id="70d8c-127">分散サーバーに MBAM Language Update をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="70d8c-127">How to Install the MBAM Language Update on Distributed Servers</span></span>](how-to-install-the-mbam-language-update-on-distributed-servers-mbam-1.md)

## <span data-ttu-id="70d8c-128">グループポリシー用の MBAM 言語更新プログラムをインストールする</span><span class="sxs-lookup"><span data-stu-id="70d8c-128">Install the MBAM language update for Group Policies</span></span>


<span data-ttu-id="70d8c-129">MBAM グループポリシーテンプレートは、各管理ワークステーションにインストールすることも、グループポリシーの中央ストアにコピーして、すべてのグループポリシーの管理者が使用できるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="70d8c-129">The MBAM Group Policy templates can be installed on each management workstation or they can be copied to the Group Policy central store, in order to make the templates available to all Group Policy administrators.</span></span> <span data-ttu-id="70d8c-130">ポリシーテンプレートは、ドメインコントローラーに直接インストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="70d8c-130">The policy templates cannot be directly installed on a domain controller.</span></span> <span data-ttu-id="70d8c-131">グループポリシーの中央ストアを使用していない場合は、MBAM グループポリシーを管理する各ドメインコントローラーにポリシーを手動でコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="70d8c-131">If you do not use a Group Policy central store, then you must copy the policies manually to each domain controller that manages MBAM Group Policy.</span></span>

<span data-ttu-id="70d8c-132">MBAM 言語ポリシーテンプレートを追加するには、"ポリシーテンプレート" ロールがワークステーションコンピューター上の同じ場所にインストールされているコンピューター上の%SystemRoot%\\PolicyDefinitions からグループポリシー言語ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="70d8c-132">To add the MBAM language policies templates, copy the Group Policy language files from %SystemRoot%\\PolicyDefinitions on the computer where the “Policy Templates” role was installed to the same location on the workstation computer.</span></span> <span data-ttu-id="70d8c-133">グループポリシーファイルの例をいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="70d8c-133">Here are some examples of Group Policy files:</span></span>

-   <span data-ttu-id="70d8c-134">BitLockerManagement の admx</span><span class="sxs-lookup"><span data-stu-id="70d8c-134">BitLockerManagement.admx</span></span>

-   <span data-ttu-id="70d8c-135">BitLockerUserManagement。 admx</span><span class="sxs-lookup"><span data-stu-id="70d8c-135">BitLockerUserManagement.admx</span></span>

-   <span data-ttu-id="70d8c-136">en-us\\BitLockerManagement.adml</span><span class="sxs-lookup"><span data-stu-id="70d8c-136">en-us\\BitLockerManagement.adml</span></span>

-   <span data-ttu-id="70d8c-137">en-us\\BitLockerUserManagement.adml</span><span class="sxs-lookup"><span data-stu-id="70d8c-137">en-us\\BitLockerUserManagement.adml</span></span>

-   <span data-ttu-id="70d8c-138">fr-fr\\ BitLockerManagement</span><span class="sxs-lookup"><span data-stu-id="70d8c-138">fr-fr\\ BitLockerManagement.adml</span></span>

-   <span data-ttu-id="70d8c-139">fr-fr\\ BitLockerUserManagement</span><span class="sxs-lookup"><span data-stu-id="70d8c-139">fr-fr\\ BitLockerUserManagement.adml</span></span>

-   <span data-ttu-id="70d8c-140">(さらに、サポートされる言語にも同じ)</span><span class="sxs-lookup"><span data-stu-id="70d8c-140">(and similarly for each supported language)</span></span>

## <span data-ttu-id="70d8c-141">MBAM インターナショナルリリースの既知の問題</span><span class="sxs-lookup"><span data-stu-id="70d8c-141">Known issues in the MBAM international release</span></span>


<span data-ttu-id="70d8c-142">このトピックでは、Microsoft BitLocker の管理と、国際リリースの監視に関する既知の問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="70d8c-142">This topic contains known issues for Microsoft BitLocker Administration and Monitoring International Release.</span></span>

[<span data-ttu-id="70d8c-143">MBAM International Release の既知の問題</span><span class="sxs-lookup"><span data-stu-id="70d8c-143">Known Issues in the MBAM International Release</span></span>](known-issues-in-the-mbam-international-release-mbam-1.md)

## <span data-ttu-id="70d8c-144">MBAM 1.0 言語更新プログラムの展開に関するその他のリソース</span><span class="sxs-lookup"><span data-stu-id="70d8c-144">Other resources for deploying the MBAM 1.0 Language Update</span></span>


[<span data-ttu-id="70d8c-145">MBAM 1.0 の展開</span><span class="sxs-lookup"><span data-stu-id="70d8c-145">Deploying MBAM 1.0</span></span>](deploying-mbam-10.md)

 

 





