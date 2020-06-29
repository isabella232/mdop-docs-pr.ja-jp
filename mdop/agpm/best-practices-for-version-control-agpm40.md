---
title: バージョン管理のベスト プラクティス
description: バージョン管理のベスト プラクティス
author: dansimp
ms.assetid: 4a2a1ac7-67f3-4ba3-ab07-860d33da0efe
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d560913c4e0f49a2015f620564a9038677d65144
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819194"
---
# <span data-ttu-id="09171-103">バージョン管理のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="09171-103">Best Practices for Version Control</span></span>


<span data-ttu-id="09171-104">Microsoft Advanced グループポリシー管理 (AGPM) では、Microsoft Visual SourceSafe®がソースコードのバージョン管理を提供しているように、グループポリシーオブジェクト (Gpo) のバージョン管理を提供します。</span><span class="sxs-lookup"><span data-stu-id="09171-104">Microsoft Advanced Group Policy Management (AGPM) provides version control for Group Policy Objects (GPOs) much like Microsoft Visual SourceSafe® provides version control for source code.</span></span> <span data-ttu-id="09171-105">開発者は、Visual SourceSafe を使って、各ソースファイルの複数のバージョンを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="09171-105">Developers can use Visual SourceSafe to manage multiple versions of each source file.</span></span> <span data-ttu-id="09171-106">グループポリシー管理者は、AGPM を使って Gpo に対しても同じ操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="09171-106">Group Policy administrators can use AGPM to do the same for GPOs.</span></span> <span data-ttu-id="09171-107">AGPM を使用する場合、グループポリシー管理者は、すべてのバージョン管理システムに適用されるベストプラクティスを認識している必要があります。</span><span class="sxs-lookup"><span data-stu-id="09171-107">When you use AGPM, Group Policy administrators should be aware of best practices that apply to any version control system:</span></span>

-   <span data-ttu-id="09171-108">**日付と時刻:** AGPM は、GPO の各バージョンを日付と時刻でスタンプします。</span><span class="sxs-lookup"><span data-stu-id="09171-108">**Date and time:** AGPM stamps each version of a GPO with the date and time.</span></span> <span data-ttu-id="09171-109">特に複数のコンピューターで Gpo を編集する場合に、履歴が正確であることを確認するには、各コンピューターの時計が1つの権限のあるタイムソースに同期されるようにします。</span><span class="sxs-lookup"><span data-stu-id="09171-109">To ensure that history is accurate, especially when you edit GPOs on more than one computer, make sure that each computer synchronizes its clock with one authoritative time source.</span></span>

-   <span data-ttu-id="09171-110">**Gpo の編集が完了したら、次のことを確認します。** 多くの場合、編集者は Gpo をチェックアウトし、忘れてしまったことを忘れないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="09171-110">**Check in GPOs when you are finished editing them:** It is common for Editors to check out GPOs and forget to check them back into the archive.</span></span> <span data-ttu-id="09171-111">ただし、他のグループポリシー管理者が GPO を変更できないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="09171-111">However, this can prevent other Group Policy administrators from changing the GPO.</span></span> <span data-ttu-id="09171-112">編集を完了したら、常に Gpo を AGPM にチェックインします。</span><span class="sxs-lookup"><span data-stu-id="09171-112">Always check GPOs back in to AGPM immediately when you are finished editing.</span></span>

-   <span data-ttu-id="09171-113">**頻繁に変更を保存する:** GPO を編集するときに、変更を頻繁に保存します。</span><span class="sxs-lookup"><span data-stu-id="09171-113">**Save changes frequently:** When you edit a GPO, save changes frequently.</span></span> <span data-ttu-id="09171-114">多くのエディターは、GPO をチェックアウトし、多くの変更を加えた後、GPO をアーカイブにチェックインします。</span><span class="sxs-lookup"><span data-stu-id="09171-114">Most Editors check out a GPO, make many changes, and then check the GPO into the archive.</span></span> <span data-ttu-id="09171-115">代わりに、GPO を定期的にアーカイブにチェックインしてからもう一度確認します。</span><span class="sxs-lookup"><span data-stu-id="09171-115">Instead, check the GPO into the archive regularly, and then check it out again.</span></span> <span data-ttu-id="09171-116">関連する変更のグループを作成した後で、すべての設定を変更するか (推奨しません)、または GPO をチェックインした後で、GPO を簡単にチェックインすることができます。</span><span class="sxs-lookup"><span data-stu-id="09171-116">The detail can be as small as checking in the GPO after you change every setting (not recommended) or checking in the GPO after you make groups of related changes.</span></span> <span data-ttu-id="09171-117">結果として、問題のトラブルシューティングに役立つように、各 GPO についてより明確に説明された履歴が得られます。</span><span class="sxs-lookup"><span data-stu-id="09171-117">The result is a better-documented history for each GPO that can help when troubleshooting issues.</span></span>

