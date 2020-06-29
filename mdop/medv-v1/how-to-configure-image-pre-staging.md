---
title: イメージの事前ステージングを構成する方法
description: イメージの事前ステージングを構成する方法
author: dansimp
ms.assetid: 92781b5a-208f-45a4-a078-ee90cf9efd9d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 38ddb7a69845aa4dbcb9cbd16b84dedc04438732
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826407"
---
# <span data-ttu-id="3c299-103">イメージの事前ステージングを構成する方法</span><span class="sxs-lookup"><span data-stu-id="3c299-103">How to Configure Image Pre-staging</span></span>


<span data-ttu-id="3c299-104">**注** イメージの事前ステージングは、最初のイメージのダウンロードにのみ役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3c299-104">**Note** Image pre-staging is useful only for the initial image download.</span></span> <span data-ttu-id="3c299-105">イメージの更新には対応していません。</span><span class="sxs-lookup"><span data-stu-id="3c299-105">It is not supported for image update.</span></span>

 

## <span data-ttu-id="3c299-106">イメージの事前ステージングを構成する方法</span><span class="sxs-lookup"><span data-stu-id="3c299-106">How to Configure Image Pre-staging</span></span>


**<span data-ttu-id="3c299-107">イメージの事前ステージングを構成するには</span><span class="sxs-lookup"><span data-stu-id="3c299-107">To configure image pre-staging</span></span>**

1.  <span data-ttu-id="3c299-108">クライアントコンピューターのイメージストアディレクトリで、ステージング用のイメージ用のフォルダーを作成し、そのフォルダーに「 *MED*」の画像という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3c299-108">On the client computer, under the image store directory, create a folder for the pre-staging image, and name it *MED-V Images*.</span></span>

    <span data-ttu-id="3c299-109">**注** このフォルダーは、 *Med-v イメージ*と呼ばれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c299-109">**Note** This folder must be called *MED-V Images*.</span></span>

     

2.  <span data-ttu-id="3c299-110">[MED-V Images] フォルダー内で、サブフォルダーを作成し、 *PrestagedImages*という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3c299-110">Inside the MED-V Images folder, create a subfolder and name it *PrestagedImages*.</span></span>

    <span data-ttu-id="3c299-111">**注** このフォルダーは、 *PrestagedImages*という名前である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c299-111">**Note** This folder must be called *PrestagedImages*.</span></span>

     

3.  <span data-ttu-id="3c299-112">[ *Med-v Images* ] フォルダーにアクセス制御リスト (ACL) セキュリティを適用するには、次の ACL を設定します。</span><span class="sxs-lookup"><span data-stu-id="3c299-112">To apply Access Control Lists (ACL) security to the *MED-V Images* folder, set the following ACL:</span></span>

    **<span data-ttu-id="3c299-113">NT AUTHORITY\\Authenticated ユーザー: (OI) (CI) (特殊アクセス:)</span><span class="sxs-lookup"><span data-stu-id="3c299-113">NT AUTHORITY\\Authenticated Users:(OI)(CI)(special access:)</span></span>**

                                             **READ\_CONTROL**

                                    **SYNCHRONIZE**

                                    **FILE\_GENERIC\_READ**

                                    **FILE\_READ\_DATA**

    **                                 <span data-ttu-id="3c299-114">ファイル \ _APPEND \ _DATA</span><span class="sxs-lookup"><span data-stu-id="3c299-114">FILE\_APPEND\_DATA</span></span>**

                                    **FILE\_READ\_EA**

                                    **FILE\_READ\_ATTRIBUTES**

    **<span data-ttu-id="3c299-115">NT AUTHORITY\\SYSTEM: (OI) (CI) F</span><span class="sxs-lookup"><span data-stu-id="3c299-115">NT AUTHORITY\\SYSTEM:(OI)(CI)F</span></span>**

    **<span data-ttu-id="3c299-116">BUILTIN\\Administrators: (OI) (CI) F</span><span class="sxs-lookup"><span data-stu-id="3c299-116">BUILTIN\\Administrators:(OI)(CI)F</span></span>**

    <span data-ttu-id="3c299-117">**注** [ *Hyper-v Images* ] フォルダーに ACL セキュリティを適用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3c299-117">**Note** It is recommended to apply ACL security to the *MED-V Images* folder.</span></span>

     

