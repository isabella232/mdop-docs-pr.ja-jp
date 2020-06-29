---
title: App-V 4.6 SP1 リリース ノート
description: App-V 4.6 SP1 リリース ノート
author: dansimp
ms.assetid: aeb6784a-864a-4f4e-976b-40c34dcfd8d6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7081aaf4a04d52bf288d7a76b4a488e2b200c3d6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819837"
---
# <span data-ttu-id="18cc2-103">App-V 4.6 SP1 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="18cc2-103">App-V 4.6 SP1 Release Notes</span></span>


<span data-ttu-id="18cc2-104">これらのリリースノートを検索するには、CTRL キーを押しながら F キーを押します。</span><span class="sxs-lookup"><span data-stu-id="18cc2-104">To search these Release Notes, press CTRL+F.</span></span>

<span data-ttu-id="18cc2-105">**重要** Microsoft Application Virtualization (App-v) 管理システムをインストールする前に、これらのリリースノートをよくお読みください。</span><span class="sxs-lookup"><span data-stu-id="18cc2-105">**Important** Read these Release Notes thoroughly before you install the Microsoft Application Virtualization (App-V) Management System.</span></span> <span data-ttu-id="18cc2-106">これらのリリースノートには、Application Virtualization (App-v) 4.6 SP1 を正常にインストールするために役立つ情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="18cc2-106">These Release Notes contain information that helps you successfully install Application Virtualization (App-V)4.6 SP1.</span></span> <span data-ttu-id="18cc2-107">このドキュメントには、製品のドキュメントでは利用できない情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="18cc2-107">This document contains information that is not available in the product documentation.</span></span> <span data-ttu-id="18cc2-108">これらのリリースノートと他の App-v のドキュメントの間に違いがある場合は、最新の変更を、権威を持つものとして扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="18cc2-108">If there is a difference between these Release Notes and other App-V documentation, the latest change should be considered authoritative.</span></span>

 

## <span data-ttu-id="18cc2-109">セキュリティの脆弱性とウイルスから保護する</span><span class="sxs-lookup"><span data-stu-id="18cc2-109">Protect Against Security Vulnerabilities and Viruses</span></span>


<span data-ttu-id="18cc2-110">セキュリティの脆弱性やウイルスから保護するために、インストールされている新しいソフトウェアに使用できる最新のセキュリティ更新プログラムをインストールすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="18cc2-110">To help protect against security vulnerabilities and viruses, it is important to install the latest available security updates for any new software being installed.</span></span> <span data-ttu-id="18cc2-111">詳細については、 [Microsoft セキュリティ web サイト](https://go.microsoft.com/fwlink/?LinkId=3482)() を参照してください https://go.microsoft.com/fwlink/?LinkId=3482) 。</span><span class="sxs-lookup"><span data-stu-id="18cc2-111">For more information, see the [Microsoft Security website](https://go.microsoft.com/fwlink/?LinkId=3482) (https://go.microsoft.com/fwlink/?LinkId=3482).</span></span>

## <span data-ttu-id="18cc2-112">Application Virtualization 4.6 SP1 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="18cc2-112">Known Issues with Application Virtualization4.6 SP1</span></span>


<span data-ttu-id="18cc2-113">このセクションでは、Microsoft Application Virtualization (App-v) 4.6 SP1 の問題に関する最新情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="18cc2-113">This section provides the most up-to-date information about issues with Microsoft Application Virtualization (App-V)4.6 SP1.</span></span> <span data-ttu-id="18cc2-114">これらの問題は製品ドキュメントには記載されていないため、場合によっては、既存の製品ドキュメントに矛盾が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="18cc2-114">These issues do not appear in the product documentation and in some cases might contradict existing product documentation.</span></span> <span data-ttu-id="18cc2-115">可能であれば、以降のリリースでこの問題に対処します。</span><span class="sxs-lookup"><span data-stu-id="18cc2-115">When it is possible, these issues will be addressed in later releases.</span></span>

### <span data-ttu-id="18cc2-116">SPRT のパスがスラッシュ (/) で終わらない場合は失われます。</span><span class="sxs-lookup"><span data-stu-id="18cc2-116">Path from SPRT is lost if it does not end in forward slash ( / )</span></span>

<span data-ttu-id="18cc2-117">プロジェクトテンプレート内の HREF のパスがスラッシュ () で終わらない場合 **/** 、生成された href にはパスが含まれません。</span><span class="sxs-lookup"><span data-stu-id="18cc2-117">When the path in an HREF in a project template does not end with a forward slash (**/**), the generated HREF does not include the path.</span></span> <span data-ttu-id="18cc2-118">これは、ユーザーが**sprt**ファイルを手動で操作したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="18cc2-118">This occurs when the user manually manipulates the **.sprt** file.</span></span> <span data-ttu-id="18cc2-119">Sequencer を使用する場合は、パスの後にスラッシュ () が常に追加され **/** ます。</span><span class="sxs-lookup"><span data-stu-id="18cc2-119">If you use the sequencer it always adds the forward slash (**/**) after the path.</span></span>

