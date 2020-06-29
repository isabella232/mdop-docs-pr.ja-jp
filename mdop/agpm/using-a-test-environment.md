---
title: テスト環境の使用
description: テスト環境の使用
author: dansimp
ms.assetid: fc5fcc7c-1ac8-483a-a6bd-2279ae2ee3fb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fc3ad91747c755efe0576cc62473848094b72ed1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818174"
---
# <span data-ttu-id="f799b-103">テスト環境の使用</span><span class="sxs-lookup"><span data-stu-id="f799b-103">Using a Test Environment</span></span>


<span data-ttu-id="f799b-104">グループポリシーオブジェクト (GPO) を運用環境に展開する前に、ラボ環境で GPO をテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f799b-104">Before you request that a Group Policy Object (GPO) be deployed to the production environment, you should test the GPO in a lab environment.</span></span> <span data-ttu-id="f799b-105">テストフォレストのドメインで GPO を開発する場合、GPO をファイルにエクスポートし、そのファイルを運用フォレストのドメインにインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="f799b-105">If you develop the GPO in a domain in a test forest, you can export the GPO to a file and import the file to a domain in the production forest.</span></span> <span data-ttu-id="f799b-106">次に、テストコンピューターとユーザーを含む組織単位 (OU) に GPO をリンクして、GPO をテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="f799b-106">You can then test the GPO by linking it to an organizational unit (OU) that contains test computers and users.</span></span>

-   [<span data-ttu-id="f799b-107">GPO をファイルにエクスポートする</span><span class="sxs-lookup"><span data-stu-id="f799b-107">Export a GPO to a File</span></span>](export-a-gpo-to-a-file.md)

-   [<span data-ttu-id="f799b-108">ファイルから GPO をインポートする</span><span class="sxs-lookup"><span data-stu-id="f799b-108">Import a GPO from a File</span></span>](import-a-gpo-from-a-file-ed.md)

-   [<span data-ttu-id="f799b-109">別の組織単位で GPO をテストする</span><span class="sxs-lookup"><span data-stu-id="f799b-109">Test a GPO in a Separate Organizational Unit</span></span>](test-a-gpo-in-a-separate-organizational-unit-agpm40.md)

<span data-ttu-id="f799b-110">**注** また、ドメインの運用環境から GPO をインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f799b-110">**Note** You can also import a GPO from the production environment of the domain.</span></span> <span data-ttu-id="f799b-111">詳細については、「[運用環境から GPO をインポートする](import-a-gpo-from-production-agpm40-ed.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f799b-111">For more information, see [Import a GPO from Production](import-a-gpo-from-production-agpm40-ed.md).</span></span>

 

 

 





