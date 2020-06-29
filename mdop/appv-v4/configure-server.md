---
title: CONFIGURE SERVER
description: CONFIGURE SERVER
author: dansimp
ms.assetid: c916eddd-74f2-46e4-953d-120b23284e37
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7757f281ec57645d20367056ba0013ef476a91a1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821974"
---
# <span data-ttu-id="a363c-103">CONFIGURE SERVER</span><span class="sxs-lookup"><span data-stu-id="a363c-103">CONFIGURE SERVER</span></span>


<span data-ttu-id="a363c-104">ユーザーがサーバーのセットアップを変更できるようにします。指定されていない設定は変更されません。</span><span class="sxs-lookup"><span data-stu-id="a363c-104">Enables a user to change the setup of a server; any settings not specified will not be modified.</span></span>

`SFTMIME CONFIGURE SERVER:server-name [/NAME display-name] [/HOST hostname]                 [/PORT port] [/PATH path] [/TYPE {HTTP|RTSP}]                 [/REFRESH {ON|OFF}] [/SECURE]                 [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a363c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a363c-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="a363c-106">説明</span><span class="sxs-lookup"><span data-stu-id="a363c-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a363c-107">サーバー: &lt; サーバー名&gt;</span><span class="sxs-lookup"><span data-stu-id="a363c-107">SERVER:&lt;server-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="a363c-108">発行サーバーの表示名。</span><span class="sxs-lookup"><span data-stu-id="a363c-108">The display name for the publishing server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a363c-109">/NAME &lt; 表示名&gt;</span><span class="sxs-lookup"><span data-stu-id="a363c-109">/NAME &lt;display-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="a363c-110">サーバーの新しい表示名。</span><span class="sxs-lookup"><span data-stu-id="a363c-110">New display name for the server.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a363c-111">/HOST &lt; hostname&gt;</span><span class="sxs-lookup"><span data-stu-id="a363c-111">/HOST &lt;hostname&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="a363c-112">発行サーバーのホスト名または IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="a363c-112">The host name or IP address for the publishing server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a363c-113">/PORT &lt; ポート&gt;</span><span class="sxs-lookup"><span data-stu-id="a363c-113">/PORT &lt;port&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="a363c-114">発行サーバーがリッスンするポート。</span><span class="sxs-lookup"><span data-stu-id="a363c-114">The port on which the publishing server listens.</span></span> <span data-ttu-id="a363c-115">既定では、標準の HTTP サーバーの場合443は80、強化されたセキュリティを使用する場合は554、標準のアプリケーション仮想化サーバーの場合は、強化されたセキュリティを使用しているサーバーの場合は322が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a363c-115">Defaults to 80 for normal HTTP servers, 443 for HTTP servers using enhanced security, 554 for normal Application Virtualization Servers, and 322 for servers using enhanced security.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a363c-116">/PATH &lt; パス&gt;</span><span class="sxs-lookup"><span data-stu-id="a363c-116">/PATH &lt;path&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="a363c-117">発行要求で使用される URL のパス部分です。</span><span class="sxs-lookup"><span data-stu-id="a363c-117">The path portion of the URL used in a publishing request.</span></span> <span data-ttu-id="a363c-118">TYPE パラメーターが RTSP に設定されている場合、パスは省略可能です。既定値は &quot; / &quot; です。</span><span class="sxs-lookup"><span data-stu-id="a363c-118">If the TYPE parameter is set to RTSP, the path is optional and defaults to &quot;/&quot;.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a363c-119">/TYPE</span><span class="sxs-lookup"><span data-stu-id="a363c-119">/TYPE</span></span></p></td>
<td align="left"><p><span data-ttu-id="a363c-120">発行サーバーが Web サーバー (HTTP) であるか、 &quot; &quot; Application Virtualization サーバー (RTSP) であるかを示し &quot; &quot; ます。</span><span class="sxs-lookup"><span data-stu-id="a363c-120">Indicates whether the publishing server is a Web server (&quot;HTTP&quot;) or an Application Virtualization Server (&quot;RTSP&quot;).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a363c-121">/更新</span><span class="sxs-lookup"><span data-stu-id="a363c-121">/REFRESH</span></span></p></td>
<td align="left"><p><span data-ttu-id="a363c-122">[オン] に設定した場合、ユーザーがログインすると公開情報が更新されます。</span><span class="sxs-lookup"><span data-stu-id="a363c-122">If set to ON, publishing information will be refreshed when the user logs in.</span></span> <span data-ttu-id="a363c-123">既定値はオンです。</span><span class="sxs-lookup"><span data-stu-id="a363c-123">Defaults to ON.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a363c-124">/セキュリティ</span><span class="sxs-lookup"><span data-stu-id="a363c-124">/SECURE</span></span></p></td>
<td align="left"><p><span data-ttu-id="a363c-125">存在する場合は、セキュリティが強化された接続を発行サーバーに対して確立する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="a363c-125">If present, indicates that a connection with enhanced security should be established to the publishing server.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a363c-126">/LOG</span><span class="sxs-lookup"><span data-stu-id="a363c-126">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="a363c-127">指定した場合、出力は指定したパス名に記録されます。</span><span class="sxs-lookup"><span data-stu-id="a363c-127">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a363c-128">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="a363c-128">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="a363c-129">指定すると、出力がアクティブなコンソールウィンドウに表示されます (既定)。</span><span class="sxs-lookup"><span data-stu-id="a363c-129">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a363c-130">/GUI</span><span class="sxs-lookup"><span data-stu-id="a363c-130">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="a363c-131">指定すると、Windows のダイアログボックスに出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a363c-131">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="a363c-132">バージョン4.6 の場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="a363c-132">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a363c-133">/Logu</span><span class="sxs-lookup"><span data-stu-id="a363c-133">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="a363c-134">指定すると、指定したパス名の UNICODE 形式で出力されます。</span><span class="sxs-lookup"><span data-stu-id="a363c-134">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="a363c-135">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a363c-135">Related topics</span></span>


[<span data-ttu-id="a363c-136">SFTMIME コマンドリファレンス</span><span class="sxs-lookup"><span data-stu-id="a363c-136">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





