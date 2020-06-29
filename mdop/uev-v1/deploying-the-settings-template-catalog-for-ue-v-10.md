---
title: UE-V 1.0 の設定テンプレート カタログの展開
description: UE-V 1.0 の設定テンプレート カタログの展開
author: dansimp
ms.assetid: 0e6ab5ef-8eeb-40b4-be7b-a841bd83be96
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f342daa958607a077fa5eb2a27ec705c8d99e67f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826634"
---
# <span data-ttu-id="1e665-103">UE-V 1.0 の設定テンプレート カタログの展開</span><span class="sxs-lookup"><span data-stu-id="1e665-103">Deploying the Settings Template Catalog for UE-V 1.0</span></span>


<span data-ttu-id="1e665-104">カスタム設定の場所テンプレートは、Microsoft User Experience Virtualization (UE-V) コンピューター上のフォルダーパスまたはサーバーメッセージブロック (SMB) ネットワーク共有上のフォルダーパスに保存できます。</span><span class="sxs-lookup"><span data-stu-id="1e665-104">Custom settings location templates can be stored on a folder path on Microsoft User Experience Virtualization (UE-V) computers or on a Server Message Block (SMB) network share.</span></span> <span data-ttu-id="1e665-105">コンピューター上のスケジュールされたタスクが、この場所から新しいまたは更新されたテンプレートを確認します。</span><span class="sxs-lookup"><span data-stu-id="1e665-105">A scheduled task on the computer checks for new or updated templates from this location.</span></span> <span data-ttu-id="1e665-106">タスクでは、この場所が毎日1回チェックされ、このフォルダー内のテンプレートに基づいて同期動作が更新されます。</span><span class="sxs-lookup"><span data-stu-id="1e665-106">The task checks this location once each day and updates its synchronization behavior based on the templates in this folder.</span></span> <span data-ttu-id="1e665-107">前回のチェック後にこのフォルダーで追加または更新されるテンプレートは、UE-V agent によって登録されます。</span><span class="sxs-lookup"><span data-stu-id="1e665-107">Templates that are added or updated in this folder since the last check are registered by the UE-V agent.</span></span> <span data-ttu-id="1e665-108">UE-V agent deregisters テンプレートはこのフォルダーから削除されました。</span><span class="sxs-lookup"><span data-stu-id="1e665-108">The UE-V agent deregisters templates that were removed from this folder.</span></span> <span data-ttu-id="1e665-109">スケジュールされたタスクはシステムとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="1e665-109">The scheduled task runs as SYSTEM.</span></span> <span data-ttu-id="1e665-110">少なくとも、ネットワーク共有は、ドメインコンピューターグループに対するアクセス許可を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e665-110">At a minimum, the network share must grant permissions for the Domain Computers group.</span></span> <span data-ttu-id="1e665-111">さらに、保存されたテンプレートを管理する管理者にネットワーク共有フォルダーへのアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="1e665-111">In addition, grant access permissions for the network share folder to administrators who will manage the stored templates.</span></span> <span data-ttu-id="1e665-112">カスタム設定の場所テンプレートの詳細については、「 [ue-v 1.0 のカスタムテンプレートの展開を計画](planning-for-custom-template-deployment-for-ue-v-10.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e665-112">For more information about custom setting location templates, see [Planning for Custom Template Deployment for UE-V 1.0](planning-for-custom-template-deployment-for-ue-v-10.md).</span></span>

**<span data-ttu-id="1e665-113">UE-V の設定テンプレートカタログを構成するには</span><span class="sxs-lookup"><span data-stu-id="1e665-113">To configure the settings template catalog for UE-V</span></span>**

1.  <span data-ttu-id="1e665-114">UE-V 設定テンプレートカタログを保存するコンピューター上に新しいフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="1e665-114">Create a new folder on the computer that will store the UE-V settings template catalog.</span></span>

