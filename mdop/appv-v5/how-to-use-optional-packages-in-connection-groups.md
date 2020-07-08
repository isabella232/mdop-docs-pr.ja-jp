---
title: 接続グループでオプション パッケージを使用する方法
description: 接続グループでオプション パッケージを使用する方法
author: dansimp
ms.assetid: 4d08a81b-55e5-471a-91dc-9a684fb3c9a1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 64a2c0758294bfa617d3d85f888cfce3a2c0d21e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813634"
---
# 接続グループでオプション パッケージを使用する方法


Microsoft Application Virtualization (App-v) 5.0 SP3 以降では、接続グループにオプションのパッケージを追加して、接続グループの管理を簡単にすることができます。 次の表は、オプションのパッケージを使用して作業をより簡単に完了できるタスクをまとめたものです。各タスクの手順へのリンクが用意されています。

**注** 
**省略可能なパッケージは、app-v 5.0 SP3 でのみサポートされます。**

 

オプションのパッケージを使用する前に、「[接続グループでオプションパッケージを使用するための要件](#bkmk-reqs-using-cg)」を参照してください。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">手順へのリンク</th>
<th align="left">タスク</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="#bkmk-apps-plugs-optional" data-raw-source="[Use one connection group, with optional packages, for multiple users who have different packages entitled to them](#bkmk-apps-plugs-optional)">異なるパッケージを持つ複数のユーザーに対して、オプションのパッケージと共に1つの接続グループを使用します。</a></p></td>
<td align="left"><p>単一の接続グループを使用して、さまざまなエンドユーザーが使用できるアプリケーションとプラグインのグループを作成します。</p>
<p>たとえば、すべてのエンドユーザーに Microsoft Office を配布する必要がありますが、さまざまなユーザーのサブセットにさまざまなプラグインを配布します。</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="#bkmk-unpub-del-optl-pkg" data-raw-source="[Unpublish or delete an optional package, or unpublish an optional package and republish it later, without changing the connection group](#bkmk-unpub-del-optl-pkg)">省略可能なパッケージを非公開にする、または削除する、またはオプションのパッケージを公開し、後で再公開する (接続グループを変更しない)</a></p></td>
<td align="left"><p>App-v クライアントで接続グループを無効にしたり、削除したり、追加したり、再度有効にしたりすることなく、省略可能なパッケージを公開、削除、または再公開します。</p>
<p>また、オプションパッケージの発行を停止し、後で再公開することもできます。これにより、接続グループを無効にしたり、再公開する必要はありません。</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-apps-plugs-optional"></a>異なるパッケージを持つ複数のユーザーに対して、オプションのパッケージと共に1つの接続グループを使用する


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">タスクの説明</th>
<th align="left">タスクを実行する方法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>App-v 5.0 SP3</strong></p>
<p>オプションのパッケージを接続グループに追加することができます。これにより、アプリケーションとプラグインのさまざまな組み合わせをさまざまなエンドユーザーに提供できます。</p>
<p><strong>例 </strong> : Microsoft Office をエンドユーザーに配布し、一部のユーザーのみに対して特定のプラグインを有効にします。</p>
<p>これを行うには、Office のパッケージと、Office プラグインを含む別のパッケージを含む接続グループを作成し、プラグインパッケージをオプションにします。</p>
<p>プラグインパッケージに対応していないエンドユーザーは、引き続き Office を実行することができます。</p></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">メソッド</th>
<th align="left">手順</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v Server –管理コンソール</p></td>
<td align="left"><ol>
<li><p>管理コンソールで、[パッケージ] を選択し <strong> </strong> て [パッケージ] ページを開きます。</p></li>
<li><p>[接続グループ] を選択し <strong> </strong> て、接続グループライブラリを表示します。</p></li>
<li><p>接続グループライブラリから適切な接続グループを選択します。</p></li>
<li><p>[ <strong> </strong> 接続されているパッケージ] ウィンドウで [編集] をクリックします。</p></li>
<li><p><strong> </strong> パッケージ名の横にある [オプション] を選択します。</p></li>
<li><p>[ <strong> パッケージアクセスをグループアクセスに追加する] チェックボックスをオンにし </strong> ます。 この必須の手順は、Active Directory グループにパッケージを割り当てたときに、以前に構成したパッケージの権利を接続グループに追加します。</p></li>
</ol></td>
</tr>
<tr class="even">
<td align="left"><p>App-v Server-PowerShell コマンドレット</p></td>
<td align="left"><p>次のコマンドレットを使用して、 <strong> -オプションパラメーターを指定し </strong> ます。</p>
<p><strong>Add-AppvServerConnectionGroupPackage</strong></p>
<p><strong>引数</strong></p>
<p><code>Add-AppvServerConnectionGroupPackage [-AppvServerConnectionGroup] &lt;SerializableConnectionGroup&gt; [[-AppvServerPackage] &lt;PackageVersion&gt;] [-Optional] [-Order &lt;int&gt;] [-UseAnyPackageVersion]</code></p>
<p><strong>例:</strong></p>
<p><code>Add-AppvServerConnectionGroupPackage -Name &quot;Connection Group 1&quot; -PackageName &quot;Package 1&quot; -Optional</code></p></td>
</tr>
<tr class="odd">
<td align="left"><p>スタンドアロンコンピューター上の app-v クライアント</p></td>
<td align="left"><ol>
<li><p>接続グループ XML ドキュメントを作成し、 <strong> Package </strong> tag 属性を <strong> </strong> <strong> "true" に設定します。</strong></p></li>
<li><p>次のコマンドレットを使用して、接続グループを追加して有効にします。</p>
<ul>
<li><p>Add-AppvClientConnectionGroup</p></li>
<li><p>Enable-AppvClientConnectionGroup</p></li>
</ul></li>
</ol>
<p><strong>オプションのパッケージを含む接続グループ XML ドキュメントの例:</strong></p>
<pre class="syntax" space="preserve"><code>&lt;?xml version=&quot;1.0&quot; ?&gt;
&lt;AppConnectionGroup
   xmlns=&quot;<a href="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&amp;quot" data-raw-source="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&amp;quot">https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&quot</a>;
   AppConnectionGroupId=&quot;8105CCD5-244B-4BA1-8888-E321E688D2CB&quot;
   VersionId=&quot;84CE3797-F1CB-4475-A223-757918929EB4&quot;
   DisplayName=&quot;Contoso Software Connection Group&quot; &gt;
&lt;Packages&gt;
&lt;Package
   PackageId=&quot;7735d1a8-5ef9-4df9-a1cf-3aa92ef54fe7&quot;
   VersionId=&quot;ec560d6f-e62e-48eb-a9e5-7c52a8c2e149&quot;
   DisplayName=&quot;Contoso Business Manager&quot;
/&gt;

&lt;Package
   PackageId=&quot;fc6fe0f7-be3d-4643-b37d-fc3f62d4dd5c&quot;
   VersionId=&quot;c67a71cd-3542-4a48-93e8-20c643c50970&quot;
   DisplayName=&quot;Contoso Forms&quot;
   IsOptional=&quot;false&quot;
/&gt;

&lt;Package
   PackageId=&quot;8f6301a5-4348-4039-9560-b27a5bb72711&quot;
   VersionId=&quot;6c694b45-3e19-46c6-a327-d159aa39e1d2&quot;
   DisplayName=&quot;Contoso Tax&quot;
   IsOptional=&quot;true&quot;
/&gt;

&lt;Package
   PackageId=&quot;89d701bc-d507-4299-b6b6-000000003472&quot;
   VersionId=&quot;*&quot;
   DisplayName=&quot;Contoso Accounts&quot;
   IsOptional=&quot;true&quot;
/&gt;

&lt;/Packages&gt;
&lt;/AppConnectionGroup&gt;</code></pre></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>App-v 5.0 SP3 より前のバージョンの場合</strong></p></td>
<td align="left"><p>特定のアプリケーションとプラグインの組み合わせを特定のユーザーが利用できるようにするには、複数の接続グループを作成する必要がありました。</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-unpub-del-optl-pkg"></a>省略可能なパッケージを非公開にする、または削除する、またはオプションのパッケージを公開し、後で再公開する (接続グループを変更しない)


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">タスクの説明</th>
<th align="left">タスクを実行する方法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>App-v 5.0 SP3</strong></p>
<p>接続グループ内の省略可能なパッケージの公開取り消し、削除、または再公開を行うことができます。これは、App-v クライアントで接続グループを無効にするか、再び有効にする必要はありません。</p>
<p>また、オプションのパッケージを非公開にし、後で再公開することもできます。これにより、接続グループを無効にしたり、再公開する必要はありません。</p>
<p><strong>例 </strong> : Microsoft Office プラグインを含むオプションのパッケージを公開し、プラグインを削除したい場合は、接続グループを無効にすることなく、パッケージの発行を取り消すことができます。</p></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">メソッド</th>
<th align="left">手順</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v Server –管理コンソール</p></td>
<td align="left"><ul>
<li><p>パッケージの発行を取り消すには: 管理コンソールで [パッケージの選択] ページを選び <strong> </strong> 、発行を取り消すパッケージを右クリックして、[発行の取り消し] をクリックし <strong> </strong> ます。</p></li>
<li><p>接続グループからオプションのパッケージを削除するには: [ <strong> 接続グループ </strong> ] ページで、削除するパッケージを選択し、右矢印をクリックして、左下の [接続] グループウィンドウからパッケージを削除します。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>スタンドアロンコンピューター上の app-v クライアント</p></td>
<td align="left"><p>次の既存のコマンドレットを使用します。</p>
<ul>
<li><p>未発行-AppvClientPackage</p></li>
<li><p>Remove-AppvClientPackage</p></li>
</ul>
<p>詳細については、「 <a href="how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md)"> PowerShell を使用してスタンドアロンコンピューターで実行されている app-v 5.0 パッケージを管理する方法」を参照してください </a> 。</p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>App-v 5.0 SP3 より前のバージョンの場合</strong></p></td>
<td align="left"><p>次のことを行う必要がありました。</p>
<ol>
<li><p>有効になっている各 App-v クライアントコンピューターから接続グループを削除します。</p></li>
<li><p>パッケージの発行を停止します。</p></li>
<li><p>接続グループの定義からパッケージを削除します。</p></li>
<li><p>接続グループを再公開します。</p></li>
</ol></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-reqs-using-cg"></a>接続グループでオプションのパッケージを使用するための要件


接続グループでオプションのパッケージを使用する前に、次の要件を確認します。

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
<td align="left"><p>接続グループには、オプション以外のパッケージが少なくとも1つ含まれている必要があります。</p></td>
<td align="left"><ul>
<li><p>この要件を満たしていることを確認します。これは、App-v Server と PowerShell コマンドレットで、要件が満たされていることを検証しないことを確認してください。</p></li>
<li><p>1つ以上の省略可能なパッケージが含まれていない接続グループを誤って作成した場合、エンドユーザーがその接続グループでパッケージ化されたアプリケーションを開こうとすると、接続グループは失敗します。</p></li>
</ul>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><ul>
<li><p>ユーザーに公開された接続グループには、グローバルに、またはユーザーに公開されるパッケージを含めることができます。</p></li>
<li><p>グローバルに公開された接続グループには、グローバルに公開されたパッケージのみを含める必要があります</p></li>
</ul></td>
<td align="left"><p>グローバルに公開された接続グループには、接続グループの仮想環境を開始するときにパッケージが利用できるようにするためにグローバルに公開されるパッケージが含まれている必要があります。</p>
<p>ユーザーが公開したパッケージを含むグローバルに公開された接続グループを追加または有効にしようとしても、接続グループは失敗します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>これらのパッケージを含む接続グループを公開する前に、省略可能なすべてのパッケージを公開する必要があります。</p></td>
<td align="left"><p>接続グループの仮想環境は、省略可能なパッケージが見つからない場合は開始できません。</p>
<p>オプション以外のパッケージが公開されていない場合、App-v クライアントは、接続グループの追加または有効化に失敗します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>グローバルに公開されたパッケージを公開する前に、そのコンピューター上のすべてのユーザーに与えられている接続グループが、パッケージを必要としなくなったことを確認します。</p></td>
<td align="left"><p>パッケージが別のユーザーの接続グループの一部であるかどうかは、システムによって確認されません。 グローバルパッケージの発行を解除すると、そのコンピューター上のすべてのユーザーが使用できなくなります。そのため、各ユーザーの接続グループにパッケージが含まれていないことを確認するか、パッケージをオプションにする必要があります。</p></td>
</tr>
</tbody>
</table>

 






## 関連トピック


[接続グループの管理](managing-connection-groups.md)

 

 





