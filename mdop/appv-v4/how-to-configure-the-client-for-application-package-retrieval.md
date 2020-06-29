---
title: アプリケーション パッケージを取得するためにクライアントを構成する方法
description: アプリケーション パッケージを取得するためにクライアントを構成する方法
author: dansimp
ms.assetid: 891f2739-da7a-46da-b452-b8c0af075525
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f5eeb0b977c6ecd44947d5d1c42d25d47b9e2530
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817827"
---
# <span data-ttu-id="51443-103">アプリケーション パッケージを取得するためにクライアントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="51443-103">How to Configure the Client for Application Package Retrieval</span></span>


<span data-ttu-id="51443-104">クライアントが Application Virtualization (App-v) Management サーバーを公開サーバーとして構成されている場合、既定では、クライアントは、ユーザーが使用を許可されている各パッケージのオープンソフトウェア記述子 (OSD) とパッケージマニフェストファイルをサーバーから取得します。</span><span class="sxs-lookup"><span data-stu-id="51443-104">When the client is configured with an Application Virtualization (App-V) Management Server as its publishing server, by default at the next publishing refresh cycle, the client retrieves from the server the Open Software Descriptor (OSD) and package manifest files for each package that the user is authorized to use.</span></span> <span data-ttu-id="51443-105">クライアントは、これらのファイルで定義されているパッケージソース情報を使用して、パッケージコンテンツ、アイコン、ファイルの種類の関連付けを検索する場所を決定します。</span><span class="sxs-lookup"><span data-stu-id="51443-105">The client uses the package source information that is defined in these files to determine where to find the package content, icons, and file type associations.</span></span>

<span data-ttu-id="51443-106">クライアントがローカルの App-v ストリーミングサーバーまたは Web サーバーやファイルサーバーなどの別の代替ソースからパッケージコンテンツ (SFT ファイル) を取得する場合は、他のサーバー上のローカルコンテンツ共有をポイントするように、コンピューター上の ApplicationSourceRoot レジストリキーの値を構成できます ()。</span><span class="sxs-lookup"><span data-stu-id="51443-106">If you want the client to obtain the package content (SFT file) from a local App-V Streaming Server or other alternate source such as a Web server or file server, instead of from the App-V Management Server, you can configure the ApplicationSourceRoot registry key value on the computer to point to the local content share on the other server.</span></span> <span data-ttu-id="51443-107">OSD ファイルでは、パッケージコンテンツの元のソースパスもそのまま定義されています。</span><span class="sxs-lookup"><span data-stu-id="51443-107">The OSD file still defines the original source path for the package content.</span></span> <span data-ttu-id="51443-108">ただし、クライアントは、OSD ファイルのコンテンツパスで指定されているサーバーと共有の代わりに、ApplicationSourceRoot 設定の値を使います。</span><span class="sxs-lookup"><span data-stu-id="51443-108">However the client uses the value of the ApplicationSourceRoot setting in place of the server and share that are specified in the content path in the OSD file.</span></span> <span data-ttu-id="51443-109">これにより、クライアントが他のサーバーからコンテンツを取得するようにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="51443-109">This redirects the client to retrieve the content from the other server.</span></span>

<span data-ttu-id="51443-110">また、パッケージマニフェストファイルまたは発行サーバーによって送信されるパスでこれらの設定を上書きする場合は、OSDSourceRoot と IconSourceRoot レジストリキーの値を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="51443-110">You can also configure the OSDSourceRoot and IconSourceRoot registry key values if you want to override those settings in the package manifest file or in the paths sent by a publishing server.</span></span> <span data-ttu-id="51443-111">OSDSourceRoot は、公開時にアプリケーションパッケージの OSD ファイル取得のソースの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="51443-111">The OSDSourceRoot specifies a source location for OSD file retrieval for an application package during publication.</span></span> <span data-ttu-id="51443-112">IconSourceRoot は、公開時にアプリケーションパッケージのアイコンを取得するためのソースの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="51443-112">The IconSourceRoot specifies a source location for icon retrieval for an application package during publication.</span></span>

**<span data-ttu-id="51443-113">注</span><span class="sxs-lookup"><span data-stu-id="51443-113">Note</span></span>**  
-   <span data-ttu-id="51443-114">IconSourceRoot と OSDSourceRoot 設定は、パッケージマニフェストファイル内の値を上書きするため、Windows Installer (.msi) ファイルメソッドを使ってパッケージを展開しようとすると、パッケージマニフェストファイル内の値は、その .msi ファイル内に含まれている値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="51443-114">The IconSourceRoot and OSDSourceRoot settings override the values in the package manifest file, so if you try to deploy a package by using the Windows Installer (.msi) file method, it will also override the values in the package manifest file that is contained within that .msi file.</span></span>

