---
title: セルフサービス ポータル ブランドとセッションのタイムアウトを設定する方法
description: セルフサービス ポータル ブランドとセッションのタイムアウトを設定する方法
author: dansimp
ms.assetid: 031eedfc-fade-4d2f-8771-b329e1d38c0d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e222880b2d5557ef15cd7a4efd6421b9972541f4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812531"
---
# <span data-ttu-id="f561d-103">セルフサービス ポータル ブランドとセッションのタイムアウトを設定する方法</span><span class="sxs-lookup"><span data-stu-id="f561d-103">How to Set the Self-Service Portal Branding and Session Time-out</span></span>


<span data-ttu-id="f561d-104">セルフサービスポータルを構成したら、会社名、ヘルプデスクの URL、および "お知らせ" というテキストを表示できます。</span><span class="sxs-lookup"><span data-stu-id="f561d-104">After you configure the Self-Service Portal, you can brand it with your company name, Help Desk URL, and "notice" text.</span></span> <span data-ttu-id="f561d-105">セッションのタイムアウト設定を変更して、指定した非アクティブな期間が経過した後にエンドユーザーのセッションの有効期限が切れるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f561d-105">You can also change the Session Time-out setting to make the end user’s session expire after a specified period of inactivity.</span></span>

**<span data-ttu-id="f561d-106">注</span><span class="sxs-lookup"><span data-stu-id="f561d-106">Note</span></span>**  
<span data-ttu-id="f561d-107">[Windows PowerShell] コマンドレットまたは MBAM サーバー構成ウィザードを使用して、セルフサービスポータルをブランド**化**することもできます。</span><span class="sxs-lookup"><span data-stu-id="f561d-107">You can also brand the Self-Service Portal by using the **Enable-MbamWebApplication** Windows PowerShell cmdlet or the MBAM Server Configuration wizard.</span></span> <span data-ttu-id="f561d-108">ウィザードを使用する手順については、「 [MBAM 2.5 Web アプリケーションを構成する方法](how-to-configure-the-mbam-25-web-applications.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f561d-108">For instructions on using the wizard, see [How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md).</span></span>



**<span data-ttu-id="f561d-109">注</span><span class="sxs-lookup"><span data-stu-id="f561d-109">Note</span></span>**  
<span data-ttu-id="f561d-110">次の手順では、 *selfservice*がセルフサービスポータルの既定の仮想ディレクトリ名です。</span><span class="sxs-lookup"><span data-stu-id="f561d-110">In the following instructions, *SelfService* is the default virtual directory name for the Self-Service Portal.</span></span> <span data-ttu-id="f561d-111">セルフサービスポータルを構成したときに、別の名前が使用されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f561d-111">You might have used a different name when you configured the Self-Service Portal.</span></span>



**<span data-ttu-id="f561d-112">セルフサービスポータルのセッションのタイムアウトとブランドを設定するには</span><span class="sxs-lookup"><span data-stu-id="f561d-112">To set the session time-out and branding for the Self-Service Portal</span></span>**

1.  <span data-ttu-id="f561d-113">エンドユーザーのセッションのタイムアウト期間を設定するには、**インターネットインフォメーションサービスマネージャー**を開始するか、 **inetmgr.exe**を実行します。</span><span class="sxs-lookup"><span data-stu-id="f561d-113">To set the time-out period for the end user’s session, start the **Internet Information Services Manager**, or run **inetmgr.exe**.</span></span>

2.  <span data-ttu-id="f561d-114">Microsoft の**サイト**にアクセスし &gt; **て**、 &gt; **SelfService** &gt; セルフサービスの**ASP.NET**セッションの状態を監視し、 &gt; **Session State**[Cookie の**設定**] の**タイムアウト**値を、エンドユーザーのセルフサービスポータルセッションの有効期限が切れるまでの時間 (分) に変更します。</span><span class="sxs-lookup"><span data-stu-id="f561d-114">Browse to **Sites** &gt; **Microsoft BitLocker Administration and Monitoring** &gt; **SelfService** &gt; **ASP.NET** &gt; **Session State**, and change the **Time-out** value under **Cookie Settings** to the number of minutes after which the end user’s Self-Service Portal session expires.</span></span> <span data-ttu-id="f561d-115">既定値は**5**です。</span><span class="sxs-lookup"><span data-stu-id="f561d-115">The default value is **5**.</span></span> <span data-ttu-id="f561d-116">タイムアウトがないように設定を無効にするには、値を**0**に設定します。</span><span class="sxs-lookup"><span data-stu-id="f561d-116">To disable the setting so that there is no time-out, set the value to **0**.</span></span>

3.  <span data-ttu-id="f561d-117">セルフサービスポータルのブランド項目を設定するには、**インターネットインフォメーションサービスマネージャー**を開始するか、 **inetmgr.exe**を実行します。</span><span class="sxs-lookup"><span data-stu-id="f561d-117">To set the branding items for the Self-Service Portal, start the **Internet Information Services Manager** or run **inetmgr.exe**.</span></span>

4.  <span data-ttu-id="f561d-118">Microsoft の**サイト**を参照 &gt; **して、** &gt; アプリの**セルフサービス**の管理と監視を行い &gt; **Application Settings**ます。</span><span class="sxs-lookup"><span data-stu-id="f561d-118">Browse to **Sites** &gt; **Microsoft BitLocker Administration and Monitoring** &gt; **SelfService** &gt; **Application Settings**.</span></span>

5.  <span data-ttu-id="f561d-119">[**名前**] 列で、変更する項目をクリックし、使用する名前を反映するように既定値を変更します。</span><span class="sxs-lookup"><span data-stu-id="f561d-119">In the **Name** column, select the item that you want to change, and change the default value to reflect the name that you want to use.</span></span> <span data-ttu-id="f561d-120">次の表に、設定できる値を示します。</span><span class="sxs-lookup"><span data-stu-id="f561d-120">The following table lists the values that you can set.</span></span>

    **<span data-ttu-id="f561d-121">注意</span><span class="sxs-lookup"><span data-stu-id="f561d-121">Caution</span></span>**  
    <span data-ttu-id="f561d-122">名前列 (CompanyName \ \*) の値を変更しないようにします。これにより、セルフサービスポータルの動作が停止する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f561d-122">Do not change the value in the Name column (CompanyName\*), as it will cause Self-Service Portal to stop working.</span></span>



~~~
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Name</th>
<th align="left">Default value</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ClientValidationEnabled</p></td>
<td align="left"><p>true</p></td>
</tr>
<tr class="even">
<td align="left"><p>CompanyName</p></td>
<td align="left"><p>Contoso IT</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DisplayNotice</p></td>
<td align="left"><p>true</p></td>
</tr>
<tr class="even">
<td align="left"><p>HelpdeskText</p></td>
<td align="left"><p>Contact Helpdesk or IT Department</p></td>
</tr>
<tr class="odd">
<td align="left"><p>HelpdeskUrl</p></td>
<td align="left"><p>#</p>
<div class="alert">
<strong>Note</strong>  
<p>In MBAM 2.5 SP1, the HelpdeskUrl default value is empty.</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>jQueryPath</p></td>
<td align="left"><p>[//go.microsoft.com/fwlink/?LinkID=390515](//go.microsoft.com/fwlink/?LinkID=390515)</p>
<div class="alert">
<strong>Note</strong>  
<p>In MBAM 2.5 SP1, this has been changed to a local JavaScript file shipped with the product, located at ~/Scripts/jquery-1.10.2.min.js</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>jQueryValidatePath</p></td>
<td align="left"><p>[//go.microsoft.com/fwlink/?LinkID=390516](//go.microsoft.com/fwlink/?LinkID=390516)</p>
<div class="alert">
<strong>Note</strong>  
<p>In MBAM 2.5 SP1, this has been changed to a local JavaScript file shipped with the product, located at ~/Scripts/jquery.validate.min.js</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>jQueryValidateUnobtrusivePath</p></td>
<td align="left"><p>[//go.microsoft.com/fwlink/?LinkID=390517](//go.microsoft.com/fwlink/?LinkID=390517)</p>
<div class="alert">
<strong>Note</strong>  
<p>In MBAM 2.5 SP1, this has been changed to a local JavaScript file shipped with the product, located at ~/Scripts/jquery.validate.unobtrusive.min.js</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>NoticeTextPath</p></td>
<td align="left"><p>Notice.txt</p>
<div class="alert">
<strong>Note</strong>  
<p>You can edit the notice text either by using the Internet Information Services (IIS) Manager or by opening and changing the Notice.txt file in the installation directory.</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>UnobtrusiveJavaScriptEnabled</p></td>
<td align="left"><p>true</p></td>
</tr>
</tbody>
</table>
~~~





## <span data-ttu-id="f561d-123">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f561d-123">Related topics</span></span>


[<span data-ttu-id="f561d-124">組織のセルフサービス ポータルのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="f561d-124">Customizing the Self-Service Portal for Your Organization</span></span>](customizing-the-self-service-portal-for-your-organization.md)



## <span data-ttu-id="f561d-125">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="f561d-125">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="f561d-126">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="f561d-126">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="f561d-127">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="f561d-127">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





