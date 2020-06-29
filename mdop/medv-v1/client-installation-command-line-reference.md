---
title: クライアント インストールのコマンド ライン リファレンス
description: クライアント インストールのコマンド ライン リファレンス
author: dansimp
ms.assetid: 122a593d-3314-4e9b-858a-08a25ed00c32
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 708daf82699c63dfaa1f99ae595911cf6bad3737
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826727"
---
# <span data-ttu-id="20230-103">クライアント インストールのコマンド ライン リファレンス</span><span class="sxs-lookup"><span data-stu-id="20230-103">Client Installation Command Line Reference</span></span>


**<span data-ttu-id="20230-104">コマンドラインから MED-V をインストールするには</span><span class="sxs-lookup"><span data-stu-id="20230-104">To install MED-V from the command line</span></span>**

1.  <span data-ttu-id="20230-105">コマンドラインで、MED-V パッケージを実行し、次の表で説明されている任意のパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="20230-105">From the command line, run the MED-V .msi package followed by any of the optional parameters described in the following table.</span></span>

2.  <span data-ttu-id="20230-106">MED-V パッケージは*MED-V\_x.msi*と呼ばれます。ここで、 *x*はバージョン番号です。</span><span class="sxs-lookup"><span data-stu-id="20230-106">The MED-V .msi package is called *MED-V\_x.msi*, where *x* is the version number.</span></span>

    <span data-ttu-id="20230-107">たとえば、 *MED-V\_1.0.65.msi*とします。</span><span class="sxs-lookup"><span data-stu-id="20230-107">For example, *MED-V\_1.0.65.msi*.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="20230-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="20230-108">Parameter</span></span></th>
