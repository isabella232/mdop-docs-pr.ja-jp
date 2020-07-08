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
# セルフサービス ポータル ブランドとセッションのタイムアウトを設定する方法


セルフサービスポータルを構成したら、会社名、ヘルプデスクの URL、および "お知らせ" というテキストを表示できます。 セッションのタイムアウト設定を変更して、指定した非アクティブな期間が経過した後にエンドユーザーのセッションの有効期限が切れるようにすることもできます。

**注**  
[Windows PowerShell] コマンドレットまたは MBAM サーバー構成ウィザードを使用して、セルフサービスポータルをブランド**化**することもできます。 ウィザードを使用する手順については、「 [MBAM 2.5 Web アプリケーションを構成する方法](how-to-configure-the-mbam-25-web-applications.md)」を参照してください。



**注**  
次の手順では、 *selfservice*がセルフサービスポータルの既定の仮想ディレクトリ名です。 セルフサービスポータルを構成したときに、別の名前が使用されている可能性があります。



**セルフサービスポータルのセッションのタイムアウトとブランドを設定するには**

1.  エンドユーザーのセッションのタイムアウト期間を設定するには、**インターネットインフォメーションサービスマネージャー**を開始するか、 **inetmgr.exe**を実行します。

2.  Microsoft の**サイト**にアクセスし &gt; **て**、 &gt; **SelfService** &gt; セルフサービスの**ASP.NET**セッションの状態を監視し、 &gt; **Session State**[Cookie の**設定**] の**タイムアウト**値を、エンドユーザーのセルフサービスポータルセッションの有効期限が切れるまでの時間 (分) に変更します。 既定値は**5**です。 タイムアウトがないように設定を無効にするには、値を**0**に設定します。

3.  セルフサービスポータルのブランド項目を設定するには、**インターネットインフォメーションサービスマネージャー**を開始するか、 **inetmgr.exe**を実行します。

4.  Microsoft の**サイト**を参照 &gt; **して、** &gt; アプリの**セルフサービス**の管理と監視を行い &gt; **Application Settings**ます。

5.  [**名前**] 列で、変更する項目をクリックし、使用する名前を反映するように既定値を変更します。 次の表に、設定できる値を示します。

    **注意**  
    名前列 (CompanyName \ *) の値を変更しないようにします。これにより、セルフサービスポータルの動作が停止する可能性があります。



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





## 関連トピック


[組織のセルフサービス ポータルのカスタマイズ](customizing-the-self-service-portal-for-your-organization.md)



## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。 





