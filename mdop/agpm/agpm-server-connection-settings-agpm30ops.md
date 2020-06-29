---
title: AGPM サーバー接続の設定
description: AGPM サーバー接続の設定
author: dansimp
ms.assetid: 5f03e397-b868-4c49-9cbf-a5f5d0ddcc39
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d9ee1e67eb2c565bcf833314d82cdf611e2caa85
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812987"
---
# <span data-ttu-id="ec7d4-103">AGPM サーバー接続の設定</span><span class="sxs-lookup"><span data-stu-id="ec7d4-103">AGPM Server Connection Settings</span></span>


<span data-ttu-id="ec7d4-104">高度なグループポリシー管理 (AGPM) 用の管理用テンプレート設定を使用して、これらの設定が適用されているグループポリシーオブジェクト (GPO) のグループポリシー管理者向けの AGPM サーバー接続を一元的に構成することができます。</span><span class="sxs-lookup"><span data-stu-id="ec7d4-104">You can use Administrative template settings for Advanced Group Policy Management (AGPM) to centrally configure AGPM Server connections for Group Policy administrators to whom a Group Policy Object (GPO) with these settings is applied.</span></span>

<span data-ttu-id="ec7d4-105">GPO を編集するときに、ユーザー Configuration\\Policies\\Administrative Templates\\Windows Components\\AGPM で次の設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ec7d4-105">The following settings are available under User Configuration\\Policies\\Administrative Templates\\Windows Components\\AGPM when editing a GPO.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ec7d4-106">設定</span><span class="sxs-lookup"><span data-stu-id="ec7d4-106">Setting</span></span></th>
<th align="left"><span data-ttu-id="ec7d4-107">効果</span><span class="sxs-lookup"><span data-stu-id="ec7d4-107">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="ec7d4-108">AGPM: 既定の AGPM サーバー (すべてのドメイン) を指定する</span><span class="sxs-lookup"><span data-stu-id="ec7d4-108">AGPM: Specify default AGPM Server (all domains)</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ec7d4-109">このポリシー設定では、すべてのドメインに対して既定の AGPM サーバーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ec7d4-109">This policy setting allows you to specify a default AGPM Server for all domains.</span></span> <span data-ttu-id="ec7d4-110">これは、AGPM クライアントでのみ使用され、グループポリシー管理者が別のアーカイブに接続することを制限します。</span><span class="sxs-lookup"><span data-stu-id="ec7d4-110">This is used only by AGPM Clients, and restricts Group Policy administrators from connecting to another archive.</span></span> <span data-ttu-id="ec7d4-111"><strong>Agpm: Agpm サーバー設定を使用して、個々のドメインに対してこの既定値を上書きできます </strong> 。</span><span class="sxs-lookup"><span data-stu-id="ec7d4-111">You can override this default for individual domains using the <strong>AGPM: Specify AGPM Servers</strong> setting.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="ec7d4-112">AGPM: AGPM サーバーを指定する</span><span class="sxs-lookup"><span data-stu-id="ec7d4-112">AGPM: Specify AGPM Servers</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ec7d4-113">このポリシー設定では、個々のドメインに対して AGPM サーバーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ec7d4-113">This policy setting allows you to specify the AGPM Servers for individual domains.</span></span> <span data-ttu-id="ec7d4-114">これは、AGPM クライアントでのみ使用され、グループポリシー管理者が指定したドメインの別のアーカイブに接続することを制限します。</span><span class="sxs-lookup"><span data-stu-id="ec7d4-114">This is used only by AGPM Clients, and restricts Group Policy administrators from connecting to a different archive for the specified domain.</span></span> <span data-ttu-id="ec7d4-115">既定の AGPM サーバーを指定するには、 <strong> agpm: DEFAULT Agpm server (すべてのドメイン) の設定を使用 </strong> し、このポリシー設定を使用して、ドメインごとに既定値を上書きします。</span><span class="sxs-lookup"><span data-stu-id="ec7d4-115">To specify a default AGPM Server, use the <strong>AGPM: Specify default AGPM Server (all domains)</strong> setting and use this policy setting to override the default on a per domain basis.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="ec7d4-116">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="ec7d4-116">Additional references</span></span>

-   [<span data-ttu-id="ec7d4-117">[管理用テンプレート] フォルダー</span><span class="sxs-lookup"><span data-stu-id="ec7d4-117">Administrative Templates Folder</span></span>](administrative-templates-folder-agpm30ops.md)

-   [<span data-ttu-id="ec7d4-118">AGPM 管理者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="ec7d4-118">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks-agpm30ops.md)

 

 





