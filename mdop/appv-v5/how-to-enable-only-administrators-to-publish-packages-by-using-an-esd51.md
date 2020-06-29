---
title: ESD を使用して管理者のみが公開パッケージを有効にできるようにする方法
description: ESD を使用して管理者のみが公開パッケージを有効にできるようにする方法
author: dansimp
ms.assetid: bbc9fda2-fc09-4d72-8d9a-e83d2fcfe234
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 22de7f62f540ceff274862c3f16b1f89d9459093
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814091"
---
# <span data-ttu-id="4230e-103">ESD を使用して管理者のみが公開パッケージを有効にできるようにする方法</span><span class="sxs-lookup"><span data-stu-id="4230e-103">How to Enable Only Administrators to Publish Packages by Using an ESD</span></span>


<span data-ttu-id="4230e-104">App-v 5.0 SP3 以降では、管理者 (エンドユーザー以外) だけがパッケージを公開または非公開にすることができるように、App-v クライアントを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="4230e-104">Starting in App-V 5.0 SP3, you can configure the App-V client so that only administrators (not end users) can publish or unpublish packages.</span></span> <span data-ttu-id="4230e-105">以前のバージョンの App-v では、エンドユーザーがこれらのタスクを実行できないようにすることはできませんでした。</span><span class="sxs-lookup"><span data-stu-id="4230e-105">In earlier versions of App-V, you could not prevent end users from performing these tasks.</span></span>

**<span data-ttu-id="4230e-106">管理者のみがパッケージの発行または発行を取り消すことができるようにするには</span><span class="sxs-lookup"><span data-stu-id="4230e-106">To enable only administrators to publish or unpublish packages</span></span>**

1.  <span data-ttu-id="4230e-107">次のグループポリシーオブジェクトノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="4230e-107">Navigate to the following Group Policy Object node:</span></span>

    <span data-ttu-id="4230e-108">**コンピューターの構成 &gt;ポリシー &gt; 管理用テンプレート &gt; システム &gt; アプリ-V の &gt; 公開**。</span><span class="sxs-lookup"><span data-stu-id="4230e-108">**Computer Configuration &gt; Policies &gt; Administrative Templates &gt; System &gt; App-V &gt; Publishing**.</span></span>

2.  <span data-ttu-id="4230e-109">[**管理者として発行する**] グループポリシーの設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="4230e-109">Enable the **Require publish as administrator** Group Policy setting.</span></span>

    <span data-ttu-id="4230e-110">または、PowerShell を使用してこの項目を設定するには、 [Powershell を使用してスタンドアロンコンピューターで実行されている app-v 5.1 パッケージを管理する方法](how-to-manage-app-v-51-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admins-pub-pkgs)に関する説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4230e-110">To alternatively use PowerShell to set this item, see [How to Manage App-V 5.1 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-51-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admins-pub-pkgs).</span></span>

    <span data-ttu-id="4230e-111">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="4230e-111">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="4230e-112">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="4230e-112">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="4230e-113">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="4230e-113">Got an App-V issue?</span></span>** <span data-ttu-id="4230e-114">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="4230e-114">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

 

 





