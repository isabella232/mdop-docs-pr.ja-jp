---
title: '[展開] タブについて'
description: '[展開] タブについて'
author: dansimp
ms.assetid: 12891798-baa4-45a5-b845-b9505ab95633
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 147e8b1057c789d97087461a585fa3f365089784
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819964"
---
# <span data-ttu-id="8893e-103">[展開] タブについて</span><span class="sxs-lookup"><span data-stu-id="8893e-103">About the Deployment Tab</span></span>


<span data-ttu-id="8893e-104">Application Virtualization Sequencer コンソールの [**展開**] タブを使用して、順序を変更するアプリケーションの情報を変更します。</span><span class="sxs-lookup"><span data-stu-id="8893e-104">Use the **Deployment** tab in the Application Virtualization Sequencer Console to change the information for an application you are about to sequence.</span></span> <span data-ttu-id="8893e-105">このタブには、次の要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8893e-105">This tab contains the following elements.</span></span>

## <span data-ttu-id="8893e-106">サーバーの URL</span><span class="sxs-lookup"><span data-stu-id="8893e-106">Server URL</span></span>


<span data-ttu-id="8893e-107">**サーバー URL**コントロールを使用して、仮想アプリケーションサーバーの構成設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="8893e-107">Use the **Server URL** controls to specify the virtual application server configuration settings.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8893e-108">コントロール</span><span class="sxs-lookup"><span data-stu-id="8893e-108">Control</span></span></th>
<th align="left"><span data-ttu-id="8893e-109">説明</span><span class="sxs-lookup"><span data-stu-id="8893e-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="8893e-110">プロトコル</span><span class="sxs-lookup"><span data-stu-id="8893e-110">Protocol</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="8893e-111">シーケンス付きのアプリケーションパッケージを仮想アプリケーションサーバーからアプリケーション仮想化デスクトップクライアントにストリーミングするプロトコルを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="8893e-111">Enables you to select the protocol that will stream the sequenced application package from a virtual application server to an Application Virtualization Desktop Client.</span></span> <span data-ttu-id="8893e-112">次のプロトコルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8893e-112">The following protocols are available:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="8893e-113">RTSP </strong> : 既定では、リアルタイムストリーミングプロトコルが仮想化対応アプリケーションの交換を制御することを指定します。</span><span class="sxs-lookup"><span data-stu-id="8893e-113">RTSP</strong>—The default, it specifies that the Real-Time Streaming Protocol controls the exchange of virtualization-enabled applications.</span></span></p></li>
<li><p><strong><span data-ttu-id="8893e-114">RTSPS </strong> —トランスポートレイヤーセキュリティ付きのリアルタイムストリーミングプロトコルが、シーケンスされたアプリケーションパッケージの交換を制御することを指定します。</span><span class="sxs-lookup"><span data-stu-id="8893e-114">RTSPS</strong>—Specifies that the Real-Time Streaming Protocol with Transport Layer Security controls the exchange of a sequenced application package.</span></span></p></li>
<li><p><strong><span data-ttu-id="8893e-115">[File </strong> (ファイル) (ファイル): 指定されたアプリケーションをファイル共有からストリーミングすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="8893e-115">File</strong>—Specifies that the sequenced application will be streamed from a file share.</span></span></p></li>
<li><p><strong><span data-ttu-id="8893e-116">HTTPS </strong> : セキュリティで保護されたハイパーテキストトランスポートプロトコルがパッケージの交換を制御することを指定します。</span><span class="sxs-lookup"><span data-stu-id="8893e-116">HTTPS</strong>—Specifies that Secure Hypertext Transport Protocol controls the exchange of a package.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="8893e-117">Hostname]</span><span class="sxs-lookup"><span data-stu-id="8893e-117">Hostname</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="8893e-118">ソフトウェアパッケージをアプリケーションの仮想化デスクトップクライアントにストリーミングする仮想アプリケーションサーバーのグループの前で、仮想アプリケーションサーバーまたはロードバランサーを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="8893e-118">Enables you to select the virtual application server or the load balancer in front of a group of virtual application servers that will stream the software package to an Application Virtualization Desktop Client.</span></span> <span data-ttu-id="8893e-119">シーケンス処理されたアプリケーションパッケージを作成するには、この項目を完了する必要がありますが、既定の% SFT_SOFTGRIDSERVER% 環境変数は、仮想アプリケーションサーバーの実際のホスト名または IP アドレスに変更することができます。</span><span class="sxs-lookup"><span data-stu-id="8893e-119">You must complete this item to create a sequenced application package, but you can change from the default %SFT_SOFTGRIDSERVER% environment variable to the actual hostname or IP address of a virtual application server.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="8893e-120">注</span><span class="sxs-lookup"><span data-stu-id="8893e-120">Note</span></span></strong><br/><p><span data-ttu-id="8893e-121">静的なホスト名または IP アドレスを指定しない場合は、各 Application Virtualization デスクトップクライアントで SFT_SOFTGRIDSERVER という環境変数を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8893e-121">If you choose not to specify a static hostname or IP address, on each Application Virtualization Desktop Client you must set up an environment variable called SFT_SOFTGRIDSERVER.</span></span> <span data-ttu-id="8893e-122">この値は、クライアント&#39;s アプリケーションのソースである仮想アプリケーションサーバーまたはロードバランサーのホスト名または IP アドレスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="8893e-122">Its value must be the hostname or IP address of the virtual application server or load balancer that is this client&#39;s source of applications.</span></span> <span data-ttu-id="8893e-123">この環境変数は、ユーザー変数ではなくシステム変数にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8893e-123">You should make this environment variable a system variable rather than a user variable.</span></span> <span data-ttu-id="8893e-124">この変数の割り当て中にこのコンピューターで実行されている Application Virtualization デスクトップクライアントセッションは、すべて閉じる必要があります。そのため、再開されたセッションで新しいアプリケーションソースが認識されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8893e-124">Any Application Virtualization Desktop Client session that is running on this computer during your assignment of this variable must be closed and then opened so that the resumed session will be aware of its new application source.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="8893e-125">Port</span><span class="sxs-lookup"><span data-stu-id="8893e-125">Port</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="8893e-126">仮想アプリケーションサーバーまたはロードバランサーが、アプリの仮想化デスクトップクライアント&#39;s 要求をリッスンするポートを指定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8893e-126">Enables you to specify the port on which the virtual application server or the load balancer will listen for an Application Virtualization Desktop Client&#39;s request for the package.</span></span> <span data-ttu-id="8893e-127">パッケージを作成するには、この情報が必要ですが、変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="8893e-127">This information is required to create a package, but you can change it.</span></span> <span data-ttu-id="8893e-128">既定のポートは554です。</span><span class="sxs-lookup"><span data-stu-id="8893e-128">The default port is 554.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="8893e-129">パス</span><span class="sxs-lookup"><span data-stu-id="8893e-129">Path</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="8893e-130">ソフトウェアパッケージが保存され、ストリーミングされる仮想アプリケーションサーバー上の相対パスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8893e-130">Enables you to specify the relative path on the virtual application server where the software package is stored and from which it will be streamed.</span></span> <span data-ttu-id="8893e-131">この情報は、SFT ファイルがコンテンツのサブディレクトリに保存されている場合に、パッケージを作成するために必要です。それ以外の場合、この情報は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="8893e-131">This information is required to create a package if the SFT file will be stored in a subdirectory of CONTENT; otherwise, this information is not required.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="8893e-132">オペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="8893e-132">Operating Systems</span></span>