<th align="left"><span data-ttu-id="20230-109">値</span><span class="sxs-lookup"><span data-stu-id="20230-109">Value</span></span></th>
<th align="left"><span data-ttu-id="20230-110">説明</span><span class="sxs-lookup"><span data-stu-id="20230-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="20230-111">/quiet</span><span class="sxs-lookup"><span data-stu-id="20230-111">/quiet</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="20230-112">サイレントインストール</span><span class="sxs-lookup"><span data-stu-id="20230-112">Silent installation</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="20230-113">/log &lt; ログファイルへの完全なパス&gt;</span><span class="sxs-lookup"><span data-stu-id="20230-113">/log &lt;full path to log file&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="20230-114">ログファイルへの完全パス。</span><span class="sxs-lookup"><span data-stu-id="20230-114">The full path to the log file.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="20230-115">INSTALLDIR</span><span class="sxs-lookup"><span data-stu-id="20230-115">INSTALLDIR</span></span></p></td>
<td align="left"><p><span data-ttu-id="20230-116">インストールディレクトリへの完全パス。</span><span class="sxs-lookup"><span data-stu-id="20230-116">The full path to the installation directory.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="20230-117">VMSFOLDER</span><span class="sxs-lookup"><span data-stu-id="20230-117">VMSFOLDER</span></span></p></td>
<td align="left"><p><span data-ttu-id="20230-118">仮想マシンフォルダーへの完全パス。</span><span class="sxs-lookup"><span data-stu-id="20230-118">The full path to the virtual machine folder.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="20230-119">INSTALL_ADMIN_TOOLS</span><span class="sxs-lookup"><span data-stu-id="20230-119">INSTALL_ADMIN_TOOLS</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="20230-120">1, 0</span><span class="sxs-lookup"><span data-stu-id="20230-120">1,0</span></span></strong></p>
<p><span data-ttu-id="20230-121">既定値: <strong> 0</span><span class="sxs-lookup"><span data-stu-id="20230-121">Default: <strong>0</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="20230-122">MED-V 管理ツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="20230-122">Installs MED-V administration tools.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="20230-123">START_AUTOMATICALLY</span><span class="sxs-lookup"><span data-stu-id="20230-123">START_AUTOMATICALLY</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="20230-124">1, 0</span><span class="sxs-lookup"><span data-stu-id="20230-124">1,0</span></span></strong></p>
<p><span data-ttu-id="20230-125">既定値: <strong> 0</span><span class="sxs-lookup"><span data-stu-id="20230-125">Default: <strong>0</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="20230-126">ユーザーが Windows にログオンするたびに、MED-V クライアントが自動的に開始されます。</span><span class="sxs-lookup"><span data-stu-id="20230-126">Automatically starts MED-V client every time the user logs on to Windows.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="20230-127">SERVER_ADDRESS</span><span class="sxs-lookup"><span data-stu-id="20230-127">SERVER_ADDRESS</span></span></p></td>
<td align="left"><p><span data-ttu-id="20230-128">ホスト名または IP</span><span class="sxs-lookup"><span data-stu-id="20230-128">host name or IP</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="20230-129">SERVER_PORT</span><span class="sxs-lookup"><span data-stu-id="20230-129">SERVER_PORT</span></span></p></td>
<td align="left"><p><span data-ttu-id="20230-130">ポート</span><span class="sxs-lookup"><span data-stu-id="20230-130">port</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="20230-131">SERVER_SSL</span><span class="sxs-lookup"><span data-stu-id="20230-131">SERVER_SSL</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="20230-132">1, 0</span><span class="sxs-lookup"><span data-stu-id="20230-132">1,0</span></span></strong></p>
<p><span data-ttu-id="20230-133"><strong>https </strong> または <strong> http の場合</span><span class="sxs-lookup"><span data-stu-id="20230-133">for <strong>https</strong> or <strong>http</span></span></strong></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="20230-134">START_MEDV</span><span class="sxs-lookup"><span data-stu-id="20230-134">START_MEDV</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="20230-135">1, 0</span><span class="sxs-lookup"><span data-stu-id="20230-135">1,0</span></span></strong></p>
<p><span data-ttu-id="20230-136">既定値: <strong> 1</span><span class="sxs-lookup"><span data-stu-id="20230-136">Default: <strong>1</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="20230-137">MED-V のインストール完了時に MED-V を開始します。</span><span class="sxs-lookup"><span data-stu-id="20230-137">Starts MED-V at the completion of the MED-V installation.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="20230-138">注</span><span class="sxs-lookup"><span data-stu-id="20230-138">Note</span></span></strong><br/><p><span data-ttu-id="20230-139">MED-V がシステムによってインストールされている場合は、START_MEDV = 0 を設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="20230-139">It is recommended to set START_MEDV=0 in case MED-V is installed by the system.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="20230-140">DESKTOP_SHORTCUT</span><span class="sxs-lookup"><span data-stu-id="20230-140">DESKTOP_SHORTCUT</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="20230-141">1, 0</span><span class="sxs-lookup"><span data-stu-id="20230-141">1,0</span></span></strong></p>
<p><span data-ttu-id="20230-142">既定値: <strong> 1</span><span class="sxs-lookup"><span data-stu-id="20230-142">Default: <strong>1</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="20230-143">デスクトップに、MED-V クライアントを起動するショートカットを作成します。</span><span class="sxs-lookup"><span data-stu-id="20230-143">Creates a shortcut on the desktop, which starts MED-V client.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="20230-144">MINIMAL_RAM_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="20230-144">MINIMAL_RAM_REQUIRED</span></span></p></td>
<td align="left"><p><span data-ttu-id="20230-145">MB 単位の RAM</span><span class="sxs-lookup"><span data-stu-id="20230-145">RAM in MB</span></span></p></td>
<td align="left"><p><span data-ttu-id="20230-146">MED-V をインストールするときには、コンピューターの RAM の最小容量が指定されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="20230-146">When installing MED-V, checks whether the computer has the minimum amount of RAM specified.</span></span> <span data-ttu-id="20230-147">存在しない場合、インストールは中止されます。</span><span class="sxs-lookup"><span data-stu-id="20230-147">If not, installation is aborted.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="20230-148">SKIP_OS_CHECK</span><span class="sxs-lookup"><span data-stu-id="20230-148">SKIP_OS_CHECK</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="20230-149">1, 0</span><span class="sxs-lookup"><span data-stu-id="20230-149">1,0</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="20230-150">オペレーティングシステムの検証を省略します。</span><span class="sxs-lookup"><span data-stu-id="20230-150">Omits the operating system validation.</span></span></p></td>
</tr>
</tbody>
</table>











