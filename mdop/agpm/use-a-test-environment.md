---
title: テスト環境を使用する
description: テスト環境を使用する
author: dansimp
ms.assetid: b8d7b3ee-030a-4b5b-8223-4a3276fd47a7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2299fb6eaf7c75f6841056f67a05fe025ea19bb7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818234"
---
# <span data-ttu-id="2ec83-103">テスト環境を使用する</span><span class="sxs-lookup"><span data-stu-id="2ec83-103">Use a Test Environment</span></span>


<span data-ttu-id="2ec83-104">テスト用の組織単位 (OU) を使用して、運用環境に展開する前にグループポリシーオブジェクト (Gpo) をテストする場合、テスト OU へのアクセスに必要なアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ec83-104">If you use a testing organizational unit (OU) to test Group Policy objects (GPOs) before deployment to the production environment, you must have the necessary permissions to access the test OU.</span></span> <span data-ttu-id="2ec83-105">Test OU の使用はオプションです。</span><span class="sxs-lookup"><span data-stu-id="2ec83-105">The use of a test OU is optional.</span></span>

**<span data-ttu-id="2ec83-106">テスト OU を使用するには</span><span class="sxs-lookup"><span data-stu-id="2ec83-106">To use a test OU</span></span>**

1.  <span data-ttu-id="2ec83-107">編集用にチェックアウトされている GPO があるときに、**グループポリシー管理コンソール**で、gpo を管理するフォレストとドメインの**グループポリシーオブジェクト**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ec83-107">While you have the GPO checked out for editing, in the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you are managing GPOs.</span></span>

2.  <span data-ttu-id="2ec83-108">テストする GPO のチェックアウトコピーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ec83-108">Click the checked out copy of the GPO to be tested.</span></span> <span data-ttu-id="2ec83-109">名前の前に**\ [AGPM \]** と表示されます。</span><span class="sxs-lookup"><span data-stu-id="2ec83-109">The name will be preceded with **\[AGPM\]**.</span></span> <span data-ttu-id="2ec83-110">表示されていない場合は、[**アクション**]、[**更新**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ec83-110">(If it is not listed, click **Action**, then **Refresh**.</span></span> <span data-ttu-id="2ec83-111">名前はアルファベット順に並べ替えることができ、 **\ [AGPM \]** gpo は通常、一覧の一番上に表示されます。)</span><span class="sxs-lookup"><span data-stu-id="2ec83-111">Sort the names alphabetically, and **\[AGPM\]** GPOs will typically appear at the top of the list.)</span></span>

3.  <span data-ttu-id="2ec83-112">GPO を [test OU] にドラッグアンドドロップします。</span><span class="sxs-lookup"><span data-stu-id="2ec83-112">Drag and drop the GPO to the test OU.</span></span>

4.  <span data-ttu-id="2ec83-113">ダイアログボックスで [ **OK** ] をクリックし、テスト OU に GPO へのリンクを作成するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="2ec83-113">Click **OK** in the dialog box asking whether to create a link to the GPO in the test OU.</span></span>

### <span data-ttu-id="2ec83-114">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="2ec83-114">Additional considerations</span></span>

-   <span data-ttu-id="2ec83-115">テストが完了すると、GPO をチェックインすると、チェックアウトした GPO のコピーへのリンクが自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="2ec83-115">When testing is complete, checking in the GPO automatically deletes the link to the checked-out copy of the GPO.</span></span>

### <span data-ttu-id="2ec83-116">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="2ec83-116">Additional references</span></span>

-   [<span data-ttu-id="2ec83-117">GPO の編集</span><span class="sxs-lookup"><span data-stu-id="2ec83-117">Editing a GPO</span></span>](editing-a-gpo.md)

 

 





