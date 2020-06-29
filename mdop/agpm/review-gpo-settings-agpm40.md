---
title: GPO の設定を確認する
description: GPO の設定を確認する
author: dansimp
ms.assetid: c346bcde-dd6a-4775-aeab-721ca3a361b2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 336118fb8d099fa5a373415320e7ca5ce8bde761
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820294"
---
# <span data-ttu-id="d5e88-103">GPO の設定を確認する</span><span class="sxs-lookup"><span data-stu-id="d5e88-103">Review GPO Settings</span></span>


<span data-ttu-id="d5e88-104">任意のバージョンのグループポリシーオブジェクト (GPO) 内の設定を確認するために、HTML ベースおよび XML ベースのレポートを生成することができます。</span><span class="sxs-lookup"><span data-stu-id="d5e88-104">You can generate HTML-based and XML-based reports for reviewing settings within any version of a Group Policy Object (GPO).</span></span>

<span data-ttu-id="d5e88-105">この手順を完了するには、レビュー担当者、編集者、承認者、または AGPM 管理者 (フルコントロール) の役割、または詳細なグループポリシー管理 (AGPM) に必要なアクセス許可を持つユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="d5e88-105">A user account with the Reviewer, Editor, Approver, or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM)is required to complete this procedure.</span></span> <span data-ttu-id="d5e88-106">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5e88-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="d5e88-107">GPO の任意のバージョンで設定を確認するには</span><span class="sxs-lookup"><span data-stu-id="d5e88-107">To review settings in any version of a GPO</span></span>**

1.  <span data-ttu-id="d5e88-108">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5e88-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="d5e88-109">[詳細] ウィンドウの [**コンテンツ**] タブで、タブをクリックして gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="d5e88-109">On the **Contents** tab in the details pane, click a tab to display GPOs.</span></span>

3.  <span data-ttu-id="d5e88-110">GPO をダブルクリックして、その履歴を表示します。</span><span class="sxs-lookup"><span data-stu-id="d5e88-110">Double-click the GPO to display its history.</span></span>

4.  <span data-ttu-id="d5e88-111">設定を確認する GPO のバージョンを右クリックし、[**設定**] をクリックし、[ **HTML レポート**] または [ **XML レポート**] をクリックして、gpo の設定の概要を表示します。</span><span class="sxs-lookup"><span data-stu-id="d5e88-111">Right-click the GPO version for which to review the settings, click **Settings**, and then click **HTML Report** or **XML Report** to display a summary of the GPO's settings.</span></span>

### <span data-ttu-id="d5e88-112">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="d5e88-112">Additional considerations</span></span>

-   <span data-ttu-id="d5e88-113">既定では、この手順を実行するには、レビュー担当者、編集者、承認者、AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5e88-113">By default, you must be a Reviewer, an Editor, an Approver, or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="d5e88-114">具体的には、GPO の [**リストコンテンツ]** と [**読み取り設定**] のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="d5e88-114">Specifically, you must have **List Contents** and **Read Settings** permissions for the GPO.</span></span> <span data-ttu-id="d5e88-115">また、Gpo の一覧を表示するには、ドメインの**リストコンテンツ**のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="d5e88-115">Also, to display the list of GPOs, you must have **List Contents** permission for the domain.</span></span>

### <span data-ttu-id="d5e88-116">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="d5e88-116">Additional references</span></span>

-   [<span data-ttu-id="d5e88-117">レビュー担当者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="d5e88-117">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm40.md)

 

 