-   <span data-ttu-id="09171-118">**Gpo を頻繁に展開する:** まだ展開されていない新しい Gpo または編集済みの Gpo は、アーカイブ内の大きな数値で累積できないようにします。</span><span class="sxs-lookup"><span data-stu-id="09171-118">**Deploy GPOs frequently:** Do not let new and edited GPOs that have not yet been deployed accumulate in large numbers in the archive.</span></span> <span data-ttu-id="09171-119">代わりに、新しい Gpo と編集済みの Gpo をできるだけ早く展開して、実稼働環境への影響を最小限にします。</span><span class="sxs-lookup"><span data-stu-id="09171-119">Instead, deploy new and edited GPOs as soon as possible so that they have a minimum effect on the production environment.</span></span> <span data-ttu-id="09171-120">一度に多くの新規および編集された Gpo を展開すると、実稼働環境が危険にさらされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="09171-120">Deploying many new and edited GPOs at one time can jeopardize the production environment.</span></span>

-   <span data-ttu-id="09171-121">**Gpo をチェックインするときの変更の目的を文書化します。** どのレビュー担当者も、GPO のバージョンを比較して、2つの間の特定の変更を確認できます。</span><span class="sxs-lookup"><span data-stu-id="09171-121">**Document the purpose of changes when you check in GPOs:** Any Reviewer can compare versions of a GPO to see specific changes between the two.</span></span> <span data-ttu-id="09171-122">特定の変更を文書化すると、値は追加されません。</span><span class="sxs-lookup"><span data-stu-id="09171-122">Documenting those specific changes adds no value.</span></span> <span data-ttu-id="09171-123">代わりに、変更の意図と目的を文書化して、校閲者が表示できる差異レポートの表示方法を文書化する代わりに説明します。</span><span class="sxs-lookup"><span data-stu-id="09171-123">Instead, document the intent and purpose of a change instead of documenting what Reviewers can see by viewing difference reports.</span></span> <span data-ttu-id="09171-124">バージョンのコメントは、比較レポートに値を追加して、エディターが GPO を変更した理由をレビュー担当者が理解できるようにします。</span><span class="sxs-lookup"><span data-stu-id="09171-124">Version comments should add value to the comparison report and help a Reviewer understand why the Editor changed the GPO.</span></span>

-   <span data-ttu-id="09171-125">**テスト環境で gpo をテストします。** テストしないで、Gpo を運用環境に展開するのは危険です。</span><span class="sxs-lookup"><span data-stu-id="09171-125">**Test GPOs in a test environment:** Deploying GPOs to the production environment without testing them is risky.</span></span> <span data-ttu-id="09171-126">代わりに、テストフォレストのドメインで Gpo をテストして、Gpo をファイルにエクスポートし、実稼働フォレストのドメインにインポートします。</span><span class="sxs-lookup"><span data-stu-id="09171-126">Instead, test your GPOs in a domain in a test forest, and then export the GPOs to files and import them to a domain in a production forest.</span></span> <span data-ttu-id="09171-127">また、テストコンピューターとユーザーを含む組織単位に Gpo をリンクすることもできます。</span><span class="sxs-lookup"><span data-stu-id="09171-127">Also, you can link GPOs to an organizational unit that contains test computers and users.</span></span> <span data-ttu-id="09171-128">各 GPO がテスト環境で正しく動作することを確認してから、その Gpo を運用環境に展開します。</span><span class="sxs-lookup"><span data-stu-id="09171-128">Verify that each GPO functions correctly in the test environment and then deploy the GPOs to the production environment.</span></span>

### <span data-ttu-id="09171-129">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="09171-129">Additional references</span></span>

-   [<span data-ttu-id="09171-130">Advanced Group Policy Management 4.0</span><span class="sxs-lookup"><span data-stu-id="09171-130">Advanced Group Policy Management 4.0</span></span>](advanced-group-policy-management-40.md)

 

 





