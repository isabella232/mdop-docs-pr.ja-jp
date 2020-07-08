---
title: MBAM Web サイトをセキュリティで保護する方法の計画
description: MBAM Web サイトをセキュリティで保護する方法の計画
author: dansimp
ms.assetid: aea1d137-62cf-4da4-9989-541e0b5ad8d8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 223c9397ad7933e11051c289c3dbcab63940fbc5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825024"
---
# MBAM Web サイトをセキュリティで保護する方法の計画


このトピックでは、Microsoft BitLocker の管理と監視 (MBAM) 2.5 の管理と監視を行うための次の方法について説明します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">メソッド</th>
<th align="left">必須または省略可能ですか?</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>証明書を使用して MBAM web サイトを保護する</p></td>
<td align="left"><p>省略可能、強く推奨</p></td>
</tr>
<tr class="even">
<td align="left"><p>アプリケーションプールアカウントのサービスプリンシパル名 (SPN) を登録しています</p></td>
<td align="left"><p>必須かどうか</p></td>
</tr>
</tbody>
</table>



MBAM の展開をセキュリティで保護する方法について詳しくは、「 [mbam 2.5 のセキュリティに関する考慮事項](mbam-25-security-considerations.md)」をご覧ください。

## 証明書を使用して MBAM web サイトを保護する


以下の間の通信をセキュリティで保護するために証明書を使用することをお勧めします。

-   MBAM クライアントと web サービス

-   ブラウザーと、Web サイトとセルフサービスポータル web サイトの管理と監視

