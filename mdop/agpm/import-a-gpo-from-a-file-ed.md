---
title: ファイルから GPO をインポートする
description: ファイルから GPO をインポートする
author: dansimp
ms.assetid: 6e901a52-1101-4fed-9f90-3819b573b378
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e15704806f089bb0d8530cd84df64b0889413426
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820724"
---
# <span data-ttu-id="00c3f-103">ファイルから GPO をインポートする</span><span class="sxs-lookup"><span data-stu-id="00c3f-103">Import a GPO from a File</span></span>


<span data-ttu-id="00c3f-104">高度なグループポリシー管理 (AGPM) で、グループポリシーオブジェクト (GPO) を CAB ファイルにエクスポートした場合、その GPO から別のフォレストのドメイン内の既存の GPO にポリシー設定をインポートできます。</span><span class="sxs-lookup"><span data-stu-id="00c3f-104">In Advanced Group Policy Management (AGPM), if you have exported a Group Policy Object (GPO) to a CAB file, you can import the policy settings from that GPO into an existing GPO in a domain in another forest.</span></span> <span data-ttu-id="00c3f-105">既存の GPO にポリシー設定をインポートすると、その GPO 内のすべてのポリシー設定が置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="00c3f-105">Importing policy settings into an existing GPO replaces all policy settings within that GPO.</span></span> <span data-ttu-id="00c3f-106">CAB ファイルに GPO 設定をエクスポートする方法について詳しくは、「 [gpo をファイルにエクスポート](export-a-gpo-to-a-file.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="00c3f-106">For information about exporting GPO settings to a CAB file, see [Export a GPO to a File](export-a-gpo-to-a-file.md).</span></span>

<span data-ttu-id="00c3f-107">この手順を完了するには、Editor または AGPM 管理者 (フルコントロール) の役割を持つ、または高度なグループポリシー管理 (AGPM) に必要なアクセス許可を持つユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="00c3f-107">A user account with the Editor or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span><span data-ttu-id="00c3f-108">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00c3f-108">Review the details in "Additional considerations" in this topic.</span></span>

## <a href="" id="bkmk-existing"></a>


**<span data-ttu-id="00c3f-109">既存の GPO にポリシー設定をインポートするには</span><span class="sxs-lookup"><span data-stu-id="00c3f-109">To import policy settings into an existing GPO</span></span>**

1.  <span data-ttu-id="00c3f-110">[**グループポリシー管理コンソール**] ツリーで、ポリシー設定をインポートするドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="00c3f-110">In the **Group Policy Management Console** tree, click **Change Control** in the domain to which you want to import policy settings.</span></span>

2.  <span data-ttu-id="00c3f-111">[**コンテンツ**] タブで、[**コントロール**] タブをクリックして、管理された gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="00c3f-111">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="00c3f-112">ポリシー設定をインポートする宛先 GPO を確認します。</span><span class="sxs-lookup"><span data-stu-id="00c3f-112">Check out the destination GPO to which you want to import policy settings.</span></span>

4.  <span data-ttu-id="00c3f-113">送信先 GPO を右クリックし、[**インポート元**] をポイントして、[**ファイル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="00c3f-113">Right-click the destination GPO, point to **Import from**, and then click **File**.</span></span>

5.  <span data-ttu-id="00c3f-114">**設定のインポートウィザード**の指示に従って、GPO のバックアップを選び、宛先 gpo のポリシー設定をインポートして、移行先 gpo の監査証跡に関するコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="00c3f-114">Follow the instructions in the **Import Settings Wizard** to select a GPO backup, import its policy settings to replace those in the destination GPO, and enter a comment for the audit trail of the destination GPO.</span></span> <span data-ttu-id="00c3f-115">既定では、ウィザードが終了すると、送信先 GPO がチェックインされます。</span><span class="sxs-lookup"><span data-stu-id="00c3f-115">By default, the destination GPO is checked in when the wizard is finished.</span></span>

### <span data-ttu-id="00c3f-116">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="00c3f-116">Additional considerations</span></span>

-   <span data-ttu-id="00c3f-117">既定では、この手順を実行するには、Editor または AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="00c3f-117">By default, you must be an Editor or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="00c3f-118">具体的には、ドメインの [**コンテンツの一覧表示**]、[**設定の編集**]、[ **gpo のインポート**] のアクセス許可が必要であり、gpo をチェックアウトする必要があります。</span><span class="sxs-lookup"><span data-stu-id="00c3f-118">Specifically, you must have **List Contents**, **Edit Settings**, and **Import GPO** permissions for the domain, and the GPO must be checked out by you.</span></span>

-   <span data-ttu-id="00c3f-119">エディターは、作成中に新しい GPO にポリシー設定をインポートすることはできませんが、新しい GPO の作成を要求し、それを作成した後でポリシー設定をインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="00c3f-119">Although an Editor cannot import policy settings into a new GPO during its creation, an Editor can request the creation of a new GPO and then import policy settings into it after it is created.</span></span>

### <span data-ttu-id="00c3f-120">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="00c3f-120">Additional references</span></span>

-   [<span data-ttu-id="00c3f-121">テスト環境の使用</span><span class="sxs-lookup"><span data-stu-id="00c3f-121">Using a Test Environment</span></span>](using-a-test-environment.md)

 

 