4.  <span data-ttu-id="3c299-118">*PrestagedImages*フォルダーに acl セキュリティを適用するには、次の acl を設定します。</span><span class="sxs-lookup"><span data-stu-id="3c299-118">To apply ACL security to the *PrestagedImages* folder, set the following ACL:</span></span>

    **<span data-ttu-id="3c299-119">NT AUTHORITY\\Authenticated ユーザー: (OI) (CI) (特殊アクセス:)</span><span class="sxs-lookup"><span data-stu-id="3c299-119">NT AUTHORITY\\Authenticated Users:(OI)(CI)(special access:)</span></span>**

    **<span data-ttu-id="3c299-120">\ _CONTROL の読み取り</span><span class="sxs-lookup"><span data-stu-id="3c299-120">READ\_CONTROL</span></span>**

    **<span data-ttu-id="3c299-121">処理</span><span class="sxs-lookup"><span data-stu-id="3c299-121">SYNCHRONIZE</span></span>**

    **<span data-ttu-id="3c299-122">ファイル \ _GENERIC \ _READ</span><span class="sxs-lookup"><span data-stu-id="3c299-122">FILE\_GENERIC\_READ</span></span>**

    **<span data-ttu-id="3c299-123">ファイル \ _READ \ _DATA</span><span class="sxs-lookup"><span data-stu-id="3c299-123">FILE\_READ\_DATA</span></span>**

    **<span data-ttu-id="3c299-124">ファイル \ _READ \ _EA</span><span class="sxs-lookup"><span data-stu-id="3c299-124">FILE\_READ\_EA</span></span>**

    **<span data-ttu-id="3c299-125">ファイル \ _READ \ _ATTRIBUTES</span><span class="sxs-lookup"><span data-stu-id="3c299-125">FILE\_READ\_ATTRIBUTES</span></span>**

    **<span data-ttu-id="3c299-126">NT AUTHORITY\\SYSTEM: (OI) (CI) F</span><span class="sxs-lookup"><span data-stu-id="3c299-126">NT AUTHORITY\\SYSTEM:(OI)(CI)F</span></span>**

    **<span data-ttu-id="3c299-127">BUILTIN\\Administrators: (OI) (CI) F</span><span class="sxs-lookup"><span data-stu-id="3c299-127">BUILTIN\\Administrators:(OI)(CI)F</span></span>**

    <span data-ttu-id="3c299-128">**注** ACL セキュリティを*PrestagedImages*フォルダーに適用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3c299-128">**Note** It is recommended to apply ACL security to the *PrestagedImages* folder.</span></span>

     

5.  <span data-ttu-id="3c299-129">画像ファイル (CKM ファイルとインデックスファイル) を*PrestagedImages*フォルダーにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="3c299-129">Push the image files (CKM and INDEX files) to the *PrestagedImages* folder.</span></span>

    <span data-ttu-id="3c299-130">**注** イメージファイルが事前ステージフォルダーにプッシュされたら、データ整合性チェックを実行して、ファイルを読み取り専用としてマークすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3c299-130">**Note** After the image files have been pushed to the pre-stage folder, it is recommended to run a data integrity check and to mark the files as read-only.</span></span>

     

6.  <span data-ttu-id="3c299-131">MED-V クライアントインストールに次のパラメーターを追加します。 *Client.MSI VMSFOLDER = "C:\\MED-V Images"*。</span><span class="sxs-lookup"><span data-stu-id="3c299-131">Include the following parameter in the MED-V client installation: *Client.MSI VMSFOLDER=”C:\\MED-V Images”*.</span></span>

## <span data-ttu-id="3c299-132">プレステージの場所を更新する方法</span><span class="sxs-lookup"><span data-stu-id="3c299-132">How to Update the Pre-stage Location</span></span>


**<span data-ttu-id="3c299-133">プレステージの位置情報を更新するには</span><span class="sxs-lookup"><span data-stu-id="3c299-133">To update the pre-stage location</span></span>**

1.  <span data-ttu-id="3c299-134">レジストリキー *PrestagedImagesPath*は、既定の画像の場所をポイントします。</span><span class="sxs-lookup"><span data-stu-id="3c299-134">The registry key, *PrestagedImagesPath*, points to the default image location.</span></span> <span data-ttu-id="3c299-135">次のディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="3c299-135">It is located in the following directory:</span></span>

    -   <span data-ttu-id="3c299-136">X86 での場合-</span><span class="sxs-lookup"><span data-stu-id="3c299-136">On an x86 -</span></span> `KEY_LOCAL_MACHINE\SOFTWARE\Kidaro`

    -   <span data-ttu-id="3c299-137">X64-</span><span class="sxs-lookup"><span data-stu-id="3c299-137">On an x64 -</span></span> `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432node`

2.  <span data-ttu-id="3c299-138">画像が別の場所にある場合は、パスを変更します。</span><span class="sxs-lookup"><span data-stu-id="3c299-138">If the image is in a different location, change the path.</span></span>

 

 





