---
title: AGPM サーバー接続の設定
description: AGPM サーバー接続の設定
author: dansimp
ms.assetid: faf78e5b-2b0d-4069-9b8c-910add892200
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d63163de0a1adf744e6d442b8073e5b32352ed67
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813019"
---
# <span data-ttu-id="33c0a-103">AGPM サーバー接続の設定</span><span class="sxs-lookup"><span data-stu-id="33c0a-103">AGPM Server Connection Settings</span></span>


<span data-ttu-id="33c0a-104">高度なグループポリシー管理 (AGPM) 用の管理用テンプレート設定を使用して、これらの設定が適用されているグループポリシーオブジェクト (GPO) のグループポリシー管理者向けの AGPM サーバー接続を一元的に構成することができます。</span><span class="sxs-lookup"><span data-stu-id="33c0a-104">You can use Administrative template settings for Advanced Group Policy Management (AGPM) to centrally configure AGPM Server connections for Group Policy administrators to whom a Group Policy object (GPO) with these settings is applied.</span></span>

<span data-ttu-id="33c0a-105">GPO を編集している場合は、ユーザー構成 \\ 管理 Templates\\Windows Components\\AGPM の下で次の設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="33c0a-105">The following settings are available under User Configuration\\Administrative Templates\\Windows Components\\AGPM when editing a GPO.</span></span> <span data-ttu-id="33c0a-106">このパスが表示されない場合は、[**管理用テンプレート**] を右クリックして、agpm または agpm テンプレートを追加します。</span><span class="sxs-lookup"><span data-stu-id="33c0a-106">If this path is not visible, right-click **Administrative Templates**, and add the agpm.admx or agpm.adm template.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="33c0a-107">設定</span><span class="sxs-lookup"><span data-stu-id="33c0a-107">Setting</span></span></th>
<th align="left"><span data-ttu-id="33c0a-108">効果</span><span class="sxs-lookup"><span data-stu-id="33c0a-108">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="33c0a-109">AGPM サーバー (すべてのドメイン)</span><span class="sxs-lookup"><span data-stu-id="33c0a-109">AGPM Server (all domains)</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="33c0a-110">この設定を有効にすると、すべてのドメインで使用する AGPM サーバー接続を1つだけ構成し、 <strong> グループポリシー管理者の [Agpm サーバー] タブの設定を無効にすることが </strong> できます。</span><span class="sxs-lookup"><span data-stu-id="33c0a-110">If enabled, this setting centrally configures one AGPM Server connection for use by all domains and disables the settings on the <strong>AGPM Server</strong> tab for Group Policy administrators.</span></span> <span data-ttu-id="33c0a-111">複数の AGPM サーバーの場合は、既定のサーバーを使用してこの設定を構成した後、 <strong> 管理用テンプレートで AGPM サーバー設定を構成して、 </strong> 他のドメインに対してこのサーバーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="33c0a-111">For multiple AGPM Servers, configure this setting with a default server and then configure the <strong>AGPM Server</strong> setting in the Administrative template to override this server for other domains.</span></span></p>
<p><span data-ttu-id="33c0a-112">無効にした場合、または構成しなかった場合、各グループポリシー管理者は、 <strong> agpm の Agpm サーバータブの各ドメインに対して表示する Agpm サーバーを選択する必要があり </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="33c0a-112">If disabled or not configured, each Group Policy administrator must select the AGPM Server to display for each domain on the <strong>AGPM Server</strong> tab in AGPM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="33c0a-113">AGPM サーバー</span><span class="sxs-lookup"><span data-stu-id="33c0a-113">AGPM Server</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="33c0a-114">この設定を有効にすると、 <strong> 管理テンプレートの Agpm サーバー (すべてのドメイン) の設定を上書きして、複数のドメイン固有の Agpm サーバーを一元的に構成することが </strong> できます。</span><span class="sxs-lookup"><span data-stu-id="33c0a-114">If enabled, this setting centrally configures multiple domain-specific AGPM Servers, overriding the <strong>AGPM Server (all domains)</strong> setting in the Administrative template.</span></span> <span data-ttu-id="33c0a-115">環境に1つの AGPM サーバーのみが必要な場合は、 <strong> 管理用テンプレートの Agpm サーバー (すべてのドメイン) の設定のみを使用し </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="33c0a-115">If your environment requires only a single AGPM Server, use only the <strong>AGPM Server (all domains)</strong> setting in the Administrative template.</span></span></p>
<p><span data-ttu-id="33c0a-116">無効にした場合、または構成しなかった場合は、 <strong> 管理用テンプレートの Agpm サーバー (すべてのドメイン) の設定によって </strong> agpm サーバー接続が構成されます。</span><span class="sxs-lookup"><span data-stu-id="33c0a-116">If disabled or not configured, the <strong>AGPM Server (all domains)</strong> setting in the Administrative template configures the AGPM Server connection.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="33c0a-117">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="33c0a-117">Additional references</span></span>

-   [<span data-ttu-id="33c0a-118">管理用テンプレートの設定</span><span class="sxs-lookup"><span data-stu-id="33c0a-118">Administrative Template Settings</span></span>](administrative-template-settings.md)

-   [<span data-ttu-id="33c0a-119">AGPM 管理者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="33c0a-119">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks.md)

 

 





