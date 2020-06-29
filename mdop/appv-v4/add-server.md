---
title: ADD SERVER
description: ADD SERVER
author: dansimp
ms.assetid: 4be2ac2e-a410-4711-9f84-f305393c8fa7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e15a5943b40e14b2f9031bf8b3ddffa693e32dea
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819887"
---
# <span data-ttu-id="64b40-103">ADD SERVER</span><span class="sxs-lookup"><span data-stu-id="64b40-103">ADD SERVER</span></span>


<span data-ttu-id="64b40-104">発行サーバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="64b40-104">Adds a publishing server.</span></span>

`SFTMIME ADD SERVER:server-name /HOST hostname /TYPE {HTTP|RTSP}                 /PATH path [/PORT port] [/REFRESH {ON|OFF}] [/SECURE]                 [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="64b40-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="64b40-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="64b40-106">説明</span><span class="sxs-lookup"><span data-stu-id="64b40-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64b40-107">サーバー: &lt; サーバー名&gt;</span><span class="sxs-lookup"><span data-stu-id="64b40-107">SERVER:&lt;server-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="64b40-108">発行サーバーの表示名。</span><span class="sxs-lookup"><span data-stu-id="64b40-108">The display name for the publishing server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64b40-109">/HOST &lt; hostname&gt;</span><span class="sxs-lookup"><span data-stu-id="64b40-109">/HOST &lt;hostname&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="64b40-110">発行サーバーのホスト名または IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="64b40-110">The host name or IP address for the publishing server.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64b40-111">/TYPE {HTTP |RTSP</span><span class="sxs-lookup"><span data-stu-id="64b40-111">/TYPE {HTTP|RTSP}</span></span></p></td>
<td align="left"><p><span data-ttu-id="64b40-112">発行サーバーが Web サーバー (HTTP) であるか、 &quot; &quot; Application Virtualization サーバー (RTSP) であるかを示し &quot; &quot; ます。</span><span class="sxs-lookup"><span data-stu-id="64b40-112">Indicates whether the publishing server is a Web server (&quot;HTTP&quot;) or an Application Virtualization Server (&quot;RTSP&quot;).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64b40-113">/PORT &lt; ポート&gt;</span><span class="sxs-lookup"><span data-stu-id="64b40-113">/PORT &lt;port&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="64b40-114">発行サーバーがリッスンするポート。</span><span class="sxs-lookup"><span data-stu-id="64b40-114">The port on which the publishing server listens.</span></span> <span data-ttu-id="64b40-115">既定では、標準の HTTP サーバーの場合443は80、強化されたセキュリティを使用する場合は554、標準のアプリケーション仮想化サーバーの場合は、強化されたセキュリティを使用しているサーバーの場合は322が使用されます。</span><span class="sxs-lookup"><span data-stu-id="64b40-115">Defaults to 80 for normal HTTP servers, 443 for HTTP servers using enhanced security, 554 for normal Application Virtualization Servers, and 322 for servers using enhanced security.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64b40-116">/PATH &lt; パス&gt;</span><span class="sxs-lookup"><span data-stu-id="64b40-116">/PATH &lt;path&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="64b40-117">発行要求で使用される URL のパス部分です。</span><span class="sxs-lookup"><span data-stu-id="64b40-117">The path portion of the URL used in a publishing request.</span></span> <span data-ttu-id="64b40-118">TYPE パラメーターが RTSP に設定されている場合、パスは省略可能です。既定値は &quot; / &quot; です。</span><span class="sxs-lookup"><span data-stu-id="64b40-118">If the TYPE parameter is set to RTSP, the path is optional and defaults to &quot;/&quot;.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64b40-119">/更新</span><span class="sxs-lookup"><span data-stu-id="64b40-119">/REFRESH</span></span></p></td>
<td align="left"><p><span data-ttu-id="64b40-120">[オン] に設定した場合、ユーザーがログインすると公開情報が更新されます。</span><span class="sxs-lookup"><span data-stu-id="64b40-120">If set to ON, publishing information will be refreshed when the user logs in.</span></span> <span data-ttu-id="64b40-121">既定値はオンです。</span><span class="sxs-lookup"><span data-stu-id="64b40-121">Defaults to ON.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64b40-122">/セキュリティ</span><span class="sxs-lookup"><span data-stu-id="64b40-122">/SECURE</span></span></p></td>
<td align="left"><p><span data-ttu-id="64b40-123">存在する場合は、セキュリティが強化された接続を発行サーバーに対して確立する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="64b40-123">If present, indicates that a connection with enhanced security should be established to the publishing server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64b40-124">/LOG</span><span class="sxs-lookup"><span data-stu-id="64b40-124">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="64b40-125">指定した場合、出力は指定したパス名に記録されます。</span><span class="sxs-lookup"><span data-stu-id="64b40-125">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64b40-126">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="64b40-126">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="64b40-127">指定すると、出力がアクティブなコンソールウィンドウに表示されます (既定)。</span><span class="sxs-lookup"><span data-stu-id="64b40-127">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64b40-128">/GUI</span><span class="sxs-lookup"><span data-stu-id="64b40-128">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="64b40-129">指定すると、Windows のダイアログボックスに出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="64b40-129">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="64b40-130">バージョン4.6 の場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="64b40-130">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64b40-131">/Logu</span><span class="sxs-lookup"><span data-stu-id="64b40-131">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="64b40-132">指定すると、指定したパス名の UNICODE 形式で出力されます。</span><span class="sxs-lookup"><span data-stu-id="64b40-132">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="64b40-133">関連トピック</span><span class="sxs-lookup"><span data-stu-id="64b40-133">Related topics</span></span>


[<span data-ttu-id="64b40-134">SFTMIME コマンドリファレンス</span><span class="sxs-lookup"><span data-stu-id="64b40-134">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





