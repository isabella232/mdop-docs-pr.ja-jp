---
title: セルフサービス ポータルをブランド化する方法
description: セルフサービス ポータルをブランド化する方法
author: dansimp
ms.assetid: 3ef9e951-7c42-4f7f-b131-3765d39b3207
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fe4f4efc5852042671711ba5780cc78055957ba8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825147"
---
# <span data-ttu-id="ecb5a-103">セルフサービス ポータルをブランド化する方法</span><span class="sxs-lookup"><span data-stu-id="ecb5a-103">How to Brand the Self-Service Portal</span></span>


<span data-ttu-id="ecb5a-104">Microsoft BitLocker 管理と監視 (MBAM) セルフサービスポータルをインストールしたら、自分の会社名、ヘルプデスクの URL、および "お知らせ" のテキストを使ってセルフサービスポータルをブランド化することができます。</span><span class="sxs-lookup"><span data-stu-id="ecb5a-104">After you install the Microsoft BitLocker Administration and Monitoring (MBAM) Self-Service Portal, you can brand the Self-Service Portal with your company name, Help Desk URL, and “notice” text.</span></span> <span data-ttu-id="ecb5a-105">また、特定の非アクティブな期間が経過した後にエンドユーザーのセッションの有効期限が切れるように、[セッションタイムアウト] 設定を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="ecb5a-105">You can also change the Session Timeout setting to make the end user’s session expire after a specified period of inactivity.</span></span>

**<span data-ttu-id="ecb5a-106">セルフサービスポータルのセッションのタイムアウトとブランドを設定するには</span><span class="sxs-lookup"><span data-stu-id="ecb5a-106">To set the session time-out and branding for the Self-Service Portal</span></span>**

1.  <span data-ttu-id="ecb5a-107">エンドユーザーのセッションのタイムアウト期間を設定するには、**インターネットインフォメーションサービスマネージャー**を開始するか、 **inetmgr.exe**を実行します。</span><span class="sxs-lookup"><span data-stu-id="ecb5a-107">To set the time-out period for the end user’s session, start the **Internet Information Services Manager**, or run **inetmgr.exe**.</span></span>

2.  <span data-ttu-id="ecb5a-108">Microsoft の**サイト**にアクセス &gt; **し**、 &gt; **SelfService** &gt; セルフサービスの**ASP.NET**セッションの状態を監視して、 &gt; **Session State**[Cookie の**設定**] の**タイムアウト**値を、エンドユーザーのセルフサービスポータルセッションの有効期限が切れるまでの時間 (分) に変更します。</span><span class="sxs-lookup"><span data-stu-id="ecb5a-108">Browse to **Sites** &gt; **Microsoft BitLocker Administration and Monitoring** &gt; **SelfService** &gt; **ASP.NET** &gt; **Session State**, and change the **Time-out** value under **Cookie Settings** to the number of minutes after which the end user’s Self-Service Portal session will expire.</span></span> <span data-ttu-id="ecb5a-109">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="ecb5a-109">The default is 5.</span></span> <span data-ttu-id="ecb5a-110">タイムアウトがないように設定を無効にするには、値を**0**に設定します。</span><span class="sxs-lookup"><span data-stu-id="ecb5a-110">To disable the setting so that there is no time-out, set the value to **0**.</span></span>

3.  <span data-ttu-id="ecb5a-111">セルフサービスポータルのブランド項目を設定するには、**インターネットインフォメーションサービスマネージャー**を開始するか、 **inetmgr.exe**を実行します。</span><span class="sxs-lookup"><span data-stu-id="ecb5a-111">To set the branding items for the Self-Service Portal, start the **Internet Information Services Manager**, or run **inetmgr.exe**.</span></span>

4.  <span data-ttu-id="ecb5a-112">Microsoft の**サイト**を参照 &gt; **して、** &gt; アプリの**セルフサービス**の管理と監視を行い &gt; **Application Settings**ます。</span><span class="sxs-lookup"><span data-stu-id="ecb5a-112">Browse to **Sites** &gt; **Microsoft BitLocker Administration and Monitoring** &gt; **SelfService** &gt; **Application Settings**.</span></span>

5.  <span data-ttu-id="ecb5a-113">[**名前**] 列で、変更する項目をクリックし、使用する名前を反映するように既定値を変更します。</span><span class="sxs-lookup"><span data-stu-id="ecb5a-113">From the **Name** column, select the item that you want to change, and change the default value to reflect the name that you want to use.</span></span> <span data-ttu-id="ecb5a-114">次の表に、設定できる値を示します。</span><span class="sxs-lookup"><span data-stu-id="ecb5a-114">The following table lists the values that you can set.</span></span>

    **<span data-ttu-id="ecb5a-115">注意</span><span class="sxs-lookup"><span data-stu-id="ecb5a-115">Caution</span></span>**  
    <span data-ttu-id="ecb5a-116">セルフサービスポータルが動作を停止する原因となるため、名前列 (CompanyName \ \*) の値を変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="ecb5a-116">Do not change the value in the Name column (CompanyName\*), as it will cause the Self-Service Portal to stop working.</span></span>



~~~
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Name</th>
<th align="left">Default Value</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>CompanyName*</p></td>
<td align="left"><p>Contoso IT</p></td>
</tr>
<tr class="even">
<td align="left"><p>HelpdeskText*</p></td>
<td align="left"><p>Contact Help Desk or IT Department</p></td>
</tr>
<tr class="odd">
<td align="left"><p>HelpdeskUrl*</p></td>
<td align="left"><p>Http://www.microsoft.com</p></td>
</tr>
<tr class="even">
<td align="left"><p>jQueryPath</p></td>
<td align="left"><p>//ajax.aspnetcdn.com/ajax/jQuery/jquery-1.7.2.min.js</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MicrosoftAjaxPath</p></td>
<td align="left"><p>//ajax.aspnetcdn.com/ajax/3.5/MicrosoftAjax.js</p></td>
</tr>
<tr class="even">
<td align="left"><p>MicrosoftMvcAjaxPath</p></td>
<td align="left"><p>//ajax.aspnetcdn.com/ajax/mvc/2.0/MicrosoftMvcValidation.js</p></td>
</tr>
<tr class="odd">
<td align="left"><p>NoticeTextPath</p></td>
<td align="left"><p>Notice.txt</p>
<div class="alert">
<strong>Note</strong>  
<p>You can edit the Notice text either by using the IIS Manager or by opening and changing the Notice.txt file in the installation directory.</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>
~~~



## <span data-ttu-id="ecb5a-117">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ecb5a-117">Related topics</span></span>


[<span data-ttu-id="ecb5a-118">MBAM 2.0 サーバー インフラストラクチャの展開</span><span class="sxs-lookup"><span data-stu-id="ecb5a-118">Deploying the MBAM 2.0 Server Infrastructure</span></span>](deploying-the-mbam-20-server-infrastructure-mbam-2.md)









