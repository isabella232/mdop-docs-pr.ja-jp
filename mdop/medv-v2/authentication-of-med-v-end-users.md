---
title: MED-V エンド ユーザーの認証
description: MED-V エンド ユーザーの認証
author: dansimp
ms.assetid: aaf96eb6-91d1-4f4d-9854-5fc73c7ae7ab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 14c1e95a94f2da76b6b6c5ebd9d4cf14dcf839a7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824887"
---
# MED-V エンド ユーザーの認証


Microsoft Enterprise デスクトップ仮想化 (MED-V) 2.0 エンドユーザーの認証は、非常に重要なセキュリティの問題です。 このコンテキストでは、authentication は、MED-V エンドユーザーの id を確認することを意味します。

以下のセクションでは、MED-V でのエンドユーザー認証についての情報とガイダンスを示します。

## MED-V でのユーザー認証


通常、MED-V での認証は、ユーザーが最初に MED-V にアクセスしたときと、ユーザーがパスワードを変更したときに、常に2つのレベルで行われます。

認証用に MED-V 設定を構成した方法によっては、一般に、MED-V が開始されたとき、または公開されたアプリケーションを初めて開こうとしたときに、ユーザーにパスワードの入力を求めるメッセージが表示されます。

コントロールできるエンドユーザー認証には、次のようないくつかの側面があります。

エンドユーザーが入力する資格情報が資格情報マネージャーに保存されているかどうか

エンドユーザーにパスワードの入力と保存のオプションが表示される方法

企業がエンドユーザー認証を管理するための優先プロセスに応じて、特定の MED-V ワークスペースに対して資格情報のキャッシュを実行するかどうかを指定できます。 エンドユーザーの資格情報をキャッシュすると、パスワードに対して1回だけの入力が求められるため便利です。 エンドユーザーが自分のパスワードを保存することを許可されていない場合、または、新しい med-v セッションを開始するたびに、新しい med-v セッションを開始する場合は、その後でもう一度入力する必要があります。 たとえば、エンドユーザーがホストにログオンしたときに、有効になっているが、認証が無効になっている場合、エンドユーザーはログオン時に1回のみプロンプトを表示するように設定されます。 この場合、資格情報はエンドユーザーがホストからログオフするまで有効です。

必要に応じて、Credential Manager を使用して、保存されているエンドユーザーの資格情報を削除することができます。

既定では、資格情報の保存は無効になっていますが、次のいずれかの方法を使用してこの設定を変更できます。

**Med-v ワークスペースパッケージを作成しているとき**。 詳細については、「 [Med-v ワークスペースパッケージを作成する](create-a-med-v-workspace-package.md)」を参照してください。

**Med-v ワークスペースを展開**した後。 ターミナルサービスのレジストリキーを設定するには、MED-V コマンドレットパラメーター UxCredentialCacheEnabled を編集します。 詳細については、「Windows PowerShell のヘルプ」を参照してください。

MED-V workspace の展開後に、DisablePasswordSaving という名前のターミナルサービスポリシーを変更して、エンドユーザー認証の環境設定を行うことができます。 DisablePasswordSaving [RDP クライアント] ダイアログウィンドウに [パスワードを保存する] チェックボックスが表示されるかどうか、および MED-V 資格情報の確認メッセージが表示されるかどうかを制御します。

DisablePasswordSaving という名前のターミナルサービスポリシーのポリシーパスを次に示します。

**Regedit.exe**

HKEY \ _LOCAL \ _MACHINE \ ソフトウェア \\ Machine\\Policies\\DisablePasswordSaving

**注**  
DisablePasswordSaving に加えた変更は、仮想マシンへの RDP プロンプトにのみ影響します。



次の表に、資格情報の保存方法と、さまざまな構成の効果の設定を構成するさまざまな方法を示します。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">値</th>
<th align="left">構成</th>
<th align="left">結果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>DisablePasswordSaving</p></td>
<td align="left"><p><strong>無効</strong></p></td>
<td align="left"><p>MED-V のプロンプトが表示され、[承諾] のチェックボックスが使用でき、オフになっています。 エンドユーザーがチェックボックスをオンにすると、後で使用するために資格情報がキャッシュされます。 エンドユーザーにも、パスワードの有効期限が切れるときにのみメッセージが表示されるという利点があります。</p>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>エンドユーザーがチェックボックスをオンにしない場合は、MED-V プロンプトではなくリモートデスクトップ接続 (RDC) クライアントのプロンプトが表示され、[受け入れる] チェックボックスはオフになります。 エンドユーザーがチェックボックスをオンにすると、RDC クライアント資格情報が保存され、後で使用できるようになります。</p>
<div class="alert">
<strong>重要</strong><br/><p>エンドユーザーが資格情報を入力しても、RDC は資格情報を検証しません。 エンドユーザーが RDC プロンプトを使用して資格情報をキャッシュした場合、正しくない資格情報が保存される可能性があるというリスクがあります。 この場合、Windows Credential Manager で間違った資格情報を削除する必要があります。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>DisablePasswordSaving</p></td>
<td align="left"><p><strong>有効</strong></p></td>
<td align="left"><div class="alert">
<strong>注</strong><br/><p>この構成では、エンドユーザーの資格情報をキャッシュできないため、安全性は高くなります。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



既定では、MED-V をインストールすると、ゲストでレジストリキーが設定され、"有効期限切れのパスワード" プロンプトが表示されません。 エンドユーザーは、ホストでパスワードの変更を求められるだけです。 ホスト上で更新された資格情報がゲストに渡されます。

**注意**  
環境でグループポリシーを使用する場合は、ゲストからのパスワードの入力を求めるメッセージが表示される原因となっているレジストリキーを上書きできることを確認します。



### 認証に関するセキュリティの問題

エンドユーザーの資格情報をキャッシュすると、ユーザーエクスペリエンスが最大限に向上しますが、そのリスクについて注意する必要があります。

資格情報のキャッシュが有効になっている場合、エンドユーザーのドメイン資格情報は、Windows Credential Manager 内の元に戻せる形式で格納されます。 このため、攻撃者は、システムレベルプロセスまたはエンドユーザープロセスとして実行されるツールを作成し、エンドユーザーの資格情報を取得することができます。 このリスクを軽減するには、DisablePasswordSaving を**Enabled**に設定します。

この問題は、MED-V 認証を無効にしたときに、ターミナルサービスのポリシー設定が有効になっている場合にも発生します。

## 関連トピック


[MED-V 操作のセキュリティのベスト プラクティス](security-best-practices-for-med-v-operations.md)









