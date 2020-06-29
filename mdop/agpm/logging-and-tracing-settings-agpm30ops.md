---
title: ログとトレースの設定
description: ログとトレースの設定
author: dansimp
ms.assetid: 858b6fbf-65b4-42fa-95a9-69b04e5734d7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 078bda16b5fcf968d45e0c4890487471105e8c44
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820594"
---
# <span data-ttu-id="5fdac-103">ログとトレースの設定</span><span class="sxs-lookup"><span data-stu-id="5fdac-103">Logging and Tracing Settings</span></span>


<span data-ttu-id="5fdac-104">高度なグループポリシー管理 (AGPM) の管理用テンプレート設定では、これらの設定が適用されたグループポリシーオブジェクト (GPO) を適用する AGPM サーバーとクライアントのログとトレースオプションを一元的に構成することができます。</span><span class="sxs-lookup"><span data-stu-id="5fdac-104">The Administrative template settings for Advanced Group Policy Management (AGPM) enable you to centrally configure logging and tracing options for AGPM Servers and clients to which a Group Policy Object (GPO) with these settings is applied.</span></span>

<span data-ttu-id="5fdac-105">GPO を編集するときに、[コンピューター Configuration\\Policies\\Administrative Templates\\Windows Components\\AGPM で次の設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5fdac-105">The following setting is available under Computer Configuration\\Policies\\Administrative Templates\\Windows Components\\AGPM when editing a GPO.</span></span>

<span data-ttu-id="5fdac-106">**トレースファイルの場所**:</span><span class="sxs-lookup"><span data-stu-id="5fdac-106">**Trace file locations**:</span></span>

-   <span data-ttu-id="5fdac-107">クライアント:%LocalAppData%\\Microsoft\\AGPM\\agpm.log</span><span class="sxs-lookup"><span data-stu-id="5fdac-107">Client: %LocalAppData%\\Microsoft\\AGPM\\agpm.log</span></span>

-   <span data-ttu-id="5fdac-108">サーバー:%ProgramData%\\Microsoft\\AGPM\\agpmserv.log</span><span class="sxs-lookup"><span data-stu-id="5fdac-108">Server: %ProgramData%\\Microsoft\\AGPM\\agpmserv.log</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5fdac-109">設定</span><span class="sxs-lookup"><span data-stu-id="5fdac-109">Setting</span></span></th>
<th align="left"><span data-ttu-id="5fdac-110">効果</span><span class="sxs-lookup"><span data-stu-id="5fdac-110">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="5fdac-111">AGPM: ログを構成する</span><span class="sxs-lookup"><span data-stu-id="5fdac-111">AGPM: Configure logging</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5fdac-112">このポリシー設定では、AGPM のログを有効にし、構成することができます。</span><span class="sxs-lookup"><span data-stu-id="5fdac-112">This policy setting allows you to turn on and configure logging for AGPM.</span></span> <span data-ttu-id="5fdac-113">この設定は、AGPM のクライアントコンポーネントとサーバーコンポーネントの両方に影響します。</span><span class="sxs-lookup"><span data-stu-id="5fdac-113">This setting affects both client and server components of AGPM.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="5fdac-114">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="5fdac-114">Additional references</span></span>

-   [<span data-ttu-id="5fdac-115">[管理用テンプレート] フォルダー</span><span class="sxs-lookup"><span data-stu-id="5fdac-115">Administrative Templates Folder</span></span>](administrative-templates-folder-agpm30ops.md)

 

 





