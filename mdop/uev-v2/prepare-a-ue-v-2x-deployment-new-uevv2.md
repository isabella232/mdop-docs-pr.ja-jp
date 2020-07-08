---
title: UE-V の展開を準備する
description: UE-V の展開を準備する
author: dansimp
ms.assetid: c429fd06-13ff-48c5-b9c9-fa1ec01ab800
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 04/19/2017
ms.openlocfilehash: e6b2de407990536e1a08532632dcea19ea0d0ee9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826424"
---
# UE-V の展開を準備する


Microsoft User Experience Virtualization (UE-V) 2.0 または2.1 を、ユーザーがエンタープライズでアクセスするデバイス間で設定を同期するためのソリューションとして展開する前に、いくつかの計画と準備を行う必要があります。 このトピックでは、展開を成功させるために、どのような種類の展開を事前に決定するかを決定するのに役立ちます。

まず、UE-V を展開するタスクを見てみましょう。

-   UE-V の展開を計画する

    何かを展開する前に、展開する UE-V 機能を決定するために、少し計画を立てることをお勧めします。 このページから離れる場合は、以下の計画情報を参照してください。

-   [UE-V 2.x の必要な機能を展開する](deploy-required-features-for-ue-v-2x-new-uevv2.md)

    すべての UE-V の展開では、次の操作が必要です。

    -   [設定の保存場所を定義する](https://technet.microsoft.com/library/dn458891.aspx#ssl)

    -   [UE-V エージェントを展開して UE-V 構成を管理する方法を決定する](https://technet.microsoft.com/library/dn458891.aspx#config)

    -   設定を同期する必要があるすべてのユーザーコンピューターに[Ue-v agent をインストール](https://technet.microsoft.com/library/dn458891.aspx#agent)する

-   必要に応じ[て、カスタムアプリケーションの ue-v 2. x を展開](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)することができます。

    計画は、カスタムアプリケーション (サードパーティまたは基幹業務) の設定の同期を UE-V がサポートしているかどうかを確認するのに役立ちます。これには、次のような UE-V の機能が必要です。

    -   カスタムのアプリケーション設定を同期するために必要なカスタム設定の場所テンプレートを作成、編集、検証できるように[、UEV Generator をインストール](https://technet.microsoft.com/library/dn458942.aspx#uevgen)します。

    -   UE-V Generator を使用して[カスタム設定場所テンプレートを作成](https://technet.microsoft.com/library/dn458942.aspx#createcustomtemplates)する

    -   カスタム設定の場所テンプレートを格納するために使用する[ue-v 設定テンプレートカタログを展開](https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue)する

このワークフロー図は、UE-V の展開と、企業への UE-V の展開方法を決定する決定についての高度な知識を提供します。

![deploymentworkflow](images/deploymentworkflow.png)

**Ue-v の展開を計画する:** 最初に、展開する UE-V コンポーネントを特定できるように、若干の計画を立てておきます。 UE-V の展開を計画するには、次のことを行う必要があります。

-   [カスタムアプリケーションの設定を同期するかどうかを決定する](#deciding)

    これにより、展開中に UE-V Generator をインストールするかどうかを決定します。これにより、カスタム設定の場所テンプレートを作成できます。 次の操作を行います。

    [Ue-v 展開で自動的に同期される設定](#autosyncsettings)を確認します。

    [他のアプリケーションの設定を同期する必要があるかどうかを確認](#determinesettingssync)します。

-   高可用性、キャパシティ計画など、 [ue-v の展開に関するその他の考慮事項](#considerations)を確認します。

-   [UE-V の前提条件とサポートされる構成を確認する](#prereqs)

## <a href="" id="deciding"></a>カスタムアプリケーションの設定を同期するかどうかを決定する


UE-V の展開では、多くの設定が自動的に同期されます。 しかし、UE-V をカスタマイズして、基幹業務やサードパーティのアプリなど、他のアプリケーションの設定を同期することもできます。

UE-V を使用してカスタムアプリケーションの設定を同期するかどうかを判断することは、UE-V の展開を計画するうえで最も重要な部分です。 このセクションのトピックは、この決定を行うのに役立ちます。

### <a href="" id="autosyncsettings"></a>UE-V 展開で自動的に同期される設定

このセクションでは、UE-V で既定で同期される設定について説明します。次の情報が含まれます。

既定で同期されている設定を持つデスクトップアプリケーション

既定で同期される Windows デスクトップの設定

Windows アプリ設定の同期のサポートのステートメント

UE-V で同期されている特定の Microsoft Office 2013、Microsoft Office 2010、および Microsoft Office 2007 の設定の完全な一覧をダウンロードするには、 [Microsoft office のユーザーエクスペリエンスの仮想化 (ue-v) 設定テンプレート](https://www.microsoft.com/download/details.aspx?id=46367)を参照してください。

### UE-V 2.1 および UE-V 2.1 SP1 で既定で同期されているデスクトップアプリケーション

UE-V 2.1 または 2.1 SP1 エージェントをインストールすると、これらの一般的な Microsoft アプリケーションの設定値をキャプチャする既定の設定場所テンプレートのグループが登録されます。

**ヒント**  
**Microsoft office 2007 の設定の同期**-ue-v 2.1 および 2.1 SP1 では、設定場所テンプレートが、Office 2007 アプリケーションに既定で含まれなくなりました。 ただし、Office 2007 テンプレートは UE-V 2.0 以前からも使用できます。また、 [ue-v テンプレートギャラリー](https://go.microsoft.com/fwlink/p/?LinkID=246589)からテンプレートを取得することもできます。



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
<td align="left"><p>Microsoft Office 2010 アプリケーション</p>
<p>(同期された <a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> すべての設定のリストをダウンロードします </a> )</p></td>
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
<p>Microsoft OneNote 2010</p>
<p>Microsoft SharePoint Designer 2010</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Office 2013 アプリケーション</p>
<p>(同期された <a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> すべての設定のリストをダウンロードします </a> )</p></td>
<td align="left"><p>Microsoft Word 2013</p>
<p>Microsoft Excel 2013</p>
<p>Microsoft Outlook 2013</p>
<p>Microsoft Access 2013</p>
<p>Microsoft Project 2013</p>
<p>Microsoft PowerPoint 2013</p>
<p>Microsoft Publisher 2013</p>
<p>Microsoft Visio 2013</p>
<p>Microsoft InfoPath 2013</p>
<p>Microsoft Lync 2013</p>
<p>Microsoft OneNote 2013</p>
<p>Microsoft SharePoint Designer 2013</p>
<p>Microsoft Office 2013 アップロードセンター</p>
<p>Microsoft OneDrive for Business 2013</p>
<p>UE-V 2.1 および 2.1 SP1 の Microsoft Office 2013 設定の場所テンプレートには、強化された Outlook 署名のサポートが含まれています。 新規、返信、転送メールの既定の署名設定の同期が追加されました。</p>
<div class="alert">
<strong>注</strong><br/><p>ユーザーが Outlook の署名を同期するすべてのデバイスに対して、Outlook プロファイルを作成する必要があります。 プロファイルがまだ作成されていない場合は、ユーザーがそれを作成し、そのデバイスで Outlook を再起動して、署名の同期を有効にすることができます。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>ブラウザーのオプション: Internet Explorer 8、Internet Explorer 9、Internet Explorer 10、Internet Explorer 11</p></td>
<td align="left"><p>[お気に入り]、[ホーム] ページ、[タブ]、およびツールバー。</p>
<div class="alert">
<strong>注</strong><br/><p>UE-V では、Internet Explorer cookie のローミング設定は行われません。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>Windows アクセサリ</p></td>
<td align="left"><p>Microsoft 電卓、メモ帳、ワードパッド。</p></td>
</tr>
</tbody>
</table>



**注**  
UE-V 2.1 SP1 は、以前のオペレーティングシステムでの Windows 10 と Microsoft 電卓の間の設定を同期しません。



### UE-V 2.0 で既定で同期されているデスクトップアプリケーション

UE-V 2.0 Agent をインストールすると、これらの一般的な Microsoft アプリケーションの設定値をキャプチャする、設定の場所テンプレートの既定のグループが登録されます。

**ヒント**  
**Microsoft office 2013 の設定の同期**-Ue-v 2.0 では、Office 2013 アプリケーションには既定で設定場所テンプレートが含まれていませんが、 [ue-v テンプレートギャラリー](https://go.microsoft.com/fwlink/p/?LinkID=246589)からダウンロードできます。 [Office 2013 と ue-v 2.0 を同期すると](synchronizing-office-2013-with-ue-v-20-both-uevv2.md)、office 2013 の設定を同期するサポートされているテンプレートの詳細が提供されます。



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
<td align="left"><p>Microsoft Office 2007 アプリケーション</p>
<p>(同期された <a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> すべての設定のリストをダウンロードします </a> )</p></td>
<td align="left"><p>Microsoft Access 2007</p>
<p>Microsoft Communicator 2007</p>
<p>Microsoft Excel 2007</p>
<p>Microsoft InfoPath 2007</p>
<p>Microsoft OneNote 2007</p>
<p>Microsoft Outlook 2007</p>
<p>Microsoft PowerPoint 2007</p>
<p>Microsoft Project 2007</p>
<p>Microsoft Publisher 2007</p>
<p>Microsoft SharePoint Designer 2007</p>
<p>Microsoft Visio 2007</p>
<p>Microsoft Word 2007</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Office 2010 アプリケーション</p>
<p>(同期された <a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> すべての設定のリストをダウンロードします </a> )</p></td>
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
<p>Microsoft OneNote 2010</p>
<p>Microsoft SharePoint Designer 2010</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ブラウザーのオプション: Internet Explorer 8、Internet Explorer 9、Internet Explorer 10</p></td>
<td align="left"><p>[お気に入り]、[ホーム] ページ、[タブ]、およびツールバー。</p>
<div class="alert">
<strong>注</strong><br/><p>UE-V では、Internet Explorer cookie のローミング設定は行われません。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>Windows アクセサリ</p></td>
<td align="left"><p>Microsoft 電卓、メモ帳、ワードパッド。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="autosyncsettings2"></a>Windows の設定が既定で同期されている

UE-V には、これらの Windows 設定の設定値をキャプチャする設定場所テンプレートが含まれています。

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Windows の設定</th>
<th align="left">説明</th>
<th align="left">適用対象</th>
<th align="left">エクスポートする</th>
<th align="left">既定の状態</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>デスクトップの背景</p></td>
<td align="left"><p>現在アクティブなデスクトップの背景または壁紙。</p></td>
<td align="left"><p>ログオン、ロック解除、リモート接続、スケジュールされたタスクイベント。</p></td>
<td align="left"><p>ログオフ、ロック、リモート切断、 <strong> 会社設定センターで [今すぐ同期] をクリックするか、スケジュールされた </strong> タスクの間隔</p></td>
<td align="left"><p>有効</p></td>
</tr>
<tr class="even">
<td align="left"><p>コンピューターの簡単操作</p></td>
<td align="left"><p>アクセシビリティと入力の設定、Microsoft 拡大鏡、ナレーター、スクリーンキーボード。</p></td>
<td align="left"><p>ログオンのみ。</p></td>
<td align="left"><p>ログオフ、ユーザーが <strong> 会社設定センターで [今すぐ同期] をクリックする </strong> か、スケジュールされたタスクの間隔</p></td>
<td align="left"><p>有効</p></td>
</tr>
<tr class="odd">
<td align="left"><p>デスクトップの設定</p></td>
<td align="left"><p>[スタート] メニューとタスクバーの設定、フォルダーオプション、既定のデスクトップアイコン、追加の時計、および地域と言語の設定。</p></td>
<td align="left"><p>ログオンのみ。</p></td>
<td align="left"><p>ログオフ、ユーザーが <strong> 会社設定センターで [今すぐ同期] をクリックする、 </strong> またはスケジュールされたタスク</p></td>
<td align="left"><p>有効</p></td>
</tr>
</tbody>
</table>



**注**  
Windows 8 以降、UE-V は、スタート画面に関連する項目や場所などの設定をローミングしません。 また、UE-V は、固定されたタスクバー項目または Windows のファイルショートカットの同期をサポートしていません。



**重要**  
UE-V 2.1 SP1 では、Windows 10 デバイス間のタスクバーの設定が移動します。 ただし、UE-V は、以前のオペレーティングシステムが実行されている Windows 10 デバイスとデバイスとの間で、タスクバーの設定を同期しません。



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">設定グループ</th>
<th align="left">カテゴリ</th>
<th align="left">回収</th>
<th align="left">[適用]</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>アプリケーションの設定</strong></p></td>
<td align="left"><p>Windows アプリ  </p></td>
<td align="left"><p>アプリを閉じる</p>
<p>Windows アプリの設定の変更イベント</p></td>
<td align="left"><p>起動時に UE-V App Monitor を起動する</p>
<p>アプリを開く</p>
<p>Windows アプリの設定の変更イベント</p>
<p>設定パッケージの到着</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>デスクトップ アプリケーション</p></td>
<td align="left"><p>アプリケーションが閉じる</p></td>
<td align="left"><p>アプリケーションが開いて閉じます</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>デスクトップの設定</strong></p></td>
<td align="left"><p>デスクトップの背景</p></td>
<td align="left"><p>ロックまたはログオフ</p></td>
<td align="left"><p>ログオン、ロック解除、リモート接続、新しいパッケージ到着の通知、ユーザーが <strong> 会社設定センターで [今すぐ同期] をクリックする </strong> か、スケジュールされたタスクを実行します。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>簡単操作 (一般的–アクセシビリティ、ナレーター、拡大鏡、スクリーンキーボード)</p></td>
<td align="left"><p>ロックまたはログオフ</p></td>
<td align="left"><p>ログオン</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p>簡単操作 (シェルオーディオ、アクセシビリティ、キーボード、マウス)</p></td>
<td align="left"><p>ロックまたはログオフ</p></td>
<td align="left"><p>ログオン、ロック解除、リモート接続、新しいパッケージ到着の通知、ユーザーが <strong> 会社設定センターで [今すぐ同期] をクリックする </strong> か、スケジュールされたタスクが実行される</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>デスクトップの設定</p></td>
<td align="left"><p>ロックまたはログオフ</p></td>
<td align="left"><p>ログオン</p></td>
</tr>
</tbody>
</table>



### UE-V-Windows アプリのサポート

Windows アプリの場合、アプリの開発者は同期される設定を指定します。 どの Windows アプリで設定の同期を有効にするかを指定できます。

Windows PowerShell のコマンドプロンプトで、コンピューターの設定をパッケージファミリ名、有効状態、有効なソースに同期できる Windows アプリの一覧を表示するには、次のように入力します。 `Get-UevAppxPackage`

**注**  
Windows 8 では、ドメインユーザーがサインイン資格情報を Microsoft アカウントにリンクした場合、UE-V は Windows アプリの設定を同期しません。 このリンクにより、設定が Microsoft OneDrive (UE-V) に同期され、Windows アプリの設定の同期が無効になります。



### UE-V-ローミングプリンターのサポート

UE-V 2.1 SP1 では、ネットワークプリンターをデバイス間でローミングできるため、ネットワーク上のデバイスにログオンしたときに、ユーザーはネットワークプリンターにアクセスできます。 これには、既定として設定したプリンターのローミングも含まれます。

UE-V でのプリンターローミングには、次のいずれかのシナリオが必要です。

-   プリントサーバーは、新しいデバイスにローミングしたときに必要なドライバーをダウンロードできます。

-   ローミングネットワークプリンターのドライバーは、そのネットワークプリンターにアクセスする必要があるすべてのデバイスにプレインストールされています。

-   プリンタードライバーは、Windows Update から入手できます。

**注**  
UE-V プリンターローミング機能では、両面印刷などのプリンター設定や基本設定はローミング**されません**。



### <a href="" id="determinesettingssync"></a>他のアプリケーションの設定を同期する必要があるかどうかを判断する

UE-V の展開で自動的に同期される設定を確認した後で、他のアプリケーションの設定を同期するかどうかを決定します。これにより、企業全体で UE-V を展開する方法が決定されます。

管理者として、どのデスクトップアプリケーションを UE-V ソリューションに含めるかを検討している場合は、ユーザーによってカスタマイズできる設定と、その設定をどのように保存するかを検討してください。 デスクトップアプリケーションによっては、カスタマイズ可能な設定や、ユーザーによって定期的にカスタマイズされる設定が含まれているわけではありません。 また、すべてのデスクトップアプリケーションの設定が、複数のコンピューターまたは環境間で安全に同期されるとは限りません。

一般的に、次の条件を満たす設定を同期することができます。

-   ユーザーがアクセスできる場所に保存される設定。 たとえば、System32 または registry の HKEY \ _CURRENT \ _USER (HKCU) セクションの外側に保存されている設定を同期しないようにします。

-   特定のコンピューターに固有の設定ではありません。 たとえば、ネットワークまたはハードウェアの構成を除外します。

-   データが破損していなくてもコンピューター間で同期できる設定。 たとえば、データベースファイルに保存されている設定を使用しないようにします。

### <a href="" id="checklistsettingssync"></a>カスタムアプリケーションを評価するためのチェックリスト

他のアプリケーションの設定を同期する必要があると判断した場合は、このチェックリストを使用して、どのアプリケーションを含めるかを判断することができます。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>このアプリケーションには、ユーザーがカスタマイズできる設定が含まれていますか。</p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>これらの設定が同期されていることは、ユーザーにとって重要ですか?</p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>これらのユーザー設定は、既にアプリケーション管理または設定ポリシーソリューションによって管理されていますか。 UE-V は、アプリケーションの起動時と Windows の設定で、ログオン、ロック解除、またはリモート接続イベントにアプリケーション設定を適用します。 他の設定で UE-V を使用している場合、同期された設定の間に不整合が発生する可能性があります。</p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>アプリケーションの設定はコンピューターに固有のものですか? ハードウェアまたは特定のコンピューターの構成に関連付けられたアプリケーションの環境設定とカスタマイズは、セッション間で一貫して同期されず、アプリケーションのパフォーマンスが低下する可能性があります。</p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>アプリケーションは、Program Files ディレクトリか、または <strong> Users [ユーザー名] の強い AppData にあるファイルディレクトリの設定を保存してい </strong> &lt; &gt; </strong> &lt; &gt; </strong> ますか? 通常、これらの場所のいずれかに保存されているアプリケーションデータは、コンピューターに固有のデータであるか、データが大きすぎて同期できないため、ユーザーと同期しないようにしてください。</p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>アプリケーションは、同期しない他のアプリケーションデータを含むファイルの設定を保存していますか。 UE-V は、1つの単位としてファイルを同期します。 設定が設定以外のアプリケーションデータを含むファイルに保存されている場合は、この追加データを同期すると、アプリケーションのパフォーマンスが低下する可能性があります。</p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>設定を含むファイルのサイズはどのくらいですか? 設定の同期のパフォーマンスは、大きなファイルの影響を受ける可能性があります。 大きなファイルを含めると、設定の同期のパフォーマンスに影響する可能性があります。</p></td>
</tr>
</tbody>
</table>



## <a href="" id="considerations"></a>UE-V 展開を準備する際のその他の考慮事項


UE-V の展開を準備している場合も、次の点について考慮する必要があります。

-   [資格情報の同期を管理する](#creds)

-   [Windows アプリの設定の同期](#appxsettings)

-   [カスタム UE-V 設定場所テンプレート](#custom)

-   [意図しないユーザー設定の構成](#prevent)

-   [パフォーマンスと容量](#capacity)

-   [高可用性](#high)

-   [コンピューターの時計の同期](#clocksync)

### <a href="" id="creds"></a>UE-V 2.1 および UE-V 2.1 SP1 での資格情報の同期の管理

Microsoft Outlook や Lync など、多くのエンタープライズアプリケーションでは、ログイン時にドメインの資格情報をユーザーに確認するメッセージが表示されます。 ユーザーは、これらのアプリケーションを開くたびに入力する必要がないように、資格情報をディスクに保存するオプションがあります。 ローミング資格情報の同期を有効にすると、ユーザーは自分の資格情報を1台のコンピューターに保存して、環境で使用するすべてのコンピューターに再入力することを防止できます。 ユーザーは、一部のドメイン資格情報を UE-V 2.1 および 2.1 SP1 と同期させることができます。

**重要**  
資格情報の同期は既定で無効になっています。 この機能を実装するには、展開中に資格情報の同期を明示的に有効にする必要があります。



UE-V 2.1 および 2.1 SP1 は企業の資格情報を同期できますが、ローカルコンピューターでのみ使用する資格情報はローミングしません。

資格情報は同期設定であり、ユーザーは UE-V の同期後に初めてコンピューターにログインしたときにプロファイルに適用されます。

資格情報の同期は、独自の設定場所テンプレートによって管理されます。これは既定では無効になっています。 他のテンプレートと同じ方法で、このテンプレートを有効または無効にすることができます。 この機能のテンプレート識別子は RoamingCredentialSettings です。

**重要**  
環境で Active Directory 資格情報のローミングを使用している場合は、UE-V 資格情報ローミングテンプレートを有効にしないことをお勧めします。



資格情報の同期を有効にするには、次のいずれかの方法を使用します。

-   会社設定センター

-   PowerShell

-   グループ ポリシー

**注**  
資格情報は同期中に暗号化されます。



[会社設定センター](https://technet.microsoft.com/library/dn458903.aspx)**:** [Windows の設定] の [ローミングの資格情報の設定] チェックボックスをオンにして、資格情報の同期を有効にします。 チェックボックスをオフにして無効にします。 このチェックボックスは、アカウントが Microsoft アカウントを使用して設定を同期するように構成されていない場合にのみ、会社の設定センターに表示されます。

[Powershell](https://technet.microsoft.com/library/dn458937.aspx)**:** この PowerShell コマンドレットでは、資格情報の同期を有効にします。

``` syntax
Enable-UevTemplate RoamingCredentialSettings
```

この PowerShell コマンドレットでは、資格情報の同期を無効にします。

``` syntax
Disable-UevTemplate RoamingCredentialSettings
```

[グループポリシー](https://technet.microsoft.com/library/dn458893.aspx)**:** グループポリシーを使用して資格情報の同期を有効にするには[、最新の MDOP ADMX テンプレートを展開](https://go.microsoft.com/fwlink/p/?LinkId=393944)する必要があります。 資格情報の同期は、Windows の設定で管理されます。 グループポリシーを使ってこの機能を管理するには、[Windows の設定の同期] ポリシーを有効にします。

1.  グループポリシーエディターを開き、[**ユーザーの構成-管理用テンプレート– Windows コンポーネント– Microsoft User Experience Virtualization]** に移動します。

2.  [ **Windows の設定を同期する**] をダブルクリックします。

3.  このポリシーが有効になっている場合は、[**ローミング資格情報**] チェックボックスをオンにして資格情報の同期を有効にするか、オフにして資格情報の同期を無効にすることができます。

4.  **[OK]** をクリックします。

### UE-V で同期された資格情報の場所

アプリケーションによって保存された資格情報ファイルは、次の場所に同期されます。

-   %UserProfile%\\AppData\\Roaming\\Microsoft\\Credentials\\

-   %UserProfile%\\AppData\\Roaming\\Microsoft\\Crypto\\

-   %UserProfile%\\AppData\\Roaming\\Microsoft\\Protect\\

-   %UserProfile%\\AppData\\Roaming\\Microsoft\\SystemCertificates\\

他の場所に保存された資格情報は、UE-V で同期されません。

### <a href="" id="appxsettings"></a>Windows アプリの設定の同期

UE-V は、次の3つの方法で Windows アプリ設定の同期を管理します。

-   **Windows アプリの同期:** Windows アプリの同期を許可または拒否する

-   **Windows アプリの一覧:** Windows アプリのリストを同期する

-   **一覧にない既定の同期動作:** Windows アプリリストにない Windows アプリの同期動作を決定します。

詳細については、「 [Windows アプリの一覧](https://technet.microsoft.com/library/dn458925.aspx#win8applist)」を参照してください。

### <a href="" id="custom"></a>カスタム UE-V 設定場所テンプレート

カスタムアプリケーションの設定を同期するために UE-V を展開する場合は、UE-V Generator を使って、これらのデスクトップアプリケーション用のカスタム設定の場所テンプレートを作成します。 テスト環境でカスタム設定場所テンプレートを作成してテストしたら、エンタープライズ内のコンピューターに設定場所テンプレートを展開できます。

カスタム設定の場所テンプレートは、エンタープライズソフトウェアの配布 (ESD) など、System Center 構成マネージャーなどの既存の展開インフラストラクチャを使用して展開するか、UE-V 設定テンプレートカタログを構成する必要があります。 構成マネージャーまたはグループポリシーと共に展開されるテンプレートは、UE-V WMI または Windows PowerShell を使用して登録する必要があります。

カスタム設定の場所テンプレートの詳細については、「[カスタムアプリケーション用に ue-v を展開する](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)」を参照してください。 UE-V を構成マネージャーと共に使用する方法について詳しくは、「 [System Center Configuration manager 2012 で ue-v](configuring-ue-v-2x-with-system-center-configuration-manager-2012-both-uevv2.md)を構成する」をご覧ください。

### <a href="" id="prevent"></a>意図しないユーザー設定の構成を防ぐ

UE-V は、次のような場合に、設定の保存場所から新しいユーザー設定情報をダウンロードし、ローカルコンピューターに設定を適用します。

-   登録されている UE-V テンプレートを含むアプリケーションが起動されるたび。

-   ユーザーがコンピューターにログオンしたとき。

-   ユーザーがコンピューターのロックを解除したとき。

-   UE-V がインストールされているリモートデスクトップコンピューターへの接続が行われた場合。

-   同期コントローラーアプリケーションのスケジュールされたタスクが実行されたとき。

UE-V がコンピューター A とコンピューター B にインストールされていて、アプリケーションに必要な設定がコンピューター A 上にある場合は、コンピューター A で最初にアプリケーションを開いて閉じる必要があります。 最初にコンピューター B でアプリを開いて閉じた場合は、コンピューター A 上のアプリケーション設定がコンピューター B 上のアプリケーション設定に設定されます。設定は、アプリケーションごとにコンピューター間で同期されます。 時間の経過と共に、設定を使用してコンピューターを開いたり閉じたりすると、設定の一貫性が保たれます。

このシナリオは、Windows の設定にも適用されます。 コンピューター B の Windows 設定がコンピューター A の Windows 設定と同じである必要がある場合は、ユーザーが最初にコンピューターにログオンしてログオフする必要があります。

ユーザーが必要としているユーザー設定が誤った順序で適用されている場合は、その設定が上書きされたコンピューター上の特定のアプリケーションまたは Windows 構成に対して復元操作を実行することで、ユーザー設定を回復できます。 詳細については、「 [ue-v で管理用のバックアップと復元を管理](manage-administrative-backup-and-restore-in-ue-v-2x-new-topic-for-21.md)する」を参照してください。

### <a href="" id="capacity"></a>パフォーマンスとキャパシティの計画

標準のディスク容量とネットワーク正常性監視を使用して、UE-V の要件を指定します。

UE-V は、設定パッケージの保存にサーバーメッセージブロック (SMB) 共有を使用します。 設定パッケージのサイズは、各アプリケーションの設定情報によって異なります。 ほとんどの設定パッケージは小さいですが、デスクトップイメージなどの大きなファイルを同期すると、パフォーマンスが低下する可能性があります (特に低速ネットワーク)。

ネットワーク待ち時間の問題を減らすために、ユーザーのコンピューターが存在する同じローカルネットワーク上に設定の保存場所を作成します。 設定の保存場所については、ユーザー1人につき 20 MB のディスク領域をお勧めします。

既定では、設定パッケージのサイズが大きいため、UE-V の同期は2秒後にタイムアウトします。 同期メソッド = Syncmethod の設定は、[グループポリシーオブジェクト](https://technet.microsoft.com/library/dn458893.aspx)を使って構成できます。

### <a href="" id="high"></a>UE-V の高可用性

UE-V の [設定] のストレージの場所と設定テンプレートカタログは、書き込み可能な共有にユーザーデータを格納することをサポートします。 高可用性を確保するには、次の条件を満たしてください。

-   記憶域ボリュームに NTFS ファイルシステムを設定します。

-   共有では分散ファイルシステム (DFS) を使用できますが、制限があります。
特に、分散ファイルシステムのレプリケーション (DFS-R) では、分散ファイルシステムの名前空間 (DFS-R) を使用するか、またはそれを使わずに単一のターゲット構成がサポートされます。
同様に、DFS-R でサポートされているターゲット構成は1つだけです。
詳細については、複製された[ユーザープロファイルデータに関する microsoft のサポート声明](https://go.microsoft.com/fwlink/p/?LinkId=313991)と、 [dfs および dfs 展開シナリオの microsoft サポートポリシーに関する情報](https://support.microsoft.com/kb/2533009)も参照してください。

    また、SYSVOL はレプリケーション用に DFS を使用するため、UE-V データファイルレプリケーションでは SYSVOL を使用できません。

-   [Ue-v の [設定の保存場所](https://technet.microsoft.com/library/dn458891.aspx#ssl)] で指定されている共有アクセス許可と NTFS アクセス制御リスト (acl) を構成します。

-   UE-V Agent と共にファイルサーバークラスタリングを使用して、通信エラーが発生したときにユーザー状態データのコピーへのアクセスを提供します。

-   クラスター化された共有、DFS 共有、またはその両方に設定の記憶域パスデータ (ユーザーデータ) と設定テンプレートカタログテンプレートを保存できます。

### <a href="" id="clocksync"></a>コンピューターの時計を同期させる (UE-V 設定の同期)

UE-V エージェントを実行するコンピューターは、一貫した設定エクスペリエンスを維持するために、タイムサーバーを使用する必要があります。 UE-V はタイムスタンプを使用して、設定の保存場所から設定を同期する必要があるかどうかを判断します。 コンピューターの時計が間違っている場合は、古い設定で新しい設定が上書きされる可能性があります。また、新しい設定が、設定の保存場所に保存されないことがあります。

## <a href="" id="prereqs"></a>UE-V の前提条件とサポートされる構成を確認する


続行する前に、お使いの環境で UE-V を実行するための要件が含まれていることを確認してください。

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>オペレーティング システム</strong></th>
<th align="left"><strong>エディション</strong></th>
<th align="left"><strong>Service pack</strong></th>
<th align="left"><strong>システムアーキテクチャ</strong></th>
<th align="left"><strong>Windows PowerShell</strong></th>
<th align="left"><strong>Microsoft .NET Framework</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows 7</p></td>
<td align="left"><p>Ultimate、Enterprise、または Professional エディション</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
<td align="left"><p>Windows PowerShell 3.0 以降</p></td>
<td align="left"><p>.NET Framework 4.5 以上 (UE-V 2.1 の場合)</p>
<p>UE-V 2.0 向けの .NET Framework 4 以上。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2008 R2</p></td>
<td align="left"><p>標準、エンタープライズ、データセンター、または Web サーバー</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 ビット</p></td>
<td align="left"><p>Windows PowerShell 3.0 以降</p></td>
<td align="left"><p>.NET Framework 4.5 以上 (UE-V 2.1 の場合)</p>
<p>UE-V 2.0 向けの .NET Framework 4 以上。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 8 および Windows 8.1</p></td>
<td align="left"><p>Enterprise または Pro</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
<td align="left"><p>Windows PowerShell 3.0 以降</p></td>
<td align="left"><p>.NET Framework 4.5 以降</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 10、1607以前のバージョン</p>
<div class="alert">
<strong>注</strong><br/><p>UE-V 2.1 SP1 のみがサポートされている Windows 10、1607以前のバージョン</p>
</div>
<div>

</div></td>
<td align="left"><p>Enterprise または Pro</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
<td align="left"><p>Windows PowerShell 3.0 以降</p></td>
<td align="left"><p>.NET Framework 4.6</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012 および Windows Server 2012 R2</p></td>
<td align="left"><p>標準またはデータセンター</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>64 ビット</p></td>
<td align="left"><p>Windows PowerShell 3.0 以降</p></td>
<td align="left"><p>.NET Framework 4.5 以降</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2016</p></td>
<td align="left"><p>標準またはデータセンター</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>64 ビット</p></td>
<td align="left"><p>Windows PowerShell 3.0 以降</p></td>
<td align="left"><p>.NET Framework 4.6 以降</p></td>
</tr>
</tbody>
</table>



また。。。

-   **MDOP ライセンス:** この技術は、Microsoft デスクトップ最適化パック (MDOP) に含まれています。 企業のお客様は、Microsoft ソフトウェアアシュアランスで MDOP を入手できます。 Microsoft ソフトウェアアシュアランスの詳細と MDOP の入手方法については、「MDOP の入手方法」を参照してください https://go.microsoft.com/fwlink/p/?LinkId=322049) 。

-   インストールする任意のコンピューターの**管理者資格情報**

**注**  

-   WIndows 10 バージョン1607以降では、UE-V は[windows 10 For Enterprise](https://www.microsoft.com/WindowsForBusiness/windows-for-enterprise)に含まれており、Microsoft デスクトップ最適化パックの一部ではなくなっています。

-   UE-V Agent の UE-V Windows PowerShell 機能を有効にするには、.NET Framework 4 以上と Windows PowerShell 3.0 以降が必要です。 [ここ](https://go.microsoft.com/fwlink/?LinkId=309609)に Windows PowerShell 3.0 をダウンロードしてください。

-   Windows 7 または Windows Server 2008 R2 オペレーティングシステムを実行しているコンピューターに、.NET Framework 4 または .NET Framework 4.5 をインストールします。 Windows 8、Windows 8.1、Windows Server 2012 オペレーティングシステムには、.NET Framework 4.5 がインストールされています。 Windows 10 オペレーティングシステムには、.NET Framework 4.6 がインストールされています。
-   必須プロファイルの "ローミングキャッシュの削除" ポリシーは、UE-V でサポートされていないため、使用できません。



UE-V に固有の特殊なランダムアクセスメモリ (RAM) 要件はありません。

### 同期プロバイダーによる設定の同期

同期プロバイダーは、ユーザーの既定の設定です。この設定では、次のような場合に、ローカルキャッシュを設定の保存場所と同期します。

-   ログオン/ログオフ

-   ロック/ロック解除

-   リモートデスクトップの接続/切断

-   アプリケーションを開く/閉じる

スケジュールされたタスクは、この設定の同期を30分ごとに、または特定のアプリケーションの特定のトリガーイベントを使用して管理します。 詳細については、「 [ue-v のスケジュールされたタスクの頻度を変更する](changing-the-frequency-of-ue-v-2x-scheduled-tasks-both-uevv2.md)」を参照してください。

UE-V Agent は、常に企業ネットワーク (リモートコンピューターおよびノート pc) に接続されていないコンピューター、および常にネットワークに接続されているコンピューター (Windows Server とホスト仮想デスクトップインターフェイス (VDI) セッションを実行しているコンピューター) のユーザー設定を同期します。

**常に利用可能な接続を備えたコンピューターの同期:** 常にネットワークに接続されているコンピューターで UE-V を使用する場合は、 *Syncmethod = None*パラメーターを使用して設定を同期するように ue-v agent を構成する必要があります。これにより、設定ストレージサーバーは標準ネットワーク共有として扱われます。 この構成では、アプリケーション設定のインポートが遅延しているかどうかを通知するように UE-V Agent を構成できます。

次のいずれかの方法を使用して、この構成を有効にします。

-   UE-V のインストール中に、コマンドプロンプトで、またはバッチファイルで AgentSetup.exe パラメーター *Syncmethod = None*を設定します。 詳細につい[ては、Ue-v agent を使用して展開して](https://technet.microsoft.com/library/dn458891.aspx#agent)ください。

-   UE-V のインストール後、System Center 2012 構成マネージャーまたは MDOP ADMX テンプレートの設定管理機能を使用して、 *Syncmethod = None*構成をプッシュします。

-   Windows PowerShell または Windows Management Instrumentation (WMI) を使って、 *Syncmethod = None*構成を設定します。

    **注**  
    これらの最後の2つの方法は、プールされた仮想デスクトップインフラストラクチャ (VDI) 環境では動作しません。



設定が同期を開始するには、コンピューターを再起動する必要があります。

**注**  
*Syncmethod = None*を設定すると、設定の変更はサーバーに直接保存されます。 設定の記憶域パスへのネットワーク接続が見つからない場合、設定の変更はデバイスにキャッシュされ、次に同期プロバイダーを実行するときに同期されます。 設定の保存パスが見つからず、ログオフ時にプールされた VDI 環境からユーザープロファイルが削除された場合、設定の変更は失われ、ユーザーはコンピューターが設定の記憶域パスに再接続されたときに変更を再適用する必要があります。



**外部同期エンジンの同期:***Syncmethod = External* parameter は、ユーザーコンピューターのローカルフォルダーに ue-v 設定が書き込まれるかどうかを指定します。次に、任意の外部同期エンジン (OneDrive for Business、ワークフォルダー、Sharepoint、Dropbox など) を使って、これらの設定をユーザーがアクセスするさまざまなコンピューターに適用することができます。

**共有 VDI セッションのサポート:** UE-V 2.1 および 2.1 SP1 は、エンドユーザー間で共有される VDI セッションのサポートを提供します。 特殊な VDI テンプレートを登録して構成することができます。これにより、UE-V は永続的でない VDI セッションに対してすべての機能をそのまま維持できます。

**注**  
非永続的な VDI セッションで VDI モードを有効にしていない場合、一部の機能が機能しなくなります。たとえば、[バックアップ/復元や前回正常](https://technet.microsoft.com/library/dn878331.aspx)に動作していた既知の良好 (lkg) などです。



VDI テンプレートは、UE-V 2.1 および 2.1 SP1 で提供され Virtualization\\Templates\\VdiState.xml ます。通常はインストール後に使用できます。

### UE-V Generator のサポートに関する前提条件

カスタム設定の場所テンプレートを作成するために使用されるコンピューターに、UE-V Generator をインストールします。 このコンピューターでは、設定が同期されているアプリケーションを実行できる必要があります。 UE-V Generator ソフトウェアを実行しているコンピューターの管理者グループのメンバーである必要があります。

UE-V Generator は、NTFS ファイルシステムを使用するコンピューターにインストールする必要があります。 UE-V Generator ソフトウェアには、.NET Framework 4 が必要です。 詳細については、「[カスタムアプリケーションの ue-v を展開する](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)」を参照してください。

## この製品のその他のリソース


-   [Microsoft User Experience Virtualization (UE-V) 2. x](index.md)

-   [UE-V 2.x の概要](get-started-with-ue-v-2x-new-uevv2.md)

-   [UE-V 2. x の管理](administering-ue-v-2x-new-uevv2.md)

-   [UE-V 2. x のトラブルシューティング](troubleshooting-ue-v-2x-both-uevv2.md)

-   [UE-V 2.x のテクニカル リファレンス](technical-reference-for-ue-v-2x-both-uevv2.md)