証明書の要求とインストールの詳細については、「[インターネットサーバー証明書を構成する](https://technet.microsoft.com/library/cc731977.aspx)」を参照してください。

**注**  
Windows PowerShell を使用している場合にのみ、web サイトと web サービスをさまざまなサーバーで構成できます。 MBAM サーバー構成ウィザードを使って web サイトを構成する場合は、同じサーバー上で web サイトと web サービスを構成する必要があります。



Web サービスとデータベース間の通信をセキュリティで保護するために、SQL Server で暗号化を強制することもお勧めします。 Web サービスと SQL Server の間の通信など、SQL Server へのすべての接続をセキュリティで保護する方法については、「 [Mbam 2.5 セキュリティに関する考慮事項](mbam-25-security-considerations.md#bkmk-secure-databases)」を参照してください。

## アプリケーションプールアカウントの Spn の登録


MBAM サーバーが管理および監視 Web サイトとセルフサービスポータルからの通信を認証できるようにするには、web アプリケーションプールに使用しているドメインアカウントの下で、ホスト名にサービスプリンシパル名 (SPN) を登録する必要があります。

このトピックでは、次の種類のホスト名の Spn を登録する方法について説明します。

-   完全修飾ドメイン名

-   NetBIOS 名

-   仮想名

### 最初の MBAM インストール用に Spn を作成する前に

Spn の作成を開始する前に、次の表の情報を確認してください。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">タスクまたはアイテム</th>
<th align="left">詳細情報</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Active Directory ドメインサービス (AD DS) でサービスアカウントを作成します。</p></td>
<td align="left"><p>サービスアカウントは、MBAM web サイトのセキュリティを確保するために、AD DS で作成するユーザーアカウントです。 MBAM web サイトはアプリケーションプールの下で実行されます。 id はサービスアカウントの名前です。 次に、Spn がアプリケーションプールアカウントに登録されます。</p>
<div class="alert">
<strong>注</strong><br/><p>すべての web サーバーに同じアプリケーションプールアカウントを使用する必要があります。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>IIS/IUSRS グループアカウントまたはアプリケーションプールアカウントに必要な権限が付与されていることを確認します。</p></td>
<td align="left"><p>確認するには、次の手順を実行します。</p>
<ol>
<li><p><strong>ローカルセキュリティポリシーエディターを開き、 </strong> [ローカルポリシー] ノードを展開し <strong> </strong> ます。</p></li>
<li><p>[ <strong> ユーザー権利の割り当て] ノードを選択し、右側の </strong> <strong> ウィンドウで [認証後にクライアントを偽装 </strong> し、 <strong> バッチジョブとしてログオンする] グループポリシー設定をダブルクリックし </strong> ます。</p></li>
</ol></td>
</tr>
<tr class="odd">
<td align="left"><p>ドメイン管理者アカウントを使用して MBAM web サイトを構成した場合、MBAM によって Spn が作成されます。</p></td>
<td align="left"><p>ドメイン管理アカウントを使用して MBAM web サイトを構成する場合は、このトピックの手順に従って、使用しているホスト名の種類に対して手動で Spn を登録します。</p></td>
</tr>
</tbody>
</table>



### 完全修飾ドメインホスト名を使用しているときに Spn を登録する

MBAM を構成するときに完全修飾ドメインホスト名を使用している場合は、次の例に示すように、SPN を1つだけ登録する必要があります。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必要な作業</th>
<th align="left">例と詳細情報</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>完全修飾ドメイン名の SPN を登録します。</p></td>
<td align="left"><p><code>Setspn -s http/mybitlockerrecovery.contoso.com contoso\mbamapppooluser</code></p>
<p>完全修飾ホスト名は <strong> mybitlockerrecovery.contoso.com </strong> であり、web アプリケーションプールに使用されているドメインアカウントは <strong> contoso\mbamapppooluser です </strong> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>アプリケーションプールアカウントに登録する SPN の制約付き委任を構成します。</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=394335" data-raw-source="[Configuring Constrained Delegation](https://go.microsoft.com/fwlink/?LinkId=394335)">制約付き委任の構成</a></p>
<p>この要件は、MBAM 2.5 にのみ適用されます。MBAM 2.5 SP1 では必要ありません。</p></td>
</tr>
</tbody>
</table>



### NetBIOS ホスト名を使用する場合の Spn の登録

MBAM を構成するときに NetBIOS ホスト名を使う場合は、次の例に示すように、NetBIOS 名に1つの SPN を登録し、完全修飾ドメイン名には別の SPN を登録します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必要な作業</th>
<th align="left">例と詳細情報</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>NetBIOS ホスト名の SPN を登録します。</p></td>
<td align="left"><p><code>Setspn -s http/nbname01 contoso\mbamapppooluser</code></p>
<p>NetBIOS のホスト名は <strong> nbname01 </strong> であり、web アプリケーションプールに使用されているドメインアカウントは <strong> contoso\mbamapppooluser です </strong> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>完全修飾ドメイン名の SPN を登録します。</p></td>
<td align="left"><p><code>Setspn –s http/nbname01.corp.contoso.com contoso\mbamapppooluser</code></p>
<p>完全修飾ドメイン名は <strong> nbname01.contoso.com </strong> であり、web アプリケーションプールに使用されているドメインアカウントは <strong> contoso\mbamapppooluser です </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>アプリケーションプールアカウントに登録する Spn の制約付き委任を構成します。</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=394335" data-raw-source="[Configuring Constrained Delegation](https://go.microsoft.com/fwlink/?LinkId=394335)">制約付き委任の構成</a></p>
<p>この要件は、MBAM 2.5 にのみ適用されます。MBAM 2.5 SP1 では必要ありません。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-regvirtualspn"></a>仮想ホスト名を使用するときの Spn の登録

完全修飾ドメイン名である仮想ホスト名で MBAM を構成する場合は、その仮想ホスト名の SPN を1つだけ登録します。 構成する仮想ホスト名が完全修飾ドメイン名ではない場合は、次の例に示すように、完全修飾ドメイン名を指定する2つ目の SPN を作成する必要があります。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必要な作業</th>
<th align="left">例と詳細情報</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>仮想ホスト名が完全修飾ドメイン名の場合、この例では、SPN を1つだけ登録します。</p></td>
<td align="left"><p><code>Setspn -s http/mbamvirtual.contoso.com contoso\mbamapppooluser</code></p>
<p>この例では、仮想ホスト名は <strong> mbamvirtual.contoso.com で </strong> あり、web アプリケーションプールに使用されているドメインアカウントは <strong> contoso\mbamapppooluser です </strong> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>仮想ホスト名が完全修飾ドメイン名ではない場合は、この追加の SPN を登録します。</p></td>
<td align="left"><p><code>Setspn -s http/mbamvirtual contoso\mbamapppooluser</code></p>
<p>この例では、仮想ホスト名は <strong> mbamvirtual </strong> で、web アプリケーションプールに使用されるドメインアカウントは <strong> contoso\mbamapppooluser です </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>仮想ホスト名が完全修飾ドメイン名ではない場合は、この追加の SPN を登録します。</p></td>
<td align="left"><p><code>Setspn -s http/mbamvirtual.contoso.com contoso\mbamapppooluser</code></p>
<p>この例では、仮想ホスト名は <strong> mbamvirtual.contoso.com で </strong> あり、web アプリケーションプールに使用されているドメインアカウントは <strong> contoso\mbamapppooluser です </strong> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ドメインネームサーバー (DNS) サーバーで、カスタムホスト名の "A record" を作成し、web サーバーまたはロードバランサーをポイントします。</p></td>
<td align="left"><p>「DNS ホストレコードを構成する」の「DNS ホスト A レコードを構成する」セクションを参照してください <a href="https://go.microsoft.com/fwlink/?LinkId=394337" data-raw-source="[Configure DNS Host Records](https://go.microsoft.com/fwlink/?LinkId=394337)"> </a> 。</p>
<p>CNAMES の代わりにレコードを使用することをお勧めします。 CNAMES を使ってドメインアドレスを指定している場合は、アプリケーションプールアカウントに web サーバー名の Spn も登録する必要があります。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>アプリケーションプールアカウントに登録する Spn の制約付き委任を構成します。</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=394335" data-raw-source="[Configuring Constrained Delegation](https://go.microsoft.com/fwlink/?LinkId=394335)">制約付き委任の構成</a></p>
<p>この要件は、MBAM 2.5 にのみ適用されます。MBAM 2.5 SP1 では必要ありません。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-registerspn"></a>以前のバージョンの MBAM からアップグレードするときに SPN を登録する

次の場合のみ、このセクションの手順を実行します。

-   以前のバージョンの MBAM からアップグレードします。

-   ロードバランスまたは分散構成で MBAM 2.5 で web サイトを実行します。現在は、読み込みが分散されていない構成で実行されています。

アプリケーションプールアカウントではなく、コンピューターアカウントに既に Spn が登録されている場合、MBAM は既存の Spn を使用し、負荷分散または分散構成で web サイトを構成することはできません。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必要な作業</th>
<th align="left">例と詳細情報</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Active Directory ドメインサービス (AD DS) でアプリケーションプールアカウントを作成します。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>現在インストールされている web サイトと web サービスを削除します。</p></td>
<td align="left"><p><a href="removing-mbam-server-features-or-software.md" data-raw-source="[Removing MBAM Server Features or Software](removing-mbam-server-features-or-software.md)">MBAM サーバーの機能またはソフトウェアの削除</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>コンピューターアカウントから Spn を削除します。</p></td>
<td align="left"><p><code>Setspn –d http/mbamwebserver mbamwebserver</code></p>
<p><code>Setspn –d http/mbamwebserver.contoso.com mbamwebserver</code></p></td>
</tr>
<tr class="even">
<td align="left"><p>アプリケーションプールアカウントに Spn を登録します。</p></td>
<td align="left"><p><a href="#bkmk-regvirtualspn" data-raw-source="[Registering SPNs when you use a virtual host name](#bkmk-regvirtualspn)">仮想ホスト名を使用するときに、spn を登録する手順に従い </a> ます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Web アプリケーションと web サービスを再構成します。</p></td>
<td align="left"><p><a href="how-to-configure-the-mbam-25-web-applications.md" data-raw-source="[How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md)">MBAM 2.5 Web アプリケーションを構成する方法</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>構成に使用する方法に応じて、次のいずれかの操作を行います。</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">方法</th>
<th align="left">詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>MBAM サーバー構成ウィザード</strong></p></td>
<td align="left"><p>[ <strong> Web サービスアプリケーションプールドメインアカウント] フィールドにアプリケーションプールアカウントを入力し </strong> ます。</p></td>
</tr>
<tr class="even">
<td align="left"><p><code>Enable-MbamWebApplication</code> Windows PowerShell コマンドレット</p></td>
<td align="left"><p>パラメーターにアカウントを入力し <code>WebServiceApplicationPoolCredential</code> ます。</p></td>
</tr>
</tbody>
</table>
<p> </p></td>
<td align="left"><div class="alert">
<strong>重要</strong><br/><p>入力するホスト名は、Spn を作成する仮想ホスト名と同じ名前である必要があります。 また、web ファームでは、ホスト名とアプリケーションプールの資格情報が、構成しているすべてのサーバーで同じである必要があります。</p>
</div>
<div>

</div>
<p>MBAM で web アプリケーションを構成する場合は、Spn の登録が試みられますが、この操作は、MBAM をインストールするサーバーのドメイン管理者権限を持っている場合にのみ実行できます。 これらの権利を持っていない場合は、構成を完了することはできますが、MBAM の前後に Spn を設定する必要があります。</p></td>
</tr>
</tbody>
</table>

## 必要な要求のフィルター処理の設定

 アプリケーションが予期したとおりに動作するには、[リストにないファイル名拡張子の許可] が必要です。  この方法については、「Microsoft BitLocker の管理と監視」「> 要求のフィルター処理」を参照してください。 > 編集機能の設定があります。


## 関連トピック


[MBAM 2.5 に対応する環境の準備](preparing-your-environment-for-mbam-25.md)

[MBAM 2.5 展開の前提条件](mbam-25-deployment-prerequisites.md)





## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。



