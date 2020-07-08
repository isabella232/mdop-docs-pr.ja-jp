---
title: UE-V 1.0 を使用して同期するアプリケーションの計画
description: UE-V 1.0 を使用して同期するアプリケーションの計画
author: dansimp
ms.assetid: c718274f-87b4-47f3-8ef7-5e1bd5557a9d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7f2b04942588d0f6efad03d5e0249534cd325c09
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812418"
---
# UE-V 1.0 を使用して同期するアプリケーションの計画


Microsoft User Experience Virtualization (UE-V) では、UE-V でキャプチャおよび適用される設定を定義する設定場所テンプレート (XML ファイル) が使用されます。 UE-V には、定義済みの設定場所テンプレートのセットが含まれています。また、管理者は、エンタープライズで使用されるサードパーティまたは基幹業務アプリケーション用のカスタム設定の場所テンプレートを作成することもできます。

管理者として、どのアプリケーションを UE-V ソリューションに含めるかを検討している場合は、ユーザーによってカスタマイズできる設定と、その設定をどのように保存するかを検討してください。 すべてのアプリケーションには、カスタマイズ可能な設定や、ユーザーによって定期的にカスタマイズできる設定が含まれているわけではありません。 また、アプリケーションの設定によっては、複数のコンピューターまたは環境間での安全なローミングができない場合もあります。 次の条件を満たす設定を同期します。

-   ユーザーがアクセスできる場所に保存される設定。 たとえば、レジストリの system32 または外部の HKCU セクションに保存されている設定を同期しないようにします。

-   特定のコンピューターに固有の設定ではありません。 たとえば、ネットワークまたはハードウェアの構成を除外します。

-   データが破損していなくてもコンピューター間で同期できる設定。 たとえば、データベースファイルに保存されている設定を使用しないようにします。

## UE-V に含まれる設定場所テンプレート


**UE-V アプリケーション設定の場所テンプレート**

UE-V agent インストールソフトウェアは、エージェントをインストールし、一般的な Microsoft アプリケーションの設定場所テンプレートの既定のグループを登録します。 これらの設定場所テンプレートは、次のアプリケーションの設定値を取得します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>アプリケーションカテゴリ</strong></th>
<th align="left"><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Office 2010 アプリケーション</p></td>
<td align="left"><p>Microsoft Word 2010</p>
<p>Microsoft Excel 2010</p>
<p>Microsoft Outlook 2010</p>
<p>Microsoft Access 2010</p>
<p>Microsoft Project 2010</p>
<p>Microsoft PowerPoint 2010</p>
<p>Microsoft Publisher 2010</p>
<p>Microsoft Visio 2010</p>
<p>Microsoft SharePoint Workspace 2010</p>
<p>Microsoft InfoPath 2010</p>
<p>Microsoft Lync 2010</p>
<p>Microsoft OneNote 2010</p></td>
</tr>
<tr class="even">
<td align="left"><p>ブラウザーオプション (Internet Explorer 8、Internet Explorer 9、Internet Explorer 10)</p></td>
<td align="left"><p>[お気に入り]、[ホーム] ページ、[タブ]、およびツールバー。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows アクセサリ</p></td>
<td align="left"><p>電卓、メモ帳、ワードパッド。</p></td>
</tr>
</tbody>
</table>

 

アプリケーションの設定は、アプリケーションの起動時にアプリケーションに適用されます。 これらは、アプリケーションが閉じるときに保存されます。

**UE-V Windows 設定の場所テンプレート**

ユーザーエクスペリエンスの仮想化には、次の Windows 設定の設定値をキャプチャする設定場所テンプレートが含まれています。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Windows の設定</th>
<th align="left">説明</th>
<th align="left">適用対象</th>
<th align="left">既定の状態</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>デスクトップの背景</p></td>
<td align="left"><p>現在アクティブなデスクトップの背景。</p></td>
<td align="left"><p>ログオン、ロック解除、リモート接続。</p></td>
<td align="left"><p>有効</p></td>
</tr>
<tr class="even">
<td align="left"><p>コンピューターの簡単操作</p></td>
<td align="left"><p>アクセシビリティと入力の設定、拡大鏡、ナレーター、スクリーンキーボード。</p></td>
<td align="left"><p>ログオン、ロック解除、リモート接続。</p></td>
<td align="left"><p>無効</p></td>
</tr>
<tr class="odd">
<td align="left"><p>デスクトップの設定</p></td>
<td align="left"><p>[スタート] メニューとタスクバーの設定、フォルダーオプション、既定のデスクトップアイコン、追加の時計、および地域と言語の設定。</p></td>
<td align="left"><p>ログオンのみ。</p></td>
<td align="left"><p>無効</p></td>
</tr>
</tbody>
</table>

 

