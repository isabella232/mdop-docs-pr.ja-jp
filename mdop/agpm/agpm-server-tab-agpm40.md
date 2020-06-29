---
title: '[AGPM サーバー] タブ'
description: '[AGPM サーバー] タブ'
author: dansimp
ms.assetid: a6689437-233e-4f33-a0d6-f7d432c96c00
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7ffaa3f55d4ae1c2a59287d9dc302aec3dd00aed
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819284"
---
# <span data-ttu-id="04771-103">[AGPM サーバー] タブ</span><span class="sxs-lookup"><span data-stu-id="04771-103">AGPM Server Tab</span></span>


<span data-ttu-id="04771-104">[**変更**] ウィンドウの [ **agpm サーバー** ] タブでは、完全修飾コンピューター名とポートを入力して agpm サーバーを選ぶことができます。また、agpm サーバー上のディスク領域を節約するために、古いバージョンのグループポリシーオブジェクト (gpo) をアーカイブから削除します。</span><span class="sxs-lookup"><span data-stu-id="04771-104">The **AGPM Server** tab on the **Change Control** pane enables you to select an AGPM Server by entering a fully-qualified computer name and port, and to delete older versions of Group Policy Objects (GPOs) from the archive to conserve disk space on the AGPM Server.</span></span>

## <span data-ttu-id="04771-105">AGPM サーバーの指定</span><span class="sxs-lookup"><span data-stu-id="04771-105">Specifying the AGPM Server</span></span>


<span data-ttu-id="04771-106">選択された AGPM サーバーによって、[**コンテンツ**] タブに表示されるアーカイブと、**ドメイン委任**設定が適用される場所が決まります。</span><span class="sxs-lookup"><span data-stu-id="04771-106">The AGPM Server selected determines which archive is displayed for you on the **Contents** tab and to which location the **Domain Delegation** settings are applied.</span></span> <span data-ttu-id="04771-107">高度なグループポリシー管理 (AGPM) の既定のポートは、ポート4600です。</span><span class="sxs-lookup"><span data-stu-id="04771-107">The default port for Advanced Group Policy Management (AGPM) is port 4600.</span></span>

<span data-ttu-id="04771-108">AGPM サーバー接続が管理用テンプレート設定を使用して一元的に構成されている場合、接続を構成するためのこのタブのオプションは使用できません。</span><span class="sxs-lookup"><span data-stu-id="04771-108">If the AGPM Server connection is centrally configured using Administrative template settings, the options on this tab for configuring the connection are unavailable.</span></span> <span data-ttu-id="04771-109">詳細については、「 [AGPM サーバー接続を構成する](configure-agpm-server-connections-agpm40.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04771-109">For more information, see [Configure AGPM Server Connections](configure-agpm-server-connections-agpm40.md).</span></span>

## <span data-ttu-id="04771-110">古い GPO のバージョンを削除する</span><span class="sxs-lookup"><span data-stu-id="04771-110">Deleting old GPO versions</span></span>


<span data-ttu-id="04771-111">既定では、すべての制御された GPO のすべてのバージョンがアーカイブに保持されます。</span><span class="sxs-lookup"><span data-stu-id="04771-111">By default, all versions of every controlled GPO are retained in the archive.</span></span> <span data-ttu-id="04771-112">ただし、各 GPO に保持するバージョンの数を制限するように AGPM サービスを構成し、その制限を超えたときに最も古いバージョンを自動的に削除することができます。</span><span class="sxs-lookup"><span data-stu-id="04771-112">However, you can configure the AGPM Service to limit the number of versions retained for each GPO and automatically delete the oldest version when that limit is exceeded.</span></span> <span data-ttu-id="04771-113">[**履歴**] ウィンドウの [**一意のバージョン**] タブに表示される GPO バージョンのみが、制限をカウントします。</span><span class="sxs-lookup"><span data-stu-id="04771-113">Only GPO versions displayed on the **Unique Versions** tab of the **History** window count toward the limit.</span></span>

<span data-ttu-id="04771-114">**注** 各 GPO に保存する一意のバージョンの最大数には、現在のバージョンが含まれていないため、0を入力すると現在のバージョンのみが保持されます。</span><span class="sxs-lookup"><span data-stu-id="04771-114">**Note** The maximum number of unique versions to store for each GPO does not include the current version, so entering 0 retains only the current version.</span></span> <span data-ttu-id="04771-115">制限は、999のバージョンよりも大きくする必要があります。</span><span class="sxs-lookup"><span data-stu-id="04771-115">The limit must be no greater than 999 versions.</span></span>

<span data-ttu-id="04771-116">GPO のバージョンが削除されても、そのバージョンのレコードは GPO の履歴に残りますが、GPO のバージョン自体はアーカイブから削除されます。</span><span class="sxs-lookup"><span data-stu-id="04771-116">When a GPO version is deleted, a record of that version remains in the history of the GPO, but the GPO version itself is deleted from the archive.</span></span> <span data-ttu-id="04771-117">削除されないように、GPO を履歴にマークすることで、その GPO のバージョンが削除されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="04771-117">You can prevent a GPO version from being deleted by marking it in the history as not deletable.</span></span>

 

### <span data-ttu-id="04771-118">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="04771-118">Additional references</span></span>

-   [<span data-ttu-id="04771-119">ユーザー インターフェイス: 高度なグループ ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="04771-119">User Interface: Advanced Group Policy Management</span></span>](user-interface-advanced-group-policy-management-agpm40.md)

-   [<span data-ttu-id="04771-120">AGPM 管理者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="04771-120">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks-agpm40.md)

-   [<span data-ttu-id="04771-121">レビュー担当者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="04771-121">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm40.md)

 

 