<span data-ttu-id="18cc2-120">回避策: HREF に末尾のスラッシュ () が含まれていることを確認し **/** ます。</span><span class="sxs-lookup"><span data-stu-id="18cc2-120">WORKAROUND Make sure that the HREF has a trailing forward slash (**/**).</span></span>

### <span data-ttu-id="18cc2-121">ユーザーフォルダー名がパッケージ名に対応していません</span><span class="sxs-lookup"><span data-stu-id="18cc2-121">User folder name do not correspond to the package name</span></span>

<span data-ttu-id="18cc2-122">ユーザーとグローバルな .pkg ファイルが含まれているフォルダーには、パッケージ名が含まれていません。</span><span class="sxs-lookup"><span data-stu-id="18cc2-122">Folders that contain user and global .pkg files no longer include the package name.</span></span> <span data-ttu-id="18cc2-123">以前は、パッケージルートフォルダー8.3 の短い名前をフォルダー名の一部として使用するために、App-v クライアントが使用されていました。</span><span class="sxs-lookup"><span data-stu-id="18cc2-123">Previously, the App-V client used to use the package root folder 8.3 short name as part of the folder name.</span></span> <span data-ttu-id="18cc2-124">これにより、簡単に識別することができます。</span><span class="sxs-lookup"><span data-stu-id="18cc2-124">This lets you easily identify it.</span></span> <span data-ttu-id="18cc2-125">App-v 4.6 SP1 sequencer を使用する場合、パッケージのルートフォルダー8.3 の短い名前がランダム文字列になります。</span><span class="sxs-lookup"><span data-stu-id="18cc2-125">When you use the App-V 4.6 SP1 sequencer, the package root folder 8.3 short names are now random strings.</span></span> <span data-ttu-id="18cc2-126">これにより、App-v クライアントを実行しているコンピューター上のパッケージの **.pkg**ファイルを含むフォルダーを特定することが困難になります。</span><span class="sxs-lookup"><span data-stu-id="18cc2-126">This makes it difficult to identify the folders that contain the package’s **.pkg** files on the computer that is running the App-V client.</span></span>

<span data-ttu-id="18cc2-127">回避策: これらのパッケージフォルダーをさらに簡単に識別するには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="18cc2-127">WORKAROUND Use one of the following methods to more easily identify these package folders:</span></span>

1.  <span data-ttu-id="18cc2-128">Sequencer を使用してパッケージを作成する場合は、プライマリアプリケーションフォルダーの8.3 の名前付け規則に従ったフォルダー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="18cc2-128">When you create the package by using the Sequencer, specify a folder name that follows the 8.3 naming convention for the primary application folder.</span></span> <span data-ttu-id="18cc2-129">この名前は、App-v 4.6 の場合と同様に、ユーザーフォルダー名の一部として使用されます。</span><span class="sxs-lookup"><span data-stu-id="18cc2-129">This name will then be used as part of the user folder name as was the case in App-V 4.6.</span></span>

