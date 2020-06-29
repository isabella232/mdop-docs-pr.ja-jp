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
# セルフサービス ポータルをブランド化する方法


Microsoft BitLocker 管理と監視 (MBAM) セルフサービスポータルをインストールしたら、自分の会社名、ヘルプデスクの URL、および "お知らせ" のテキストを使ってセルフサービスポータルをブランド化することができます。 また、特定の非アクティブな期間が経過した後にエンドユーザーのセッションの有効期限が切れるように、[セッションタイムアウト] 設定を変更することもできます。

**セルフサービスポータルのセッションのタイムアウトとブランドを設定するには**

1.  エンドユーザーのセッションのタイムアウト期間を設定するには、**インターネットインフォメーションサービスマネージャー**を開始するか、 **inetmgr.exe**を実行します。

2.  Microsoft の**サイト**にアクセス &gt; **し**、 &gt; **SelfService** &gt; セルフサービスの**ASP.NET**セッションの状態を監視して、 &gt; **Session State**[Cookie の**設定**] の**タイムアウト**値を、エンドユーザーのセルフサービスポータルセッションの有効期限が切れるまでの時間 (分) に変更します。 既定値は 5 です。 タイムアウトがないように設定を無効にするには、値を**0**に設定します。

3.  セルフサービスポータルのブランド項目を設定するには、**インターネットインフォメーションサービスマネージャー**を開始するか、 **inetmgr.exe**を実行します。

4.  Microsoft の**サイト**を参照 &gt; **して、** &gt; アプリの**セルフサービス**の管理と監視を行い &gt; **Application Settings**ます。

5.  [**名前**] 列で、変更する項目をクリックし、使用する名前を反映するように既定値を変更します。 次の表に、設定できる値を示します。

    **注意**  
    セルフサービスポータルが動作を停止する原因となるため、名前列 (CompanyName \ *) の値を変更しないでください。



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



## 関連トピック


[MBAM 2.0 サーバー インフラストラクチャの展開](deploying-the-mbam-20-server-infrastructure-mbam-2.md)









