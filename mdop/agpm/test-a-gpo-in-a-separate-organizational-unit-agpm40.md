---
title: 別の組織単位で GPO をテストする
description: 別の組織単位で GPO をテストする
author: dansimp
ms.assetid: 9a9e6d22-74e6-41d8-ac2f-12a1b76ad5a0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 509721fdd775c8669399549f6dcc29cb9ebaea2f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818257"
---
# <span data-ttu-id="f3969-103">別の組織単位で GPO をテストする</span><span class="sxs-lookup"><span data-stu-id="f3969-103">Test a GPO in a Separate Organizational Unit</span></span>


<span data-ttu-id="f3969-104">テスト用の組織単位 (OU) を使って、運用環境に展開する前に同じドメイン内のグループポリシーオブジェクト (Gpo) をテストする場合は、テスト OU へのアクセスに必要なアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3969-104">If you use a testing organizational unit (OU) to test Group Policy Objects (GPOs) within the same domain before deployment to the production environment, you must have the necessary permissions to access the test OU.</span></span> <span data-ttu-id="f3969-105">Test OU の使用は任意です。</span><span class="sxs-lookup"><span data-stu-id="f3969-105">Using a test OU is optional.</span></span>

**<span data-ttu-id="f3969-106">テスト OU を使用するには</span><span class="sxs-lookup"><span data-stu-id="f3969-106">To use a test OU</span></span>**

1.  <span data-ttu-id="f3969-107">編集用にチェックアウトされた GPO はありますが、**グループポリシー管理コンソール**で、gpo を管理するフォレストとドメインの**グループポリシーオブジェクト**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f3969-107">Although you have the GPO checked out for editing, in the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you are managing GPOs.</span></span>

2.  <span data-ttu-id="f3969-108">テストする GPO のチェックアウトコピーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f3969-108">Click the checked out copy of the GPO to be tested.</span></span> <span data-ttu-id="f3969-109">名前の先頭には**\ [AGPM \]** と表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3969-109">The name will be preceded by **\[AGPM\]**.</span></span> <span data-ttu-id="f3969-110">表示されていない場合は、[**アクション**]、[**更新**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f3969-110">(If it is not listed, click **Action**, then **Refresh**.</span></span> <span data-ttu-id="f3969-111">名前はアルファベット順に並べ替えることができ、 **\ [AGPM \]** gpo は通常、一覧の一番上に表示されます。)</span><span class="sxs-lookup"><span data-stu-id="f3969-111">Sort the names alphabetically, and **\[AGPM\]** GPOs will typically appear at the top of the list.)</span></span>

3.  <span data-ttu-id="f3969-112">GPO を test OU にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="f3969-112">Drag the GPO to the test OU.</span></span>

4.  <span data-ttu-id="f3969-113">テスト OU に GPO へのリンクを作成するかどうかを確認するダイアログボックスで [ **OK** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f3969-113">Click **OK** in the dialog box that asks whether to create a link to the GPO in the test OU.</span></span>

### <span data-ttu-id="f3969-114">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="f3969-114">Additional considerations</span></span>

-   <span data-ttu-id="f3969-115">テストが完了すると、GPO をチェックインすると、チェックアウトした GPO のコピーへのリンクが自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="f3969-115">When testing is complete, checking in the GPO automatically deletes the link to the checked-out copy of the GPO.</span></span>

### <span data-ttu-id="f3969-116">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="f3969-116">Additional references</span></span>

-   [<span data-ttu-id="f3969-117">テスト環境の使用</span><span class="sxs-lookup"><span data-stu-id="f3969-117">Using a Test Environment</span></span>](using-a-test-environment.md)

 

 





