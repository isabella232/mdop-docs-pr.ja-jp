---
title: PowerShell コマンドレットを読み込んでコマンドレットのヘルプを取得する方法
description: PowerShell コマンドレットを読み込んでコマンドレットのヘルプを取得する方法
author: dansimp
ms.assetid: 0624495b-943e-485b-9e54-b50e4ee6591c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: 7692d3e36aabc4f3142f664e94d9d71b2cfc1bd3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813955"
---
# PowerShell コマンドレットを読み込んでコマンドレットのヘルプを取得する方法


このトピックについては、次のトピックをご覧ください。

-   [PowerShell コマンドレットを使うための要件](#bkmk-reqs-using-posh)

-   [PowerShell コマンドレットの読み込み](#bkmk-load-cmdlets)

-   [PowerShell コマンドレットのヘルプの表示](#bkmk-get-cmdlet-help)

-   [PowerShell コマンドレットのヘルプの表示](#bkmk-display-help-cmdlet)

## <a href="" id="bkmk-reqs-using-posh"></a>PowerShell コマンドレットを使うための要件


App-v PowerShell コマンドレットを使用するための次の要件を確認します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">要件</th>
<th align="left">詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ユーザーは、次のいずれかの方法を使用して、アクセス権を付与した場合にのみ、App-v Server コマンドレットを実行できます。</p></td>
<td align="left"><ul>
<li><p><strong>App-v Server を展開して構成する場合 </strong> :</p>
<p>Active Directory グループ、または App-v 環境を管理する権限を持つ個々のユーザーを指定します。 「 <a href="how-to-deploy-the-app-v-50-server-50sp3.md" data-raw-source="[How to Deploy the App-V 5.0 Server](how-to-deploy-the-app-v-50-server-50sp3.md)"> App-v 5.0 サーバーを展開する方法」を参照してください </a> 。</p></li>
<li><p><strong>App-v Server を展開した後は、 </strong> 次の手順に従います。</p>
<p>App-v 管理コンソールを使用して、追加の Active Directory グループまたはユーザーを追加します。 <a href="how-to-add-or-remove-an-administrator-by-using-the-management-console.md" data-raw-source="[How to Add or Remove an Administrator by Using the Management Console](how-to-add-or-remove-an-administrator-by-using-the-management-console.md)">管理コンソールを使用して管理者を追加または削除する方法について説明し </a> ます。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>昇格されたコマンドプロンプトを必要とするコマンドレット</p></td>
<td align="left"><ul>
<li><p>Add-AppvClientPackage</p></li>
<li><p>Remove-AppvClientPackage</p></li>
<li><p>Set-AppvClientConfiguration</p></li>
<li><p>Add-AppvClientConnectionGroup</p></li>
<li><p>Remove-AppvClientConnectionGroup</p></li>
<li><p>Add-AppvPublishingServer</p></li>
<li><p>Remove-AppvPublishingServer</p></li>
<li><p>送信-AppvClientReport</p></li>
<li><p>Set-AppvClientMode</p></li>
<li><p>Set-AppvClientPackage</p></li>
<li><p>Set-AppvPublishingServer</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>管理者特権のコマンドプロンプトを要求するように構成していない場合は、エンドユーザーが実行できるコマンドレット</p></td>
<td align="left"><ul>
<li><p>公開-AppvClientPackage</p></li>
<li><p>未発行-AppvClientPackage</p></li>
</ul>
<p>管理者特権でコマンドプロンプトを要求するようにこれらのコマンドレットを構成するには、次のいずれかの方法を使用します。</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">メソッド</th>
<th align="left">その他のリソース</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong> </strong> <strong> -Requirepublishasadmin パラメーターを指定して AppvClientConfiguration コマンドレットを実行し </strong> ます。</p></td>
<td align="left"><ul>
<li><p><a href="how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admin-only-posh-topic-cg" data-raw-source="[How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admin-only-posh-topic-cg)">PowerShell を使用してスタンドアロン コンピューターで接続グループを管理する方法</a></p></li>
<li><p><a href="how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md)">PowerShell を使用してスタンドアロン コンピューターで実行されている App-V 5.0 パッケージを管理する方法</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>App-v クライアントの [管理者として発行する] グループポリシー設定を有効にします。</p></td>
<td align="left"><p><a href="how-to-publish-a-package-by-using-the-management-console-50.md" data-raw-source="[How to Publish a Package by Using the Management Console](how-to-publish-a-package-by-using-the-management-console-50.md)">管理コンソールを使用してパッケージを公開する方法</a> </p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-load-cmdlets"></a>PowerShell コマンドレットの読み込み
PowerShell コマンドレットモジュールを読み込むには、次の操作を行います。

1.  Windows PowerShell または Windows PowerShell Integrated Scripting Environment (ISE) を開きます。

2.  次のいずれかのコマンドを入力して、目的のモジュールのコマンドレットを読み込みます。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-v コンポーネント</th>
<th align="left">入力するコマンド</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v Server</p></td>
<td align="left"><p>インポート-モジュール AppvServer</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v Sequencer</p></td>
<td align="left"><p>インポート-モジュール AppvSequencer</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v クライアント</p></td>
<td align="left"><p>インポート-モジュール AppvClient</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-get-cmdlet-help"></a>PowerShell コマンドレットのヘルプの表示
App-v 5.0 SP3 以降では、コマンドレットのヘルプは次の2つの形式で提供されます。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">形式</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ダウンロード可能なモジュールとして</p></td>
<td align="left"><p>コマンドレットモジュールをダウンロードした後、最新のヘルプをダウンロードするには、次の操作を行います。</p>
<ol>
<li><p>Windows PowerShell または Windows PowerShell Integrated Scripting Environment (ISE) を開きます。</p></li>
<li><p>次のいずれかのコマンドを入力して、目的のモジュールのコマンドレットを読み込みます。</p></li>
</ol>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-v コンポーネント</th>
<th align="left">入力するコマンド</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v Server</p></td>
<td align="left"><p>更新-ヘルプ-モジュール AppvServer</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v Sequencer</p></td>
<td align="left"><p>更新-ヘルプ-モジュール AppvSequencer</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v クライアント</p></td>
<td align="left"><p>更新-ヘルプ-モジュール AppvClient</p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
<tr class="even">
<td align="left"><p>Web ページとしての TechNet の場合</p></td>
<td align="left"><p>「 <a href="https://technet.microsoft.com/library/dn520245.aspx" data-raw-source="[Microsoft Desktop Optimization Pack Automation with Windows PowerShell](https://technet.microsoft.com/library/dn520245.aspx)"> Windows PowerShell での Microsoft デスクトップ最適化パックオートメーション」の下の [App-V] ノードを参照してください </a> 。</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-display-help-cmdlet"></a>PowerShell コマンドレットのヘルプの表示
特定の PowerShell コマンドレットのヘルプを表示するには、次の操作を行います。

1.  Windows PowerShell または Windows PowerShell Integrated Scripting Environment (ISE) を開きます。

2.  「 **Get-ヘルプ** &lt; *」コマンドレット*を入力し &gt; ます。たとえば、「 **AppvClientPackage**」と入力します。

App-v**の提案をお寄せ**ください。 [ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。 App-v**の問題が発生**しましたか? App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

 

 





