---
title: ADMX テンプレートとグループ ポリシーを使用して App-V 5.1 Client 構成を変更する方法
description: ADMX テンプレートとグループ ポリシーを使用して App-V 5.1 Client 構成を変更する方法
author: dansimp
ms.assetid: 0d9cf13a-b29c-4c87-a776-15fea34027dd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 18363b4fb904d995862ac30634be1350c972d918
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813826"
---
# <span data-ttu-id="ec973-103">ADMX テンプレートとグループ ポリシーを使用して App-V 5.1 Client 構成を変更する方法</span><span class="sxs-lookup"><span data-stu-id="ec973-103">How to Modify App-V 5.1 Client Configuration Using the ADMX Template and Group Policy</span></span>


<span data-ttu-id="ec973-104">Microsoft Application Virtualization (App-v) 5.1 ADMX テンプレートを使用して、ADMX テンプレートとグループポリシーを使用して App-v 5.1 クライアント設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="ec973-104">Use the Microsoft Application Virtualization (App-V) 5.1 ADMX template to configure App-V 5.1 client settings using the ADMX Template and Group Policy.</span></span>

**<span data-ttu-id="ec973-105">グループポリシーを使って App-v 5.1 クライアントの構成を変更するには</span><span class="sxs-lookup"><span data-stu-id="ec973-105">To modify App-V 5.1 client configuration using Group Policy</span></span>**

1.  <span data-ttu-id="ec973-106">App-v 5.1 クライアント構成を変更するには、App-v 5.1 で利用できる許可**Xtemplate**ファイルを探します。</span><span class="sxs-lookup"><span data-stu-id="ec973-106">To modify the App-V 5.1 client configuration, locate the **ADMXTemplate** files that are available with App-V 5.1.</span></span>

    <span data-ttu-id="ec973-107">**注** 次のリンクを使用して、App V 5.1 **ADMX テンプレート**をダウンロード <https://go.microsoft.com/fwlink/p/?LinkId=393941> します。</span><span class="sxs-lookup"><span data-stu-id="ec973-107">**Note** Use the following link to download the App-V 5.1 **ADMX Templates**: <https://go.microsoft.com/fwlink/p/?LinkId=393941>.</span></span>

     

2.  <span data-ttu-id="ec973-108">グループポリシーを管理するコンピューター (通常はドメインコントローラー) で、テンプレートの**admx**ファイルを次のディレクトリにコピーします。 \*\* &lt; インストールドライブ &gt; \ \ Windows \ ポリシー定義\*\*。</span><span class="sxs-lookup"><span data-stu-id="ec973-108">On the computer where you manage group Policy, typically the domain controller, copy the template **.admx** file to the following directory: **&lt;Installation Drive&gt; \\ Windows \\ PolicyDefinitions**.</span></span>

    <span data-ttu-id="ec973-109">次に、同じコンピューターで、 **adml**ファイルを次のディレクトリにコピーします。 \*\* &lt; インストールドライブ &gt; \ Windows \ \ ポリシーの定義 \ \ en-us\*\*。</span><span class="sxs-lookup"><span data-stu-id="ec973-109">Next, on the same computer, copy the **.adml** file to the following directory: **&lt;InstallationDrive&gt; \\ Windows \\ PolicyDefinitions \\ en-US**.</span></span>

3.  <span data-ttu-id="ec973-110">ファイルをコピーした後、グループポリシー管理コンソールを開いて、5.1 アプリに関連付けられているポリシーを変更するには、[**コンピューター構成**  /  **ポリシー**] の  /  **管理用テンプレート**  /  **System**  /  **App**に移動します。</span><span class="sxs-lookup"><span data-stu-id="ec973-110">After you have copied the files open the Group Policy Management Console, to modify the policies associated with your App-V 5.1 clients browse to **Computer Configuration** / **Policies** / **Administrative Templates** / **System** / **App-V**.</span></span>

    <span data-ttu-id="ec973-111">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="ec973-111">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="ec973-112">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="ec973-112">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="ec973-113">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="ec973-113">Got an App-V issue?</span></span>** <span data-ttu-id="ec973-114">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="ec973-114">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="ec973-115">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ec973-115">Related topics</span></span>


[<span data-ttu-id="ec973-116">APP-V 5.1 の展開</span><span class="sxs-lookup"><span data-stu-id="ec973-116">Deploying App-V 5.1</span></span>](deploying-app-v-51.md)

[<span data-ttu-id="ec973-117">Client の構成設定について</span><span class="sxs-lookup"><span data-stu-id="ec973-117">About Client Configuration Settings</span></span>](about-client-configuration-settings51.md)

 

 