2.  <span data-ttu-id="18cc2-130">Sprj ファイルには、ユーザーフォルダー名の先頭として使用される文字列を表示するタグが含まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="18cc2-130">The .sprj file now contains a tag that displays the string that is used as the beginning of the user folder name.</span></span> <span data-ttu-id="18cc2-131">**PACKAGEROOTFOLDER**要素の**SHORTNAME**要素を使って、名前を確認できます。</span><span class="sxs-lookup"><span data-stu-id="18cc2-131">You can use the **SHORTNAME** element of the **PACKAGEROOTFOLDER** element to determine the name.</span></span>

### <span data-ttu-id="18cc2-132">64プロセッサを搭載しているコンピューターで、App-v 4.6 SP1 を実行します。</span><span class="sxs-lookup"><span data-stu-id="18cc2-132">Running App-V 4.6 SP1 on computers that have more than 64 processors</span></span>

<span data-ttu-id="18cc2-133">64プロセッサ以上がインストールされているコンピューターで App-v 4.6 SP1 を実行した場合、App-v クライアントは失敗します。</span><span class="sxs-lookup"><span data-stu-id="18cc2-133">When you run App-V 4.6 SP1 on computers that have more than 64 processors installed, the App-V client fails.</span></span>

<span data-ttu-id="18cc2-134">回避策なし。</span><span class="sxs-lookup"><span data-stu-id="18cc2-134">WORKAROUND None.</span></span> <span data-ttu-id="18cc2-135">この構成はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="18cc2-135">This configuration is not supported.</span></span> <span data-ttu-id="18cc2-136">64プロセッサ未満の SP1on コンピューターを4.6 実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="18cc2-136">You must run App-V 4.6 SP1on computers that have fewer than 64 processors.</span></span>

### <span data-ttu-id="18cc2-137">Application Virtualization 4.6 SP1 の更新プログラムが、Microsoft Update を使用するすべてのロケールで提供されない</span><span class="sxs-lookup"><span data-stu-id="18cc2-137">Application Virtualization 4.6 SP1 update is not offered on all locales that use Microsoft Update</span></span>

<span data-ttu-id="18cc2-138">Microsoft Update を使用している場合、次の言語ロケールでは、App-v 4.6 SP1 の更新プログラムは使用できません。</span><span class="sxs-lookup"><span data-stu-id="18cc2-138">When you use Microsoft Update, the update for App-V 4.6 SP1 is not available for the following language locales:</span></span>

-   <span data-ttu-id="18cc2-139">カザフ語</span><span class="sxs-lookup"><span data-stu-id="18cc2-139">Kazakh</span></span>

-   <span data-ttu-id="18cc2-140">ヒンディー語</span><span class="sxs-lookup"><span data-stu-id="18cc2-140">Hindi</span></span>

-   <span data-ttu-id="18cc2-141">セルビア語-キリル</span><span class="sxs-lookup"><span data-stu-id="18cc2-141">Serbian-Cyrillic</span></span>

<span data-ttu-id="18cc2-142">回避策: Microsoft Windows Server Update Services (WSUS) を使用している場合は、英語版の更新プログラムを使用するか、Microsoft Update カタログから更新プログラムをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="18cc2-142">WORKAROUND If you are using Microsoft Windows Server Update Services (WSUS) use the English version of the update or download the update from the Microsoft Update Catalog.</span></span>

### <span data-ttu-id="18cc2-143">親パッケージを展開した後は、プラグインをサイドバイサイドコンポーネントと共にシーケンスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="18cc2-143">After expanding the parent package, you cannot sequence a plug-in with side by side components</span></span>

<span data-ttu-id="18cc2-144">[**ツール**] を使用して親パッケージを展開すると、  /  アプリの V シーケンサーコンソールで [パッケージ] が [**ローカルシステム] に展開**され、プラグインと並列コンポーネントの順序を合わせたときに、インストールエラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="18cc2-144">When you expand a parent package by using **Tools** / **Expand Package to Local System** in the App-V Sequencer console and you sequence a plug-in with side by side components, an installation error is returned.</span></span> <span data-ttu-id="18cc2-145">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="18cc2-145">For example:</span></span>

-   **<span data-ttu-id="18cc2-146">HRESULT 0x80073712</span><span class="sxs-lookup"><span data-stu-id="18cc2-146">HRESULT 0x80073712</span></span>**

