---
title: カスタム UE-V テンプレートと UE-V Generator の操作
description: カスタム UE-V テンプレートと UE-V Generator の操作
author: dansimp
ms.assetid: 7bb2583a-b032-4800-9bf9-eb33528e1d0d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: db5387254842bfdcf3898089bc12a8e929e3813a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823977"
---
# <span data-ttu-id="15e2e-103">カスタム UE-V テンプレートと UE-V Generator の操作</span><span class="sxs-lookup"><span data-stu-id="15e2e-103">Working with Custom UE-V Templates and the UE-V Generator</span></span>


<span data-ttu-id="15e2e-104">ユーザーコンピューター間でアプリケーションをローミングするために、Microsoft User Experience Virtualization (UE-V) では、*設定場所テンプレート*が使用されます。</span><span class="sxs-lookup"><span data-stu-id="15e2e-104">In order to roam applications between user computers, Microsoft User Experience Virtualization (UE-V) uses *settings location templates*.</span></span> <span data-ttu-id="15e2e-105">一部の設定場所テンプレートは、ユーザーエクスペリエンスの仮想化に含まれています。</span><span class="sxs-lookup"><span data-stu-id="15e2e-105">Some settings location templates are included with User Experience Virtualization.</span></span> <span data-ttu-id="15e2e-106">また、UE-V Generator を使用して、カスタム設定の場所テンプレートを作成、編集、または検証することもできます。</span><span class="sxs-lookup"><span data-stu-id="15e2e-106">You can also create, edit, or validate custom settings location templates with the UE-V Generator.</span></span>

<span data-ttu-id="15e2e-107">UE-V Generator は、アプリケーションがその設定を保存する場所を検出し、キャプチャするために、アプリケーションを監視します。</span><span class="sxs-lookup"><span data-stu-id="15e2e-107">The UE-V Generator monitors an application to discover and capture the locations where the application stores its settings.</span></span> <span data-ttu-id="15e2e-108">監視対象のアプリケーションは、従来のアプリケーションである必要があります。</span><span class="sxs-lookup"><span data-stu-id="15e2e-108">The application being monitored must be a traditional application.</span></span> <span data-ttu-id="15e2e-109">UE-V Generator は、次の種類のアプリケーションの設定場所テンプレートを作成できません。</span><span class="sxs-lookup"><span data-stu-id="15e2e-109">The UE-V Generator cannot create a settings location template for the following application types:</span></span>

-   <span data-ttu-id="15e2e-110">仮想化されたアプリケーション</span><span class="sxs-lookup"><span data-stu-id="15e2e-110">Virtualized applications</span></span>

-   <span data-ttu-id="15e2e-111">ターミナルサービスを通じて提供されるアプリケーション</span><span class="sxs-lookup"><span data-stu-id="15e2e-111">Application offered through terminal services</span></span>

-   <span data-ttu-id="15e2e-112">Java アプリケーション</span><span class="sxs-lookup"><span data-stu-id="15e2e-112">Java applications</span></span>

-   <span data-ttu-id="15e2e-113">Windows 8 アプリケーション</span><span class="sxs-lookup"><span data-stu-id="15e2e-113">Windows 8 applications</span></span>

## <span data-ttu-id="15e2e-114">UE-V Generator を使用して UE-V 設定場所テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="15e2e-114">Create UE-V Settings Location Templates with the UE-V Generator</span></span>


<span data-ttu-id="15e2e-115">UE-V Generator を使って設定場所テンプレートを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="15e2e-115">How to use the UE-V Generator to create settings location templates.</span></span>

[<span data-ttu-id="15e2e-116">UE-V Generator を使用して UE-V 設定場所テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="15e2e-116">Create UE-V Settings Location Templates with the UE-V Generator</span></span>](create-ue-v-settings-location-templates-with-the-ue-v-generator.md)

## <span data-ttu-id="15e2e-117">UE-V Generator を使用して UE-V 設定場所テンプレートを編集する</span><span class="sxs-lookup"><span data-stu-id="15e2e-117">Edit UE-V Settings Location Templates with the UE-V Generator</span></span>


<span data-ttu-id="15e2e-118">UE-V Generator を使用して設定場所テンプレートを編集する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="15e2e-118">How to use the UE-V Generator to edit settings location templates.</span></span>

[<span data-ttu-id="15e2e-119">UE-V Generator を使用して UE-V 設定場所テンプレートを編集する</span><span class="sxs-lookup"><span data-stu-id="15e2e-119">Edit UE-V Settings Location Templates with the UE-V Generator</span></span>](edit-ue-v-settings-location-templates-with-the-ue-v-generator.md)

## <span data-ttu-id="15e2e-120">UE-V Generator を使用して UE-V 設定場所テンプレートを検証する</span><span class="sxs-lookup"><span data-stu-id="15e2e-120">Validate UE-V Settings Location Templates with UE-V Generator</span></span>


<span data-ttu-id="15e2e-121">Ue-v generator を使用して、UE-V Generator の外部で変更された設定の場所テンプレートを検証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="15e2e-121">How to use the UE-V Generator to validate settings location templates modified outside the UE-V Generator.</span></span>

[<span data-ttu-id="15e2e-122">UE-V Generator を使用して UE-V 設定場所テンプレートを検証する</span><span class="sxs-lookup"><span data-stu-id="15e2e-122">Validate UE-V Settings Location Templates with UE-V Generator</span></span>](validate-ue-v-settings-location-templates-with-ue-v-generator.md)

