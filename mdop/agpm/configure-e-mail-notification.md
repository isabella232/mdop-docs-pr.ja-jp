---
title: 電子メール通知を構成する
description: 電子メール通知を構成する
author: dansimp
ms.assetid: 6e152de0-4376-4963-8d1a-3e7f5866d30f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 46e8d00c2446a0185de30bbd1f39a7e3eaf90080
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818977"
---
# <span data-ttu-id="fa324-103">電子メール通知を構成する</span><span class="sxs-lookup"><span data-stu-id="fa324-103">Configure E-Mail Notification</span></span>


<span data-ttu-id="fa324-104">編集者またはレビュー担当者がグループポリシーオブジェクト (GPO) を作成、展開、または削除しようとすると、指定された電子メールアドレスにこの操作の要求が送信されます。これにより、承認者は要求を評価して、それを実装または拒否することができます。</span><span class="sxs-lookup"><span data-stu-id="fa324-104">When an Editor or a Reviewer attempts to create, deploy, or delete a Group Policy object (GPO), a request for this action is sent to a designated e-mail address or addresses so that an Approver can evaluate the request and implement or deny it.</span></span> <span data-ttu-id="fa324-105">通知の送信先となる電子メールアドレス、および通知の送信先となるエイリアスを決定します。</span><span class="sxs-lookup"><span data-stu-id="fa324-105">You determine the e-mail address or addresses to which notifications are sent, as well as the alias from which notifications are sent.</span></span>

<span data-ttu-id="fa324-106">この手順を完了するには、AGPM 管理者 (フルコントロール) の役割または高度なグループポリシー管理の必要なアクセス許可を持つユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="fa324-106">A user account with the AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="fa324-107">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa324-107">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="fa324-108">AGPM の電子メール通知を構成するには</span><span class="sxs-lookup"><span data-stu-id="fa324-108">To configure e-mail notification for AGPM</span></span>**

1.  <span data-ttu-id="fa324-109">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fa324-109">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="fa324-110">詳細ウィンドウで、[ **Domain Delegation** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="fa324-110">In the details pane, click the **Domain Delegation** tab.</span></span>

3.  <span data-ttu-id="fa324-111">[**差出人**] フィールドに、通知を送信するための AGPM の電子メールエイリアスを入力します。</span><span class="sxs-lookup"><span data-stu-id="fa324-111">In the **From** field, type the e-mail alias for AGPM from which notifications should be sent.</span></span>

4.  <span data-ttu-id="fa324-112">[**宛先**] フィールドに、承認の依頼を受け取る承認者の電子メールアドレスのコンマ区切りリストを入力します。</span><span class="sxs-lookup"><span data-stu-id="fa324-112">In the **To** field, type a comma-delimited list of e-mail addresses of Approvers who should receive requests for approval.</span></span>

5.  <span data-ttu-id="fa324-113">[ **Smtp server** ] フィールドに、有効な smtp メールサーバーを入力します。</span><span class="sxs-lookup"><span data-stu-id="fa324-113">In the **SMTP server** field, type a valid SMTP mail server.</span></span>

6.  <span data-ttu-id="fa324-114">[**ユーザー名**] フィールドと [**パスワード**] フィールドに、SMTP サービスへのアクセス権を持つユーザーの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="fa324-114">In the **User name** and **Password** fields, type the credentials of a user with access to the SMTP service.</span></span>

7.  <span data-ttu-id="fa324-115">**[適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fa324-115">Click **Apply**.</span></span>

### <span data-ttu-id="fa324-116">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="fa324-116">Additional considerations</span></span>

-   <span data-ttu-id="fa324-117">既定では、この手順を実行するには AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa324-117">By default, you must be an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="fa324-118">具体的には、ドメインの [**リストの内容**] および [**変更オプション**] のアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa324-118">Specifically, you must have **List Contents** and **Modify Options** permissions for the domain.</span></span>

-   <span data-ttu-id="fa324-119">AGPM のメール通知は、ドメインレベルの設定です。</span><span class="sxs-lookup"><span data-stu-id="fa324-119">E-mail notification for AGPM is a domain-level setting.</span></span> <span data-ttu-id="fa324-120">各ドメインの [ **Domain Delegation** ] タブで、さまざまな承認者の電子メールアドレスまたは AGPM 電子メールエイリアスを指定するか、または環境全体で同じメールアドレスを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="fa324-120">You can provide different Approver e-mail addresses or AGPM e-mail aliases on each domain's **Domain Delegation** tab, or use the same e-mail addresses throughout your environment.</span></span>

### <span data-ttu-id="fa324-121">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="fa324-121">Additional references</span></span>

-   [<span data-ttu-id="fa324-122">AGPM 管理者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="fa324-122">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks.md)

 

 