<span data-ttu-id="8893e-133">**オペレーティングシステム**のコントロールを使って、アプリケーションのオペレーティングシステム要件を指定します。</span><span class="sxs-lookup"><span data-stu-id="8893e-133">Use the **Operating Systems** controls to specify the application's operating system requirements.</span></span> <span data-ttu-id="8893e-134">選択されたオペレーティングシステムをサポートできないアプリケーションの仮想化デスクトップクライアントの場合、アプリケーションは起動しません。</span><span class="sxs-lookup"><span data-stu-id="8893e-134">If an Application Virtualization Desktop Client cannot support any of the selected operating systems, the application will not start.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8893e-135">コントロール</span><span class="sxs-lookup"><span data-stu-id="8893e-135">Controls</span></span></th>
<th align="left"><span data-ttu-id="8893e-136">説明</span><span class="sxs-lookup"><span data-stu-id="8893e-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="8893e-137">利用可能なオペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="8893e-137">Available Operating Systems</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="8893e-138">パッケージ内のアプリケーションをサポートできるオペレーティングシステムの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8893e-138">Displays a list of operating systems that can support the applications in the package.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="8893e-139">選択されたオペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="8893e-139">Selected Operating Systems</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="8893e-140">パッケージ内のアプリケーションをサポートする、選択したオペレーティングシステムの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8893e-140">Displays a list of selected operating systems that support the applications in the package.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="8893e-141">出力オプション</span><span class="sxs-lookup"><span data-stu-id="8893e-141">Output Options</span></span>


