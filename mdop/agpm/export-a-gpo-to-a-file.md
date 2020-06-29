---
title: GPO をファイルにエクスポートする
description: GPO をファイルにエクスポートする
author: dansimp
ms.assetid: 0d01b1f7-a6a4-4d0d-9aa7-2d6f1ae93d9d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4622930cb0e5b439649cc0445ae2b3d02d7d3224
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820854"
---
# <span data-ttu-id="2c163-103">GPO をファイルにエクスポートする</span><span class="sxs-lookup"><span data-stu-id="2c163-103">Export a GPO to a File</span></span>


<span data-ttu-id="2c163-104">管理されたグループポリシーオブジェクト (GPO) を CAB ファイルにエクスポートして、別のフォレストのドメインにコピーし、そのドメインの高度なグループポリシー管理 (AGPM) に GPO をインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="2c163-104">You can export a controlled Group Policy Object (GPO) to a CAB file so that you can copy it to a domain in another forest and import the GPO into Advanced Group Policy Management (AGPM) in that domain.</span></span> <span data-ttu-id="2c163-105">GPO 設定を新規または既存の GPO にインポートする方法について詳しくは、「[ファイルから gpo をインポート](import-a-gpo-from-a-file-ed.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2c163-105">For information about how to import GPO settings into a new or existing GPO, see [Import a GPO from a File](import-a-gpo-from-a-file-ed.md).</span></span>

<span data-ttu-id="2c163-106">この手順を完了するには、Editor または AGPM 管理者 (フルコントロール) の役割を持つ、または高度なグループポリシー管理 (AGPM) に必要なアクセス許可を持つユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="2c163-106">A user account with the Editor or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span><span data-ttu-id="2c163-107">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c163-107">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="2c163-108">GPO をファイルにエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="2c163-108">To export a GPO to a file</span></span>**

1.  <span data-ttu-id="2c163-109">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c163-109">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="2c163-110">[**コンテンツ**] タブで、[**コントロール**] タブをクリックして、管理された gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="2c163-110">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="2c163-111">GPO を右クリックし、[**エクスポート先**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c163-111">Right-click the GPO, and then click **Export to**.</span></span>

4.  <span data-ttu-id="2c163-112">GPO をエクスポートするファイルのファイル名を入力し、[**エクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c163-112">Enter a file name for the file to which you want to export the GPO, and then click **Export**.</span></span> <span data-ttu-id="2c163-113">ファイルが存在しない場合は、作成されます。</span><span class="sxs-lookup"><span data-stu-id="2c163-113">If the file does not exist, it is created.</span></span> <span data-ttu-id="2c163-114">既に存在する場合は、置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="2c163-114">If it already exists, it is replaced.</span></span>

### <span data-ttu-id="2c163-115">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="2c163-115">Additional considerations</span></span>

-   <span data-ttu-id="2c163-116">既定では、この手順を実行するには、Editor または AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c163-116">By default, you must be an Editor or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="2c163-117">具体的には、GPO の [**コンテンツの一覧表示**]、[**設定の読み取り**]、[ **gpo のエクスポート**] のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="2c163-117">Specifically, you must have **List Contents**, **Read Settings**, and **Export GPO** permissions for the GPO.</span></span>

### <span data-ttu-id="2c163-118">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="2c163-118">Additional references</span></span>

-   [<span data-ttu-id="2c163-119">テスト環境の使用</span><span class="sxs-lookup"><span data-stu-id="2c163-119">Using a Test Environment</span></span>](using-a-test-environment.md)

 

 





