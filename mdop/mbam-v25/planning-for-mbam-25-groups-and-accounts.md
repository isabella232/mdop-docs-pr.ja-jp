---
title: MBAM 2.5 グループとアカウントの計画
description: MBAM 2.5 グループとアカウントの計画
author: dansimp
ms.assetid: 73bb9fe5-5900-4b6f-b271-ade62991fca1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: 3431c3602685a4f96cb4c1333700107ba9c38b96
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825804"
---
# MBAM 2.5 グループとアカウントの計画


このトピックでは、Microsoft BitLocker の管理と監視 (MBAM) データベース、レポート、および web アプリケーションのセキュリティとアクセス権を提供するために、Active Directory ドメインサービス (AD DS) で作成する必要がある役割とアカウントの一覧を示します。 各ロールとアカウントについて、MBAM サーバー構成ウィザードの対応するフィールドが提供されています。 これらのアカウントに対応する Windows PowerShell コマンドレットとパラメーターの一覧については、「 [Windows Powershell を使用して MBAM 2.5 サーバー機能を構成](configuring-mbam-25-server-features-by-using-windows-powershell.md#bkmk-reqd-posh-accts)する」を参照してください。

**注**  
MBAM は、管理されたサービスアカウントの使用をサポートしていません。



## データベースアカウント


コンプライアンスと監査データベースおよび回復データベースの次のアカウントを作成します。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">アカウント名と目的</th>
<th align="left">アカウントの種類</th>
<th align="left">このアカウントに対応する MBAM サーバー構成ウィザードフィールド</th>
<th align="left">このアカウントに対応する MBAM サーバー構成ウィザードのフィールドの説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>コンプライアンスと監査データベースと復元データベースの読み取り/書き込みのユーザーまたはレポートのグループ</p></td>
<td align="left"><p>ユーザーまたはグループ</p></td>
<td align="left"><p>読み取り/書き込みアクセスドメインユーザーまたはグループ</p></td>
<td align="left"><p>コンプライアンスと監査データベースへの読み取り/書き込みアクセス許可を持つドメインユーザーまたはグループ。また、web アプリケーションがこれらのデータベースのデータとレポートにアクセスできるようにするための回復データベースです。</p>
<p>このフィールドにユーザー名を入力した場合、[ <strong> Web アプリケーションの構成] ページの [web サービスアプリケーションプールのドメインアカウント] フィールドの値と同じ値にする必要があり </strong> <strong> </strong> ます。</p>
<p>このフィールドにグループ名を入力した場合、[ <strong> Web アプリケーションの構成] ページの [web サービスアプリケーションプールのドメインアカウント] フィールドの値は、 </strong> <strong> </strong> このフィールドに入力するグループのメンバーである必要があります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>コンプライアンスおよび監査データベース読み取り専用ユーザーまたはレポート用グループ</p></td>
<td align="left"><p>ユーザーまたはグループ</p></td>
<td align="left"><p>読み取り専用アクセスドメインのユーザーまたはグループ</p></td>
<td align="left"><p>コンプライアンスと監査データベースへの読み取り専用アクセスが許可されているユーザーまたはグループの名前。レポートがこのデータベースのコンプライアンスと監査データにアクセスできるようにします。</p>
<p>このフィールドにユーザー名を入力した場合、[ <strong> </strong> レポートの構成] ページの [コンプライアンスおよび監査データベースドメインアカウント] フィールドで指定したユーザーと同じユーザー名を入力する必要があり <strong> </strong> ます。</p>
<p>このフィールドにグループ名を入力した場合、[ <strong> レポートの構成] ページの [コンプライアンスと監査データベースのドメインアカウント] フィールドで指定した値は、 </strong> <strong> </strong> このフィールドで指定したグループのメンバーである必要があります。</p></td>
</tr>
</tbody>
</table>



## レポートアカウント


レポート機能に対して次のアカウントを作成します。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">アカウント名/目的</th>
<th align="left">アカウントの種類</th>
<th align="left">このアカウントに対応する MBAM サーバー構成ウィザードフィールド</th>
<th align="left">このアカウントに対応する MBAM サーバー構成ウィザードのフィールドの説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>レポート読み取り専用ドメインアクセスグループ</p></td>
<td align="left"><p>Group</p></td>
<td align="left"><p>レポート役割のドメイングループ</p></td>
<td align="left"><p>管理および監視 Web サイトのレポートに対して読み取り専用のアクセス権を持つドメインユーザーグループを指定します。 指定するグループは、web アプリが有効になっているときに、レポートの読み取り専用アクセスグループパラメーターとして指定したグループと同じグループである必要があります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>コンプライアンスと監査データベースドメインのユーザーアカウント</p></td>
<td align="left"><p>ユーザー</p></td>
<td align="left"><p>コンプライアンスと監査データベースのドメインアカウント</p></td>
<td align="left"><p>ローカル SQL Server Reporting Services インスタンスがコンプライアンスと監査データベースにアクセスするために使用するドメインユーザーアカウントとパスワード。 このアカウントに <strong> </strong> は、SQL Server Reporting Services サーバーへのバッチ権限としてログオンする権限が必要です。</p>
<p>[ <strong> データベースの構成] ページの [読み取り専用アクセスドメインユーザーまたはグループ] フィールドに入力した値がユーザー名である場合は、 </strong> <strong> </strong> このフィールドに同じ値を入力する必要があります。</p>
<p>[ <strong> データベースの構成] ページの [読み取り専用アクセスドメインユーザーまたはグループ] フィールドに入力した値 </strong> <strong> がグループ名である場合 </strong> 、このフィールドに入力する値は、そのグループのメンバーである必要があります。</p>
<p>有効期限が切れないように、このアカウントのパスワードを設定します。 ユーザーアカウントは、MBAM Reports Users グループで利用できるすべてのデータにアクセスできる必要があります。</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-helpdesk-roles"></a>管理と監視 Web サイト (ヘルプデスク) アカウント


管理と監視の Web サイトに次のアカウントを作成します。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">アカウント名/目的</th>
<th align="left">アカウントの種類</th>
<th align="left">このアカウントに対応する MBAM サーバー構成ウィザードフィールド</th>
<th align="left">このアカウントに対応する MBAM サーバー構成ウィザードのフィールドの説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Web サービスアプリケーションプールドメインアカウント</p></td>
<td align="left"><p>ユーザー</p></td>
<td align="left"><p>Web サービスアプリケーションプールドメインアカウント</p></td>
<td align="left"><p>Web アプリケーションのアプリケーションプールによって使用されるドメインユーザーアカウント。</p>
<p>[ <strong> データベースの構成] ページの [読み取り/書き込み権限ドメインユーザーまたはグループ] フィールドにユーザー名を入力した場合は、 </strong> <strong> </strong> このフィールドに同じ値を入力する必要があります。</p>
<p>[ <strong> データベースの構成] ページの [読み取り/書き込みアクセスドメインユーザーまたはグループ] フィールドにグループ名を入力した場合 </strong> <strong> </strong> 、このフィールドに入力する値は、そのグループのメンバーである必要があります。</p>
<p>資格情報を指定しない場合、以前に有効になっていた web アプリケーションに指定された資格情報が使用されます。 すべての web アプリケーションは、同じアプリケーションプールの資格情報を使用する必要があります。 Web アプリケーションごとに異なる資格情報を指定すると、最後に指定された値が使用されます。</p>
<div class="alert">
<strong>重要</strong><br/><p>セキュリティを向上させるには、資格情報で指定されているアカウントに、制限付きのユーザー権限を設定します。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM Advanced ヘルプデスクユーザーアクセスグループ</p></td>
<td align="left"><p>Group</p></td>
<td align="left"><p>MBAM Advanced ヘルプデスクユーザー</p></td>
<td align="left"><p>管理と監視の Web サイトのすべての回復領域にメンバーがアクセスできるドメインユーザーグループ。 この役割を持つユーザーは、エンドユーザーがドライブを回復するときに、エンドユーザーのドメインとユーザー名ではなく、回復キーのみを入力する必要があります。 Mbam ヘルプデスクユーザーグループと MBAM Advanced ヘルプデスクユーザーグループの両方のメンバーである場合、MBAM Advanced ヘルプデスクのユーザーグループの権限は、MBAM ヘルプデスクのグループ権限よりも優先されます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM ヘルプデスクユーザーアクセスグループ</p></td>
<td align="left"><p>Group</p></td>
<td align="left"><p>MBAM ヘルプデスクユーザー</p></td>
<td align="left"><p>「MBAM 管理および監視 Web サイトの TPM およびドライブ回復の領域を管理する」にアクセスできるメンバーのドメインユーザーグループ。 この役割を持つユーザーは、いずれかのオプションを使用する場合は、エンドユーザーのドメインとアカウント名を含むすべてのフィールドに入力する必要があります。</p>
<p>Mbam ヘルプデスクユーザーグループと MBAM Advanced ヘルプデスクユーザーグループの両方のメンバーである場合、MBAM Advanced ヘルプデスクのユーザーグループの権限は、MBAM ヘルプデスクのグループ権限よりも優先されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM レポートユーザーアクセスグループ</p></td>
<td align="left"><p>Group</p></td>
<td align="left"><p>MBAM レポートユーザー</p></td>
<td align="left"><p>管理および監視 Web サイトの [レポート] 領域のレポートに対する読み取り専用アクセス権を持つメンバーのドメインユーザーグループ。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM データ移行ユーザーグループ</p></td>
<td align="left"><p>Group</p></td>
<td align="left"><p>MBAM データ移行ユーザー</p></td>
<td align="left"><p>Mbam サーバー上で実行されている MBAM 回復とハードウェアサービスを使用して、メンバーが MBAM にデータを書き込む権限を持つ、オプションのドメインユーザーグループ。 通常、このアカウントは、書き込み/Mbam * コマンドレットと共に使用され、回復と TPM データを Active Directory から MBAM データベースに書き込みます。</p>
<p>詳細については、「 <a href="mbam-25-security-considerations.md" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md)"> mbam 2.5 セキュリティに関する考慮事項」を参照してください </a> 。</p></td>
</tr>
</tbody>
</table>




## 関連トピック


[MBAM 2.5 に対応する環境の準備](preparing-your-environment-for-mbam-25.md)

[MBAM 2.5 展開の前提条件](mbam-25-deployment-prerequisites.md)



## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。 





