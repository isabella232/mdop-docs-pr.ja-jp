---
title: 運用環境から GPO をインポートする
description: 運用環境から GPO をインポートする
author: dansimp
ms.assetid: ffa02b2a-2a43-4fc0-a06e-7d4b59022cc3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 239ac6938645325292bfc647ef89a77710c5f074
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820677"
---
# <span data-ttu-id="bb08c-103">運用環境から GPO をインポートする</span><span class="sxs-lookup"><span data-stu-id="bb08c-103">Import a GPO from Production</span></span>


<span data-ttu-id="bb08c-104">高度なグループポリシー管理 (AGPM) の外部でコントロールされたグループポリシーオブジェクト (GPO) に変更が加えられた場合、その GPO のコピーを運用環境からインポートし、アーカイブに保存して、アーカイブと運用環境を一貫した状態にすることができます。</span><span class="sxs-lookup"><span data-stu-id="bb08c-104">If changes are made to a controlled Group Policy object (GPO) outside of Advanced Group Policy Management (AGPM), you can import a copy of the GPO from the production environment and save it to the archive to bring the archive and the production environment to a consistent state.</span></span> <span data-ttu-id="bb08c-105">(制御されていない GPO をインポートするには、GPO を制御します。</span><span class="sxs-lookup"><span data-stu-id="bb08c-105">(To import an uncontrolled GPO, control the GPO.</span></span> <span data-ttu-id="bb08c-106">「前に制御していない[GPO の制御を要求する」を](request-control-of-a-previously-uncontrolled-gpo.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb08c-106">See [Request Control of a Previously Uncontrolled GPO](request-control-of-a-previously-uncontrolled-gpo.md).)</span></span>

<span data-ttu-id="bb08c-107">この手順を完了するには、エディター、承認者、または AGPM 管理者 (フルコントロール) の役割を持つユーザーアカウント、または高度なグループポリシー管理の必要なアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="bb08c-107">A user account with the Editor, Approver, or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="bb08c-108">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb08c-108">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="bb08c-109">運用環境から GPO をインポートするには</span><span class="sxs-lookup"><span data-stu-id="bb08c-109">To import a GPO from the production environment</span></span>**

1.  <span data-ttu-id="bb08c-110">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb08c-110">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="bb08c-111">[**コンテンツ**] タブで、[**コントロール**] タブをクリックして、管理された gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="bb08c-111">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="bb08c-112">GPO を右クリックし、[**生産からのインポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb08c-112">Right-click the GPO, and then click **Import from Production**.</span></span>

4.  <span data-ttu-id="bb08c-113">GPO の監査記録に関するコメントを入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb08c-113">Type a comment for the audit trail of the GPO, then click **OK**.</span></span>

### <span data-ttu-id="bb08c-114">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="bb08c-114">Additional considerations</span></span>

-   <span data-ttu-id="bb08c-115">既定では、この手順を実行するには、編集者、承認者、または AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb08c-115">By default, you must be an Editor, Approver, or AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="bb08c-116">具体的には、GPO**の [** 設定の**編集**]、[ **gpo の展開**]、または [gpo の**削除**] のアクセス許可を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb08c-116">Specifically, you must have **List Contents** and either **Edit Settings**, **Deploy GPO**, or **Delete GPO** permissions for the GPO.</span></span>

### <span data-ttu-id="bb08c-117">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="bb08c-117">Additional references</span></span>

-   [<span data-ttu-id="bb08c-118">GPO の作成、制御、インポート</span><span class="sxs-lookup"><span data-stu-id="bb08c-118">Creating, Controlling, or Importing a GPO</span></span>](creating-controlling-or-importing-a-gpo-editor.md)

 

 