<span data-ttu-id="8893e-142">[**出力オプション]** コントロールを使用して、インストールするアプリケーションの出力オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="8893e-142">Use the **Output Options** controls to specify the output options for the application to be installed.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8893e-143">コントロール</span><span class="sxs-lookup"><span data-stu-id="8893e-143">Control</span></span></th>
<th align="left"><span data-ttu-id="8893e-144">説明</span><span class="sxs-lookup"><span data-stu-id="8893e-144">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="8893e-145">圧縮アルゴリズム</span><span class="sxs-lookup"><span data-stu-id="8893e-145">Compression Algorithm</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="8893e-146">ネットワーク経由でストリーミングするための SFT ファイルの圧縮方法を選択する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="8893e-146">Use to select the method for compressing the SFT file for streaming across a network.</span></span> <span data-ttu-id="8893e-147">次のいずれかの圧縮方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="8893e-147">Select one of the following compression methods:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="8893e-148">[圧縮済み </strong> : SFT ファイルが ZLIB 形式で圧縮されていることを指定し <a href="https://go.microsoft.com/fwlink/?LinkId=111475" data-raw-source="[ZLIB](https://go.microsoft.com/fwlink/?LinkId=111475)"> </a> ます。</span><span class="sxs-lookup"><span data-stu-id="8893e-148">Compressed</strong>—Specifies that the SFT file be compressed in the <a href="https://go.microsoft.com/fwlink/?LinkId=111475" data-raw-source="[ZLIB](https://go.microsoft.com/fwlink/?LinkId=111475)">ZLIB</a> format.</span></span></p></li>
<li><p><strong><span data-ttu-id="8893e-149">圧縮なし </strong> : 既定では、SFT ファイルが圧縮されないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="8893e-149">Not Compressed</strong>—The default; specifies that the SFT file not be compressed.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="8893e-150">セキュリティ記述子を適用する</span><span class="sxs-lookup"><span data-stu-id="8893e-150">Enforce Security Descriptors</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="8893e-151">クライアントに展開された後に、パッケージ内のアプリケーションのセキュリティ記述子を適用する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="8893e-151">Select to enforce security descriptors of the applications in the package after it is deployed to the client.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="8893e-152">Microsoft Windows Installer (MSI) パッケージを生成する</span><span class="sxs-lookup"><span data-stu-id="8893e-152">Generate Microsoft Windows Installer (MSI) Package</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="8893e-153">Windows Installer でシーケンス付きのアプリケーションパッケージをインストールまたは展開する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="8893e-153">Select to install or deploy a sequenced application package with the Windows Installer.</span></span> <span data-ttu-id="8893e-154">Sequencer を使用して何らかの変更を加えた場合、その変更は Windows インストーラファイルには含まれません。</span><span class="sxs-lookup"><span data-stu-id="8893e-154">If you have made any changes using the sequencer the changes will not be included with the Windows Installer file.</span></span> <span data-ttu-id="8893e-155">Windows Installer ファイルは、ハードディスクに保存されている sft ファイルを使用して、常に作成されます。</span><span class="sxs-lookup"><span data-stu-id="8893e-155">The Windows Installer file will always be created using the .sft file saved on the hard disk.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="8893e-156">関連トピック</span><span class="sxs-lookup"><span data-stu-id="8893e-156">Related topics</span></span>


[<span data-ttu-id="8893e-157">展開のプロパティを変更する方法</span><span class="sxs-lookup"><span data-stu-id="8893e-157">How to Change Deployment Properties</span></span>](how-to-change-deployment-properties.md)

[<span data-ttu-id="8893e-158">Sequencer Console</span><span class="sxs-lookup"><span data-stu-id="8893e-158">Sequencer Console</span></span>](sequencer-console.md)









