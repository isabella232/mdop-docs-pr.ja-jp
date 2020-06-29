---
title: AGPM サーバー接続を構成する
description: AGPM サーバー接続を構成する
author: dansimp
ms.assetid: 409cbbcf-3b0e-459d-9bd2-75cb7b9430b0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d7fdc26045b478da14957cdfe6000d58ab72a064
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819084"
---
# <span data-ttu-id="284bc-103">AGPM サーバー接続を構成する</span><span class="sxs-lookup"><span data-stu-id="284bc-103">Configure an AGPM Server Connection</span></span>


<span data-ttu-id="284bc-104">正しい中央のアーカイブに接続されていることを確認するには、AGPM サーバー接続の構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="284bc-104">To ensure that you are connected to the correct central archive, review the configuration of the AGPM Server connection.</span></span> <span data-ttu-id="284bc-105">AGPM 管理者 (フルコントロール) で、AGPM サーバー接続が構成されていない場合は、手動で構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="284bc-105">If an AGPM Administrator (Full Control) has not configured an AGPM Server connection for you, then you must manually configure it.</span></span>

**<span data-ttu-id="284bc-106">AGPM サーバーを選ぶには</span><span class="sxs-lookup"><span data-stu-id="284bc-106">To select an AGPM Server</span></span>**

1.  <span data-ttu-id="284bc-107">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="284bc-107">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="284bc-108">詳細ウィンドウで、[ **AGPM サーバー** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="284bc-108">In the details pane, click the **AGPM Server** tab:</span></span>

    -   <span data-ttu-id="284bc-109">**Agpm サーバー**タブのオプションが使用できない場合は、Agpm 管理者によって一元的に構成されています。</span><span class="sxs-lookup"><span data-stu-id="284bc-109">If the options on the **AGPM Server** tab are unavailable, they have been centrally configured by an AGPM Administrator.</span></span>

    -   <span data-ttu-id="284bc-110">[ **Agpm サーバー** ] タブのオプションが使用可能な場合は、agpm サーバーの完全修飾コンピューター名 (server.contoso.com など) と、agpm サービスがリッスンするポート (既定では、ポート 4600) を入力します。</span><span class="sxs-lookup"><span data-stu-id="284bc-110">If the options on the **AGPM Server** tab are available, type the fully-qualified computer name for the AGPM Server (for example, server.contoso.com) and the port on which the AGPM Service listens (by default, port 4600).</span></span> <span data-ttu-id="284bc-111">[**適用**] をクリックし、[**はい**] をクリックして確認します。</span><span class="sxs-lookup"><span data-stu-id="284bc-111">Click **Apply**, then click **Yes** to confirm.</span></span>

### <span data-ttu-id="284bc-112">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="284bc-112">Additional considerations</span></span>

-   <span data-ttu-id="284bc-113">選択された AGPM サーバーによって、[**コンテンツ**] タブに表示される gpo と、[**ドメイン委任**] タブの設定が適用される場所が決まります。</span><span class="sxs-lookup"><span data-stu-id="284bc-113">The AGPM Servers selected determine which GPOs are displayed on the **Contents** tab and to what location the **Domain Delegation** tab settings are applied.</span></span> <span data-ttu-id="284bc-114">管理用テンプレートで一元管理されていない場合は、各グループポリシー管理者がこの設定を構成して、ドメインの AGPM サーバーを指すようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="284bc-114">If not centrally managed through the Administrative template, each Group Policy administrator must configure this setting to point to the AGPM Server for the domain.</span></span>

### <span data-ttu-id="284bc-115">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="284bc-115">Additional references</span></span>

-   [<span data-ttu-id="284bc-116">レビュー担当者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="284bc-116">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm40.md)

 

 