Windows デスクトップの背景と簡単なアクセス設定は、ユーザーがログオンしたとき、コンピューターのロックが解除されたとき、または別のコンピューターへのリモート接続時に適用されます。 エージェントは、ユーザーがログオフしたとき、コンピューターがロックされているとき、またはリモート接続が切断されたときに、これらの設定を保存します。 既定では、Windows デスクトップの背景設定は、同じオペレーティングシステムバージョンのコンピューター間でローミングされます。

Windows デスクトップと簡単操作の設定は、ユーザーにデスクトップが表示される前にログオン時に適用されます。 ログオンエクスペリエンスを最適化するために、これらの設定は既定ではローミングされません。 デスクトップと簡単操作の設定は、グループポリシー、PowerShell、WMI を使って有効にすることができます。

UE-V は、異なる言語のオペレーティングシステム間での設定のローミングをサポートしていません。 たとえば、英語とドイツ語の間の同期はサポートされていません。 UE-V がユーザー設定をローミングするすべてのコンピューターの言語は一致する必要があります。

**注** Microsoft によって提供される設定の場所テンプレートを変更した場合、ユーザーエクスペリエンスの仮想化は、指定したアプリケーションまたは Windows の [設定] グループで適切に動作しない可能性があります。

 

## <a href="" id="prevent-unintentional-user-settings-configuration-"></a>意図しないユーザー設定の構成を防ぐ


ユーザーエクスペリエンスの仮想化では、新しいユーザー設定の情報が確認され、設定の保存場所からその情報が自動的にダウンロードされます。 次のような場合、ローカルコンピューターに設定が適用されます。

-   登録されている UE-V テンプレートが含まれているアプリケーションが起動されるたび。

-   ユーザーが自分のコンピューターにログオンしたとき。

-   ユーザーがコンピューターのロックを解除したとき。

-   UE-V がインストールされているリモートデスクトップコンピューターへの接続が行われた場合。

UE-V がコンピューター A とコンピューター B にインストールされていて、アプリケーションの目的の設定がコンピューター A 上にある場合は、コンピューター A で最初にアプリケーションを開いて閉じる必要があります。 最初にコンピューター B でアプリを開いて閉じた場合、コンピューター A 上のアプリケーション設定は、コンピューター B のアプリケーション設定と同じになるように構成されます。

このシナリオは、Windows の設定にも適用されます。 コンピューター B の Windows 設定がコンピューター A の Windows 設定と同じである必要がある場合は、ユーザーがコンピューター A を最初にログオンしてログオフする必要があります。

目的のユーザー設定が誤った順序で適用されている場合は、設定が上書きされたコンピューター上の特定のアプリケーションまたは Windows 構成の復元操作を実行することで、それらの設定を回復できます。 詳細については、「 [ue-v 1.0 と同期されたアプリケーションと Windows の設定の復元](restoring-application-and-windows-settings-synchronized-with-ue-v-10.md)」を参照してください。

## カスタム UE-V 設定場所テンプレート


ユーザー設定の場所テンプレートは、UE-V Generator を使って作成できます。 テスト環境でカスタム設定場所テンプレートを作成してテストしたら、エンタープライズ内のコンピューターに設定場所テンプレートを展開できます。 カスタム設定の場所テンプレートは、エンタープライズソフトウェア配布 (ESD) メソッドなどの既存の展開インフラストラクチャを使用して展開するか、または UE-V 設定テンプレートカタログを構成する必要があります。 ESD またはグループポリシーと共に展開されるテンプレートは、UE-V WMI または PowerShell を使用して登録する必要があります。 カスタム設定の場所テンプレートの詳細については、「 [ue-v 1.0 向けのカスタムテンプレートの展開を計画](planning-for-custom-template-deployment-for-ue-v-10.md)する」を参照してください。

基幹業務アプリケーションを同期する必要があるかどうかに関するガイダンスについては、「 [ue-v 1.0 の基幹業務アプリケーションを評価するためのチェックリスト](checklist-for-evaluating-line-of-business-applications-for-ue-v-10.md)」を参照してください。

## 関連トピック


[UE-V 1.0 の計画](planning-for-ue-v-10.md)

[UE-V 1.0 のカスタム テンプレートの展開計画](planning-for-custom-template-deployment-for-ue-v-10.md)

[UE-V 1.0 の展開](deploying-ue-v-10.md)

 

 





