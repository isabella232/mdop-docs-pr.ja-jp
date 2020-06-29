---
title: 保存される GPO のバージョンを制限する
description: 保存される GPO のバージョンを制限する
author: dansimp
ms.assetid: da14edc5-0c36-4c54-b122-861c86b99eb1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 20a3ae60cc330c27cbd19e943ba7f071d4ec60b1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820624"
---
# <span data-ttu-id="abcab-103">保存される GPO のバージョンを制限する</span><span class="sxs-lookup"><span data-stu-id="abcab-103">Limit the GPO Versions Stored</span></span>


<span data-ttu-id="abcab-104">既定では、コントロールされたすべてのグループポリシーオブジェクト (GPO) のすべてのバージョンが、AGPM サーバー上のアーカイブに保持されます。</span><span class="sxs-lookup"><span data-stu-id="abcab-104">By default, all versions of every controlled Group Policy Object (GPO) are retained in the archive on the AGPM Server.</span></span> <span data-ttu-id="abcab-105">ただし、その制限を超えた場合は、各 GPO に保持するバージョンの数を制限し、以前のバージョンを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="abcab-105">However, you can limit the number of versions retained for each GPO and delete older versions when that limit is exceeded.</span></span> <span data-ttu-id="abcab-106">GPO のバージョンが削除されても、バージョンのレコードは GPO の履歴に残りますが、GPO のバージョン自体はアーカイブから削除されます。</span><span class="sxs-lookup"><span data-stu-id="abcab-106">When GPO versions are deleted, a record of the version remains in the history of the GPO, but the GPO version itself is deleted from the archive.</span></span>

<span data-ttu-id="abcab-107">この手順を完了するには、AGPM 管理者 (フルコントロール) の役割または高度なグループポリシー管理 (AGPM) に必要なアクセス許可を持つユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="abcab-107">A user account with the AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="abcab-108">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abcab-108">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="abcab-109">保存する GPO バージョンの数を制限するには</span><span class="sxs-lookup"><span data-stu-id="abcab-109">To limit the number of GPO versions stored</span></span>**

1.  <span data-ttu-id="abcab-110">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="abcab-110">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="abcab-111">詳細ウィンドウで、[ **AGPM サーバー** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="abcab-111">In the details pane, click the **AGPM Server** tab.</span></span>

3.  <span data-ttu-id="abcab-112">[**古いバージョンの各 gpo をアーカイブから削除**する] チェックボックスをオンにして、現在のバージョンを除く、各 gpo に対して保存する gpo のバージョンの最大数を入力します。</span><span class="sxs-lookup"><span data-stu-id="abcab-112">Select the **Delete old versions of each GPO from the archive** check box, and type the maximum number of GPO versions to store for each GPO, not including the current version.</span></span> <span data-ttu-id="abcab-113">現在のバージョンのみを保持するには、「0」を入力します。</span><span class="sxs-lookup"><span data-stu-id="abcab-113">To retain only the current version, enter 0.</span></span> <span data-ttu-id="abcab-114">最大値は999より大きくする必要があります。</span><span class="sxs-lookup"><span data-stu-id="abcab-114">The maximum must be no greater than 999.</span></span>

    <span data-ttu-id="abcab-115">**重要** [**履歴**] ウィンドウの [**一意のバージョン**] タブに表示される GPO バージョンのみが、制限をカウントします。</span><span class="sxs-lookup"><span data-stu-id="abcab-115">**Important** Only GPO versions displayed on the **Unique Versions** tab of the **History** window count toward the limit.</span></span>

     

4.  <span data-ttu-id="abcab-116">[**適用**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="abcab-116">Click the **Apply** button.</span></span>

### <span data-ttu-id="abcab-117">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="abcab-117">Additional considerations</span></span>

-   <span data-ttu-id="abcab-118">既定では、この手順を実行するには AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="abcab-118">By default, you must be an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="abcab-119">具体的には、ドメインの [**リストの内容**] および [**変更オプション**] のアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="abcab-119">Specifically, you must have **List Contents** and **Modify Options** permissions for the domain.</span></span>

-   <span data-ttu-id="abcab-120">GPO のバージョンを削除できないように、履歴にマークすることで、その GPO のバージョンが削除されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="abcab-120">You can prevent a GPO version from being deleted by marking it in the history as ineligible for deletion.</span></span> <span data-ttu-id="abcab-121">そのためには、GPO の履歴でバージョンを右クリックし、[**削除しない**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="abcab-121">To do so, right-click the version in the history of the GPO and click **Do Not Delete**.</span></span>

### <span data-ttu-id="abcab-122">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="abcab-122">Additional references</span></span>

-   [<span data-ttu-id="abcab-123">アーカイブの管理</span><span class="sxs-lookup"><span data-stu-id="abcab-123">Managing the Archive</span></span>](managing-the-archive.md)

 

 