-   <span data-ttu-id="51443-115">Publishing および HTTP (S) ストリーミング操作の両方で、App-v 4.5 SP1 クライアントは、ユーザーのコンピューターの Internet Explorer で構成されているプロキシサーバー設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="51443-115">During both the publishing and HTTP(S) streaming operations,App-V 4.5 SP1 clients use the proxy server settings that are configured in Internet Explorer on the user’s computer.</span></span>



**<span data-ttu-id="51443-116">ApplicationSourceRoot レジストリキー値を構成するには</span><span class="sxs-lookup"><span data-stu-id="51443-116">To configure the ApplicationSourceRoot registry key value</span></span>**

-   <span data-ttu-id="51443-117">UNC パスまたは URL のいずれかを使用して、次のレジストリキー値の ApplicationSourceRoot を構成します。</span><span class="sxs-lookup"><span data-stu-id="51443-117">Configure the ApplicationSourceRoot in the following registry key value with either a UNC path or a URL:</span></span>

    <span data-ttu-id="51443-118">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\ApplicationSourceRoot</span><span class="sxs-lookup"><span data-stu-id="51443-118">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\ApplicationSourceRoot</span></span>

    <span data-ttu-id="51443-119">汎用名前付け規則 (UNC) パスの正しい形式は、 **\\\\computername\\sharefolder\\\ [folder \] \ [\ \]**(**フォルダー**は省略可能) です。</span><span class="sxs-lookup"><span data-stu-id="51443-119">The correct format for the Universal Naming Convention (UNC) path is **\\\\computername\\sharefolder\\\[folder\]\[\\\]**, where **folder** is optional.</span></span> <span data-ttu-id="51443-120">**Computername**には完全修飾ドメイン名 (FQDN) または IP アドレスを使用できます。また、**フォルダー**名にはドライブ文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="51443-120">The **computername** can be a Fully Qualified Domain Name (FQDN) or an IP address, and **sharefolder** can be a drive letter.</span></span> <span data-ttu-id="51443-121">OSD パスの**\\\\computername\\sharedfolder**または drive 文字の部分のみが置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="51443-121">Only the **\\\\computername\\sharedfolder** or drive letter portion of the OSD path is replaced.</span></span>

    <span data-ttu-id="51443-122">URL パスの正しい形式は**protocol://servername: \ [port \] \ [/path\] \ [/\]**。ここで、**ポート**と**パス**は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="51443-122">The correct format for the URL path is **protocol://servername:\[port\]\[/path\]\[/\]**, where **port** and **path** are optional.</span></span> <span data-ttu-id="51443-123">**Port**が指定されていない場合は、プロトコルの既定のポートが使用されます。</span><span class="sxs-lookup"><span data-stu-id="51443-123">If **port** is not specified, the default port for the protocol is used.</span></span> <span data-ttu-id="51443-124">OSD URL の**protocol:/server: port**部分のみが置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="51443-124">Only the **protocol://server:port** portion of the OSD URL is replaced.</span></span>

    **<span data-ttu-id="51443-125">重要</span><span class="sxs-lookup"><span data-stu-id="51443-125">Important</span></span>**  
    <span data-ttu-id="51443-126">ApplicationSourceRoot 定義では、環境変数はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="51443-126">Environment variables are not supported in the ApplicationSourceRoot definition.</span></span>



~~~
The following table lists examples of acceptable URL and UNC path formats.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ApplicationSourceRoot</th>
<th align="left">OSD File HREF Path</th>
<th align="left">Result</th>
<th align="left">Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>rtsps://mainserver:322</p></td>
<td align="left"><p>rtsp://appserver/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>rtsps://mainserver:322/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>rtsps://mainserver:322/prodapps</p></td>
<td align="left"><p>rtsp://appserver/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>rtsps://mainserver:322/prodapps/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>https://mainserver:443/prodapps</p></td>
<td align="left"><p>rtsp://appserver/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>https://mainserver:443/prodapps/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>rtsps://mainserver:322/prodapps</p></td>
<td align="left"><p>rtsp://%SFT_APPVSERVER%:554/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>rtsps://mainserver:322/prodapps/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>rtsps://mainserver:322</p></td>
<td align="left"><p>\\uncserver\share\productivity\office2k3.sft</p></td>
<td align="left"><p>rtsps://mainserver:322/productivity/office2k3.sft</p></td>
<td align="left"><p>‘\’ converted to ‘/’</p></td>
</tr>
<tr class="even">
<td align="left"><p>rtsps://mainserver:322</p></td>
<td align="left"><p>file://\\uncserver\share\productivity\office2k3.sft</p></td>
<td align="left"><p>rtsps://mainserver:322/productivity/office2k3.sft</p></td>
<td align="left"><p>‘\’ converted to ‘/’</p></td>
</tr>
<tr class="odd">
<td align="left"><p>\\uncserver\share</p></td>
<td align="left"><p>rtsp://appserver/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>\\uncserver\share\productivity\office2k3.sft</p></td>
<td align="left"><p>‘/’ converted to ‘\’ and parameter dropped when converting to UNC path</p></td>
</tr>
<tr class="even">
<td align="left"><p>\\uncserver\share\prodapps</p></td>
<td align="left"><p>rtsp://appserver/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>\\uncserver\share\prodapps\productivity\office2k3.sft</p></td>
<td align="left"><p>‘/’ converted to ‘\’ and parameter dropped when converting to UNC path</p></td>
</tr>
<tr class="odd">
<td align="left"><p>M:</p></td>
<td align="left"><p>\\uncserver\share\productivity\office2k3.sft</p></td>
<td align="left"><p>M:\productivity\office2k3.sft</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>M:\prodapps</p></td>
<td align="left"><p>\\uncserver\share\productivity\office2k3.sft</p></td>
<td align="left"><p>M:\prodapps\productivity\office2k3.sft</p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>
~~~