<span data-ttu-id="18cc2-147">この問題は、sequencer がサイドバイサイドのコンポーネントをレジストリに書き込むときに、次のレジストリキーの値が消去されない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="18cc2-147">This is caused when the sequencer writes the side-by-side component to the registry but does not clear the value for the following registry key:</span></span>

<span data-ttu-id="18cc2-148">HKEY \ _LOCAL \ _MACHINE \\COMPONENTS\\StoreDirty</span><span class="sxs-lookup"><span data-stu-id="18cc2-148">HKEY\_LOCAL\_MACHINE\\COMPONENTS\\StoreDirty</span></span>

<span data-ttu-id="18cc2-149">回避策: sequencer を実行しているコンピューター上で親パッケージを展開した後、次のレジストリキーの値を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="18cc2-149">WORKAROUND After expanding the parent package on the computer that is running the sequencer, you have to delete the value for the following registry key:</span></span>

<span data-ttu-id="18cc2-150">HKEY \ _LOCAL \ _MACHINE \\COMPONENTS\\StoreDirty</span><span class="sxs-lookup"><span data-stu-id="18cc2-150">HKEY\_LOCAL\_MACHINE\\COMPONENTS\\StoreDirty</span></span>

<span data-ttu-id="18cc2-151">値を削除したら、プラグインの順序を指定します。</span><span class="sxs-lookup"><span data-stu-id="18cc2-151">After you have deleted the value, sequence the plug-in.</span></span>

### <span data-ttu-id="18cc2-152">リリースノートの著作権情報</span><span class="sxs-lookup"><span data-stu-id="18cc2-152">Release Notes Copyright Information</span></span>

<span data-ttu-id="18cc2-153">このドキュメントは "現在のところ" として提供されています。</span><span class="sxs-lookup"><span data-stu-id="18cc2-153">This document is provided “as-is”.</span></span> <span data-ttu-id="18cc2-154">このドキュメントで説明されている情報とビュー (URL などのインターネット web サイトの参照など) は、予告なしに変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="18cc2-154">Information and views expressed in this document, such as URL and other Internet website references, may change without notice.</span></span> <span data-ttu-id="18cc2-155">使用のリスクを負うことができます。</span><span class="sxs-lookup"><span data-stu-id="18cc2-155">You bear the risk of using it.</span></span>

<span data-ttu-id="18cc2-156">ここに示すいくつかの例は、例示のためだけに用意されており、架空のものでもあります。</span><span class="sxs-lookup"><span data-stu-id="18cc2-156">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="18cc2-157">実際の関連付けや接続は意図していないか、または推定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="18cc2-157">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="18cc2-158">このドキュメントは、マイクロソフト製品に含まれる知的財産に対していかなる法的権利も付与しません。</span><span class="sxs-lookup"><span data-stu-id="18cc2-158">This document does not provide you with any legal rights to any intellectual property in any Microsoft product.</span></span> <span data-ttu-id="18cc2-159">お客様は、内部的な参照目的に限り、このドキュメントを複製して使用することができます。</span><span class="sxs-lookup"><span data-stu-id="18cc2-159">You may copy and use this document for your internal, reference purposes.</span></span> <span data-ttu-id="18cc2-160">このドキュメントは、内部的な参照目的に合わせて変更できます。</span><span class="sxs-lookup"><span data-stu-id="18cc2-160">You may modify this document for your internal, reference purposes.</span></span>



<span data-ttu-id="18cc2-161">Microsoft、Active Directory、ActiveSync、ActiveX、Excel、SQL Server、windows、windows PowerShell、windows Server、Windows Vista は、Microsoft の会社グループの商標です。</span><span class="sxs-lookup"><span data-stu-id="18cc2-161">Microsoft, Active Directory, ActiveSync, ActiveX, Excel, SQL Server, Windows, Windows PowerShell, Windows Server, and Windows Vista are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="18cc2-162">その他のすべての商標は、該当する所有者に帰属します。</span><span class="sxs-lookup"><span data-stu-id="18cc2-162">All other trademarks are property of their respective owners.</span></span>

 

 