## <a href="" id="bkmk-standardnonstandardsettingslocations"></a><span data-ttu-id="15e2e-123">標準設定と非標準設定の場所</span><span class="sxs-lookup"><span data-stu-id="15e2e-123">Standard and Nonstandard settings locations</span></span>


<span data-ttu-id="15e2e-124">UE-V Generator は、アプリケーションが設定情報を格納するために使用する設定ファイルとレジストリ設定をどのように検索するかを特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="15e2e-124">The UE-V Generator helps you identify where applications look for settings files and registry settings that applications use to store settings information.</span></span> <span data-ttu-id="15e2e-125">UE-V Generator を使用して、標準の場所で設定をキャプチャするために、探索プロセスの一部としてアプリケーションを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="15e2e-125">You can use the UE-V Generator to open the application as part of the discovery process to capture settings in standard locations.</span></span> <span data-ttu-id="15e2e-126">標準的な場所には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="15e2e-126">Standard locations include the following:</span></span>

-   <span data-ttu-id="15e2e-127">**レジストリ設定**– HKEY の下にあるレジストリの場所 \ **_CURRENT \ _USER**</span><span class="sxs-lookup"><span data-stu-id="15e2e-127">**Registry Settings** – Registry locations under **HKEY\_CURRENT\_USER**</span></span>

-   <span data-ttu-id="15e2e-128">**アプリケーション設定ファイル**– \ \**ユーザー*\* \ \ [ユーザー名 \] に保存されているファイル \ \ **AppData**  \\  **ローミング**</span><span class="sxs-lookup"><span data-stu-id="15e2e-128">**Application Settings Files** – Files stored under \\ **Users** \\ \[User name\] \\ **AppData** \\ **Roaming**</span></span>

<span data-ttu-id="15e2e-129">UE-V Generator は、ユーザーのコンピューターまたは環境間で、一般的に保存されているアプリケーションソフトウェアファイルが適切にローミングしない場所を除外します。</span><span class="sxs-lookup"><span data-stu-id="15e2e-129">The UE-V Generator excludes locations which commonly store application software files do not roam well between user computers or environments.</span></span> <span data-ttu-id="15e2e-130">UE-V Generator では、これらの場所は除外されます。</span><span class="sxs-lookup"><span data-stu-id="15e2e-130">The UE-V Generator excludes these locations.</span></span> <span data-ttu-id="15e2e-131">除外する場所は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="15e2e-131">Excluded locations are as follows:</span></span>

-   <span data-ttu-id="15e2e-132">HKEY \ _CURRENT \ _USER のレジストリキーと、ログオンしたユーザーが値を書き込むことができないファイル</span><span class="sxs-lookup"><span data-stu-id="15e2e-132">HKEY\_CURRENT\_USER registry keys and files to which the logged-on user cannot write values</span></span>

-   <span data-ttu-id="15e2e-133">HKEY \ _CURRENT \ _USER のレジストリキーと、Windows オペレーティングシステムのコア機能に関連付けられているファイル</span><span class="sxs-lookup"><span data-stu-id="15e2e-133">HKEY\_CURRENT\_USER registry keys and files that are associated with the core functionality of the Windows operating system</span></span>

-   <span data-ttu-id="15e2e-134">HKEY \ _LOCAL \ _MACHINE ハイブに含まれるすべてのレジストリキー (管理者権限が必要であり、設定には UAC ライセンスが必要な場合があります)</span><span class="sxs-lookup"><span data-stu-id="15e2e-134">All registry keys that are located in the HKEY\_LOCAL\_MACHINE hive (Requires Administrator rights and might require UAC agreement to set)</span></span>

-   <span data-ttu-id="15e2e-135">Program Files ディレクトリに保存されているファイル (管理者権限が必要であるため、UAC 契約を設定する必要がある場合)</span><span class="sxs-lookup"><span data-stu-id="15e2e-135">Files that are located in Program Files directories (Requires Administrator rights and might require UAC agreement to set)</span></span>

-   <span data-ttu-id="15e2e-136">ユーザー (\ \ \ [ユーザー名 \]) にあるファイル (ユーザー名 \ \)</span><span class="sxs-lookup"><span data-stu-id="15e2e-136">Files located in Users \\ \[User name\] \\ AppData \\ LocalLow</span></span>

-   <span data-ttu-id="15e2e-137">% Systemroot% にある Windows オペレーティングシステムファイル (管理者権限が必要であるため、UAC 契約を設定する必要があります)</span><span class="sxs-lookup"><span data-stu-id="15e2e-137">Windows operating system files that are located in %systemroot% (Requires Administrator rights and might require UAC agreement to set)</span></span>

<span data-ttu-id="15e2e-138">アプリケーションの設定をローミングするために、これらの場所に格納されているレジストリキーとファイルが必要な場合は、テンプレートの作成プロセス中に、除外された場所を設定の場所テンプレートに手動で追加することができます。</span><span class="sxs-lookup"><span data-stu-id="15e2e-138">If registry keys and files stored in these locations are required in order to roam application settings, you can manually add the excluded locations to the settings location template during the template creation process.</span></span>

## <span data-ttu-id="15e2e-139">この製品のその他のリソース</span><span class="sxs-lookup"><span data-stu-id="15e2e-139">Other resources for this product</span></span>


[<span data-ttu-id="15e2e-140">UE-V 1.0 の操作</span><span class="sxs-lookup"><span data-stu-id="15e2e-140">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)

[<span data-ttu-id="15e2e-141">UE-V 1.0 の管理</span><span class="sxs-lookup"><span data-stu-id="15e2e-141">Administering UE-V 1.0</span></span>](administering-ue-v-10.md)

 

 