**<span data-ttu-id="51443-127">OSDSourceRoot 値を構成するには</span><span class="sxs-lookup"><span data-stu-id="51443-127">To configure the OSDSourceRoot value</span></span>**

-   <span data-ttu-id="51443-128">次のレジストリキー値で、[UNC パスまたは URL を使用して OSDSourceRoot を構成します。</span><span class="sxs-lookup"><span data-stu-id="51443-128">Configure the OSDSourceRoot in the following registry key value with either a UNC path or a URL:</span></span>

    <span data-ttu-id="51443-129">HKEY \ _LOCAL \ _MACHINE ¥ $ ¥¥ \ softgrid¥ 5 \ # # # ¥¥5</span><span class="sxs-lookup"><span data-stu-id="51443-129">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\OSDSourceRoot</span></span>

    <span data-ttu-id="51443-130">次の例のように、OSDSourceRoot に使用できる形式には、UNC パスと Url が含まれます。</span><span class="sxs-lookup"><span data-stu-id="51443-130">Acceptable formats for the OSDSourceRoot include UNC paths and URLs, as in the following example:</span></span>

    <span data-ttu-id="51443-131">**\\\\computername\\sharefolder\\resource**または**\\\\computername\\content**または\*\* &lt; drive &gt; : \\ foldername\*\*</span><span class="sxs-lookup"><span data-stu-id="51443-131">**\\\\computername\\sharefolder\\resource** or **\\\\computername\\content** or **&lt;drive&gt;:\\foldername**</span></span>

    <span data-ttu-id="51443-132">**http://computername/productivity/**/**https://computername/productivity/**</span><span class="sxs-lookup"><span data-stu-id="51443-132">**http://computername/productivity/** or **https://computername/productivity/**</span></span>

**<span data-ttu-id="51443-133">IconSourceRoot 値を構成するには</span><span class="sxs-lookup"><span data-stu-id="51443-133">To configure the IconSourceRoot value</span></span>**

-   <span data-ttu-id="51443-134">UNC パスまたは URL のいずれかを使用して、次のレジストリキー値の IconSourceRoot を構成します。</span><span class="sxs-lookup"><span data-stu-id="51443-134">Configure the IconSourceRoot in the following registry key value with either a UNC path or a URL:</span></span>

    <span data-ttu-id="51443-135">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\IconSourceRoot</span><span class="sxs-lookup"><span data-stu-id="51443-135">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\IconSourceRoot</span></span>

    <span data-ttu-id="51443-136">IconSourceRoot の受け付け可能な形式には、次の例のように UNC パスと Url が含まれます。</span><span class="sxs-lookup"><span data-stu-id="51443-136">Acceptable formats for the IconSourceRoot include UNC paths and URLs, as in the following example:</span></span>

    <span data-ttu-id="51443-137">**\\\\computername\\sharefolder\\resource**または**\\\\computername\\content**または\*\* &lt; drive &gt; : \\ foldername\*\*</span><span class="sxs-lookup"><span data-stu-id="51443-137">**\\\\computername\\sharefolder\\resource** or **\\\\computername\\content** or **&lt;drive&gt;:\\foldername**</span></span>

    <span data-ttu-id="51443-138">**http://computername/productivity/**/**https://computername/productivity/**</span><span class="sxs-lookup"><span data-stu-id="51443-138">**http://computername/productivity/** or **https://computername/productivity/**</span></span>

## <span data-ttu-id="51443-139">関連トピック</span><span class="sxs-lookup"><span data-stu-id="51443-139">Related topics</span></span>


[<span data-ttu-id="51443-140">コマンド ラインを使用して App-V Client レジストリ設定を構成する方法</span><span class="sxs-lookup"><span data-stu-id="51443-140">How to Configure the App-V Client Registry Settings by Using the Command Line</span></span>](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)









