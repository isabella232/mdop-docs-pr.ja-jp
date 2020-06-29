---
title: ログとトレースの設定
description: ログとトレースの設定
author: dansimp
ms.assetid: db6b43c7-fdde-4d11-b5ab-a81346e56940
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bef0f8367647aad688c2aec7586ecdaae2e22143
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820587"
---
# <span data-ttu-id="3657e-103">ログとトレースの設定</span><span class="sxs-lookup"><span data-stu-id="3657e-103">Logging and Tracing Settings</span></span>


<span data-ttu-id="3657e-104">高度なグループポリシー管理 (AGPM) の管理用テンプレート設定では、これらの設定が適用されたグループポリシーオブジェクト (GPO) を適用する AGPM サーバーとクライアントのログとトレースオプションを一元的に構成することができます。</span><span class="sxs-lookup"><span data-stu-id="3657e-104">The Administrative Template settings for Advanced Group Policy Management (AGPM) enable you to centrally configure logging and tracing options for AGPM Servers and clients to which a Group Policy object (GPO) with these settings is applied.</span></span>

<span data-ttu-id="3657e-105">グループポリシー管理コンソール (GPMC) で GPO を編集するときに、**グループポリシーオブジェクトエディター**のコンピューター構成 \\ 管理 Templates\\Windows Components\\AGPM の下で、次の設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3657e-105">The following setting is available under Computer Configuration\\Administrative Templates\\Windows Components\\AGPM in the **Group Policy Object Editor** when editing a GPO in the Group Policy Management Console (GPMC).</span></span> <span data-ttu-id="3657e-106">このパスが表示されない場合は、[**管理用テンプレート**] を右クリックして、agpm または agpm テンプレートを追加します。</span><span class="sxs-lookup"><span data-stu-id="3657e-106">If this path is not visible, right-click **Administrative Templates**, and add the agpm.admx or agpm.adm template.</span></span>

<span data-ttu-id="3657e-107">**トレースファイルの場所**:</span><span class="sxs-lookup"><span data-stu-id="3657e-107">**Trace file locations**:</span></span>

-   <span data-ttu-id="3657e-108">クライアント:%LocalAppData%\\Microsoft\\AGPM\\agpm.log</span><span class="sxs-lookup"><span data-stu-id="3657e-108">Client: %LocalAppData%\\Microsoft\\AGPM\\agpm.log</span></span>

-   <span data-ttu-id="3657e-109">サーバー:%CommonAppData%\\Microsoft\\AGPM\\agpmserv.log</span><span class="sxs-lookup"><span data-stu-id="3657e-109">Server: %CommonAppData%\\Microsoft\\AGPM\\agpmserv.log</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3657e-110">設定</span><span class="sxs-lookup"><span data-stu-id="3657e-110">Setting</span></span></th>
<th align="left"><span data-ttu-id="3657e-111">効果</span><span class="sxs-lookup"><span data-stu-id="3657e-111">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3657e-112">AGPM ログ</span><span class="sxs-lookup"><span data-stu-id="3657e-112">AGPM Logging</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3657e-113">この設定を有効にすると、トレースを有効にするか、詳細レベルを設定するかが構成されます。</span><span class="sxs-lookup"><span data-stu-id="3657e-113">If enabled, this setting configures whether tracing is turned on and the level of detail.</span></span> <span data-ttu-id="3657e-114">この設定は、AGPM のクライアントコンポーネントとサーバーコンポーネントの両方に影響します。</span><span class="sxs-lookup"><span data-stu-id="3657e-114">This setting affects both client and server components of AGPM.</span></span></p>
<p><span data-ttu-id="3657e-115">無効にした場合、または構成しなかった場合、この設定には影響はありません。</span><span class="sxs-lookup"><span data-stu-id="3657e-115">If disabled or not configured, this setting has no effect.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="3657e-116">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="3657e-116">Additional references</span></span>

-   [<span data-ttu-id="3657e-117">管理用テンプレートの設定</span><span class="sxs-lookup"><span data-stu-id="3657e-117">Administrative Template Settings</span></span>](administrative-template-settings.md)

 

 