2.  <span data-ttu-id="1e665-115">設定テンプレートカタログフォルダーに対して、次の共有レベル (SMB) のアクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="1e665-115">Set the following share-level (SMB) permissions for the settings template catalog folder.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong><span data-ttu-id="1e665-116">ユーザーアカウント</span><span class="sxs-lookup"><span data-stu-id="1e665-116">User account</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="1e665-117">権限の推奨</span><span class="sxs-lookup"><span data-stu-id="1e665-117">Recommend permissions</span></span></strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1e665-118">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="1e665-118">Everyone</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1e665-119">権限なし</span><span class="sxs-lookup"><span data-stu-id="1e665-119">No Permissions</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="1e665-120">ドメインコンピューター</span><span class="sxs-lookup"><span data-stu-id="1e665-120">Domain Computers</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1e665-121">アクセス許可レベルの読み取り</span><span class="sxs-lookup"><span data-stu-id="1e665-121">Read Permission Levels</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1e665-122">管理者</span><span class="sxs-lookup"><span data-stu-id="1e665-122">Administrators</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1e665-123">読み取り/書き込みアクセス許可レベル</span><span class="sxs-lookup"><span data-stu-id="1e665-123">Read/Write Permission Levels</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

3.  <span data-ttu-id="1e665-124">設定テンプレートカタログフォルダーに対して、次の NTFS アクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="1e665-124">Set the following NTFS permissions for the settings template catalog folder.</span></span>

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="1e665-125">ユーザーアカウント</span><span class="sxs-lookup"><span data-stu-id="1e665-125">User Account</span></span></th>
    <th align="left"><span data-ttu-id="1e665-126">推奨されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="1e665-126">Recommended Permissions</span></span></th>
    <th align="left"><span data-ttu-id="1e665-127">適用対象</span><span class="sxs-lookup"><span data-stu-id="1e665-127">Apply To</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1e665-128">作成者/所有者</span><span class="sxs-lookup"><span data-stu-id="1e665-128">Creator/Owner</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1e665-129">フルコントロール</span><span class="sxs-lookup"><span data-stu-id="1e665-129">Full Control</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1e665-130">このフォルダー、サブフォルダー、ファイル</span><span class="sxs-lookup"><span data-stu-id="1e665-130">This Folder, Subfolders and Files</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="1e665-131">ドメインコンピューター</span><span class="sxs-lookup"><span data-stu-id="1e665-131">Domain Computers</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1e665-132">フォルダーの内容の一覧表示と読み取り</span><span class="sxs-lookup"><span data-stu-id="1e665-132">List Folder Contents and Read</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1e665-133">このフォルダー、サブフォルダー、ファイル</span><span class="sxs-lookup"><span data-stu-id="1e665-133">This Folder, Subfolders and Files</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1e665-134">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="1e665-134">Everyone</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1e665-135">権限なし</span><span class="sxs-lookup"><span data-stu-id="1e665-135">No Permissions</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1e665-136">権限なし</span><span class="sxs-lookup"><span data-stu-id="1e665-136">No Permissions</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="1e665-137">管理者</span><span class="sxs-lookup"><span data-stu-id="1e665-137">Administrators</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1e665-138">フルコントロール</span><span class="sxs-lookup"><span data-stu-id="1e665-138">Full Control</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1e665-139">このフォルダー、サブフォルダー、ファイル</span><span class="sxs-lookup"><span data-stu-id="1e665-139">This Folder, Subfolders and Files</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

4.  <span data-ttu-id="1e665-140">[ **OK** ] をクリックしてダイアログボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="1e665-140">Click **OK** to close the dialog boxes.</span></span>

## <span data-ttu-id="1e665-141">関連トピック</span><span class="sxs-lookup"><span data-stu-id="1e665-141">Related topics</span></span>


[<span data-ttu-id="1e665-142">UE-V 1.0 の展開</span><span class="sxs-lookup"><span data-stu-id="1e665-142">Deploying UE-V 1.0</span></span>](deploying-ue-v-10.md)

[<span data-ttu-id="1e665-143">UE-V 1.0 のカスタム テンプレートの展開計画</span><span class="sxs-lookup"><span data-stu-id="1e665-143">Planning for Custom Template Deployment for UE-V 1.0</span></span>](planning-for-custom-template-deployment-for-ue-v-10.md)

 

 





