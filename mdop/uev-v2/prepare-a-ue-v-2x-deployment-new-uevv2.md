---
title: UE-V 2.x の展開の準備
description: UE-V 2.x の展開の準備
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
ms.openlocfilehash: 3e4d4b69975deda473372345733d8e8593a4775d
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910532"
---
# <a name="prepare-a-ue-v-2x-deployment"></a>UE-V 2.x の展開の準備


Microsoft User Experience Virtualization (UE-V) 2.0 または 2.1 を、ユーザーがエンタープライズでアクセスするデバイス間で設定を同期するソリューションとして展開する前に、いくつかの計画と準備を行う必要があります。 このトピックでは、展開が成功するために、実行する展開の種類と事前に行う準備を決定するのに役立ちます。

最初に、次の手順で展開するタスクをUE-V。

-   展開の計画UE-Vする

    何かを展開する前に、最初に少し計画を立て、展開する機能UE-V決定してください。 したがって、このページを離れる場合は、必ず戻ってきて、以下の計画情報を確認してください。

-   [UE-V 2.x の必要な機能を展開する](deploy-required-features-for-ue-v-2x-new-uevv2.md)

    すべてのUE-V展開には、次のアクティビティが必要です。

    -   [設定の保存場所を定義する](https://technet.microsoft.com/library/dn458891.aspx#ssl)

    -   [エージェントを展開し、UE-V構成をUE-Vする](https://technet.microsoft.com/library/dn458891.aspx#config)

    -   [同期された設定UE-V必要](https://technet.microsoft.com/library/dn458891.aspx#agent)があるすべてのユーザー コンピューターにエージェント エージェントをインストールする

-   必要に応じて、[カスタム アプリケーションUE-V 2.x を展開できます。](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)

    計画は、UE-V がカスタム アプリケーション (サード パーティ製またはビジネスライン) の設定の同期をサポートするかどうかを決定するのに役立ちます。これには、次の機能が必要UE-Vです。

    -   [UEV Generator をインストール](https://technet.microsoft.com/library/dn458942.aspx#uevgen) して、カスタム アプリケーション設定の同期に必要なカスタム設定の場所テンプレートを作成、編集、検証できます

    -   [ユーザー設定の場所テンプレートを作成するには](https://technet.microsoft.com/library/dn458942.aspx#createcustomtemplates)、UE-V Generator を使用します。

    -   [カスタム設定UE-V保存するために使用](https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue)するカスタム設定テンプレート カタログを展開する

このワークフロー図は、企業の展開とUE-Vの展開方法を決定する決定をUE-Vします。

![展開ワークフロー。](images/deploymentworkflow.png)

**展開の計画UE-V次の手順を実行します。** 最初に、少し計画を立て、展開するコンポーネントUE-V決定します。 展開の計画UE-Vには、次のことが含まれる。

-   [カスタム アプリケーションの設定を同期するかどうかを決定する](#deciding)

    これにより、展開中に UE-Vジェネレーターをインストールするかどうかを決定します。これにより、カスタム設定の場所テンプレートを作成できます。 次の手順が含まれます。

    展開で[自動的に同期](#autosyncsettings)される設定を確認UE-Vします。

    [他のアプリケーションに対して同期された設定が必要かどうかを判断します](#determinesettingssync)。

-   高可用性[や容量計画など、UE-V](#considerations)展開に関するその他の考慮事項を確認します。

-   [コンポーネントの前提条件とサポートされている構成を確認UE-V](#prereqs)

## <a name="decide-whether-to-synchronize-settings-for-custom-applications"></a><a href="" id="deciding"></a>カスタム アプリケーションの同期設定するかどうかを決定する


一部のUE-Vでは、多くの設定が自動的に同期されます。 ただし、他のアプリケーションUE-V(line-of-business アプリやサード パーティ製アプリなど)の設定を同期するために、ユーザー設定をカスタマイズすることもできます。

カスタム アプリケーションの設定UE-V同期するかどうかを決定することが、展開の計画の最もUE-Vです。 このセクションのトピックは、その決定に役立ちます。

### <a name="settings-that-are-automatically-synchronized-in-a-ue-v-deployment"></a><a href="" id="autosyncsettings"></a>設定展開で自動的に同期されるUE-V

このセクションでは、既定で同期される設定に関する情報を以下UE-V含めて説明します。

既定で設定が同期されているデスクトップ アプリケーション

Windows同期されるデスクトップ設定の設定

アプリ設定の同期をサポートWindowsステートメント

Microsoft Office で同期される特定の Microsoft Office 2013、Microsoft Office 2010、および Microsoft Office 200 UE-V 7 設定の完全なリストをダウンロードするには、「Microsoft Office のユーザー エクスペリエンス仮想化[(UE-V)](https://www.microsoft.com/download/details.aspx?id=46367)設定テンプレート」を参照してください。

### <a name="desktop-applications-synchronized-by-default-in-ue-v-21-and-ue-v-21-sp1"></a>デスクトップ アプリケーションは、既定で 2.1 および UE-V 2.1 SP1 UE-V同期されます。

UE-V 2.1 または 2.1 SP1 エージェントをインストールすると、これらの一般的な Microsoft アプリケーションの設定値をキャプチャする設定場所テンプレートの既定のグループが登録されます。

**ヒント**  
**Microsoft Office 2007**設定 同期 – UE-V 2.1 および 2.1 SP1 では、Office 2007 アプリケーションの設定場所テンプレートは既定では含まれません。 ただし、UE-V 2.0 以前Office 2007 テンプレートを使用し、UE-V テンプレート ギャラリーからテンプレート[を取得できます](https://go.microsoft.com/fwlink/p/?LinkID=246589)。



<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>アプリケーション カテゴリ</strong></th>
<th align="left"><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Office 2010 アプリケーション</p>
<p>( <a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> 同期された設定の一覧をダウンロード </a> する )</p></td>
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
<p>( <a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> 同期された設定の一覧をダウンロード </a> する )</p></td>
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
<p>Microsoft Office 2013 アップロード センター</p>
<p>Microsoft OneDrive 2013 の詳細</p>
<p>2013 UE-V 2.1 および 2.1 SP1 Microsoft Office設定の場所テンプレートには、Outlookが含まれます。 新しいメール、返信メール、転送メールの既定の署名設定の同期が追加されました。</p>
<div class="alert">
<strong>備考</strong><br/><p>ユーザー Outlook署名を同期するデバイスに対して、ユーザー プロファイルを作成Outlookがあります。 プロファイルが作成されていない場合、ユーザーは作成したプロファイルを作成し、そのデバイスOutlook再起動して署名の同期を有効にできます。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>ブラウザー のオプション: Internet Explorer 8、Internet Explorer 9、Internet Explorer 10、Internet Explorer 11</p></td>
<td align="left"><p>お気に入り、ホーム ページ、タブ、およびツールバー。</p>
<div class="alert">
<strong>備考</strong><br/><p>UE-V Cookie の設定をローミングInternet Explorerしない。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>Windowsアクセサリ</p></td>
<td align="left"><p>Microsoft 電卓、メモ帳、WordPad。</p></td>
</tr>
</tbody>
</table>



**備考**  
UE-V 2.1 SP1 では、以前のオペレーティング システムの Microsoft 電卓とWindows 10のMicrosoft 電卓を同期させる必要があります。



### <a name="desktop-applications-synchronized-by-default-in-ue-v-20"></a>デスクトップ アプリケーションは、既定で 2.0 UE-V同期されます

UE-V 2.0 Agent をインストールすると、これらの一般的な Microsoft アプリケーションの設定値をキャプチャする設定場所テンプレートの既定のグループが登録されます。

**ヒント**  
**Microsoft Office 2013 設定 同期**– UE-V 2.0 では、Office 2013 アプリケーションの設定場所テンプレートは既定では含まれませんが[、UE-V](https://go.microsoft.com/fwlink/p/?LinkID=246589)テンプレート ギャラリーからダウンロードできます。 [2013 Office 2.0 との同期UE-V 2013](synchronizing-office-2013-with-ue-v-20-both-uevv2.md)の設定を同期するサポートされているテンプレートOffice提供します。



<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>アプリケーション カテゴリ</strong></th>
<th align="left"><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Office 2007 アプリケーション</p>
<p>( <a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> 同期された設定の一覧をダウンロード </a> する )</p></td>
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
<p>( <a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> 同期された設定の一覧をダウンロード </a> する )</p></td>
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
<td align="left"><p>ブラウザー のオプション: Internet Explorer 8、Internet Explorer 9、およびInternet Explorer 10</p></td>
<td align="left"><p>お気に入り、ホーム ページ、タブ、およびツールバー。</p>
<div class="alert">
<strong>備考</strong><br/><p>UE-V Cookie の設定をローミングInternet Explorerしない。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>Windowsアクセサリ</p></td>
<td align="left"><p>Microsoft 電卓、メモ帳、WordPad。</p></td>
</tr>
</tbody>
</table>



### <a name="windows-settings-synchronized-by-default"></a><a href="" id="autosyncsettings2"></a>Windows設定が既定で同期されている

UE-Vには、これらの設定の設定値をキャプチャする設定場所テンプレートWindowsがあります。

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
<th align="left">適用する</th>
<th align="left">エクスポートオン</th>
<th align="left">既定の状態</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>デスクトップの背景</p></td>
<td align="left"><p>現在アクティブなデスクトップの背景または壁紙。</p></td>
<td align="left"><p>ログオン、ロック解除、リモート接続、スケジュールされたタスクイベント。</p></td>
<td align="left"><p>ログオフ、ロック、リモート切断、ユーザーが [会社の同期] センターで [今すぐ同期 <strong> 設定]、またはスケジュールされたタスクの間隔 </strong></p></td>
<td align="left"><p>有効</p></td>
</tr>
<tr class="even">
<td align="left"><p>コンピューターの簡単操作</p></td>
<td align="left"><p>アクセシビリティと入力設定、Microsoft Magnifier、ナレーター、およびオンスクリーン キーボード。</p></td>
<td align="left"><p>ログオンのみ。</p></td>
<td align="left"><p>ログオフ、ユーザーが [会社の同期] センターで [今すぐ同期 <strong> </strong> 設定]、またはスケジュールされたタスクの間隔</p></td>
<td align="left"><p>有効</p></td>
</tr>
<tr class="odd">
<td align="left"><p>デスクトップ設定</p></td>
<td align="left"><p>スタート メニュータスク バーの設定、フォルダー オプション、既定のデスクトップ アイコン、追加のクロック、地域と言語の設定。</p></td>
<td align="left"><p>ログオンのみ。</p></td>
<td align="left"><p>ログオフ、ユーザーが [会社の同期] センターで [今 <strong> </strong> すぐ同期設定]、またはスケジュールされたタスク</p></td>
<td align="left"><p>有効</p></td>
</tr>
</tbody>
</table>



**備考**  
スタート画面Windows 8、UE-V場所など、スタート画面に関連する設定をローミングしない場合があります。 さらに、UE-Vタスク バーアイテムの同期やファイル ショートカットWindowsサポートされていません。



**重要**  
UE-V 2.1 SP1 は、タスク バーの設定をデバイス間Windows 10します。 ただし、UE-V以前のオペレーティング システムを実行しているデバイスWindows 10タスク バーの設定は同期されません。



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
<th align="left">キャプチャ</th>
<th align="left">設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>アプリケーション設定</strong></p></td>
<td align="left"><p>Windows アプリ  </p></td>
<td align="left"><p>アプリを閉じる</p>
<p>Windows設定変更イベント</p></td>
<td align="left"><p>起動時にUE-Vアプリ モニターを起動する</p>
<p>アプリを開く</p>
<p>Windowsアプリ設定変更イベント</p>
<p>設定パッケージの到着</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>デスクトップ アプリケーション</p></td>
<td align="left"><p>アプリケーションが閉じる</p></td>
<td align="left"><p>アプリケーションが開き、閉じる</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>デスクトップ設定</strong></p></td>
<td align="left"><p>デスクトップの背景</p></td>
<td align="left"><p>ロックまたはログオフ</p></td>
<td align="left"><p>ログオン、ロック解除、リモート接続、新しいパッケージ到着の通知、ユーザーが [会社のサービス センターで今すぐ同期設定クリックするか、スケジュールされたタスクの実行を <strong> </strong> クリックします。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>簡単操作 (一般的なアクセシビリティ、ナレーター、拡大鏡、スクリーン キーボード)</p></td>
<td align="left"><p>ロックまたはログオフ</p></td>
<td align="left"><p>ログオン</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p>簡単操作 (シェル - オーディオ、アクセシビリティ、キーボード、マウス)</p></td>
<td align="left"><p>ロックまたはログオフ</p></td>
<td align="left"><p>ログオン、ロック解除、リモート接続、新しいパッケージ到着の通知、ユーザーが [会社] センターで [今すぐ同期] をクリック設定スケジュールされたタスクの <strong> </strong> 実行</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>デスクトップ設定</p></td>
<td align="left"><p>ロックまたはログオフ</p></td>
<td align="left"><p>ログオン</p></td>
</tr>
</tbody>
</table>



### <a name="ue-v-support-for-windows-apps"></a>UE-VアプリのWindowsサポート

アプリWindows、アプリ開発者は同期される設定を指定します。 設定の同期にWindowsアプリを指定できます。

コンピューターの設定をパッケージ ファミリ名、有効な状態、有効なソースと同期できる Windows アプリの一覧を表示するには、Windows PowerShell コマンド プロンプトで次Windows PowerShell入力します。 `Get-UevAppxPackage`

**備考**  
このWindows 8、UE-Vユーザーがサインイン資格情報を Microsoft アカウントにリンクしている場合、Windowsアプリの設定は同期されません。 このリンクは、アプリ設定の同期をMicrosoft OneDrive、UE-Vの同期を無効にWindows同期します。



### <a name="ue-v-support-for-roaming-printers"></a>UE-Vプリンターのサポート

UE-V 2.1 SP1 では、ネットワーク プリンターをデバイス間でローミングして、ユーザーがネットワーク上の任意のデバイスにログオンするときにネットワーク プリンターにアクセスできます。 これには、既定として設定したプリンターのローミングが含まれます。

プリンターでのプリンターのローミングUE-V、次のいずれかのシナリオが必要です。

-   印刷サーバーは、新しいデバイスにローミングするときに必要なドライバーをダウンロードできます。

-   ローミング ネットワーク プリンターのドライバーは、そのネットワーク プリンターにアクセスする必要があるすべてのデバイスに事前にインストールされます。

-   プリンター ドライバーは、更新プログラムからWindowsできます。

**備考**  
プリンター UE-V移動機能**では、プリンター**の設定や基本設定 (両面印刷など) はローミングしない。



### <a name="determine-whether-you-need-settings-synchronized-for-other-applications"></a><a href="" id="determinesettingssync"></a>他のアプリケーションに対して同期された設定が必要かどうかを判断する

UE-V 展開で自動的に同期される設定を確認した後、エンタープライズ全体に UE-V を展開する方法が決定されますので、他のアプリケーションの設定を同期するかどうかを決定します。

管理者として、UE-V ソリューションに含めるデスクトップ アプリケーションを検討する場合は、ユーザーがカスタマイズできる設定と、アプリケーションが設定を保存する方法と場所を検討します。 一部のデスクトップ アプリケーションには、カスタマイズできる設定や、ユーザーが日常的にカスタマイズできる設定がある場合があります。 また、すべてのデスクトップ アプリケーション設定を複数のコンピューターまたは環境間で安全に同期できる場合があります。

一般に、次の条件を満たす設定を同期できます。

-   設定アクセス可能な場所に格納されているデータ。 たとえば、System32 またはレジストリの HKEY\_CURRENT\_USER (HKCU) セクションの外部に格納されている設定は同期されません。

-   設定特定のコンピューターに固有の値を指定します。 たとえば、ネットワーク構成またはハードウェア構成を除外します。

-   設定データを危険にさらさずにコンピューター間で同期できるデータ。 たとえば、データベース ファイルに格納されている設定は使用できません。

### <a name="checklist-for-evaluating-custom-applications"></a><a href="" id="checklistsettingssync"></a>カスタム アプリケーションを評価するためのチェックリスト

他のアプリケーションの設定を同期する必要がある場合は、このチェックリストを使用して、どのアプリケーションを含めるのか把握できます。

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
<td align="left"><p>このアプリケーションには、ユーザーがカスタマイズできる設定が含まれているか。</p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>ユーザーがこれらの設定を同期することが重要ですか?</p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>これらのユーザー設定は、アプリケーション管理または設定ポリシー ソリューションによって既に管理されていますか? UE-V起動時にアプリケーション設定を適用し、Windows、ロック解除、またはリモート接続イベント時に設定を適用します。 他の設定共有ソリューションUE-V使用すると、同期された設定間で矛盾が発生する可能性があります。</p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>アプリケーション設定はコンピューターに固有の設定ですか? ハードウェアまたは特定のコンピューター構成に関連付けられているアプリケーションの基本設定とカスタマイズは、セッション間で一貫して同期されないので、アプリケーション エクスペリエンスが低下する可能性があります。</p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>アプリケーションは、Program Files ディレクトリまたは Users [User name] Strong AppData strong LocalLow ディレクトリにあるファイル ディレクトリに設定を <strong> </strong> &lt; &gt; </strong> &lt; &gt; 保存 </strong> しますか? これらの場所のどちらかに格納されているアプリケーション データは、通常、このデータはコンピューターに固有のデータか、データが大きすぎて同期できないので、ユーザーと同期する必要はありません。</p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>アプリケーションは、同期しない他のアプリケーション データを含む設定をファイルに保存しますか? UE-Vファイルを 1 つの単位として同期します。 設定が設定以外のアプリケーション データを含むファイルに格納されている場合、この追加データを同期すると、アプリケーション エクスペリエンスが低下する可能性があります。</p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>設定を含むファイルのサイズを指定します。 設定の同期のパフォーマンスは、大きなファイルの影響を受ける可能性があります。 大きなファイルを含め、設定の同期のパフォーマンスに影響を与える可能性があります。</p></td>
</tr>
</tbody>
</table>



## <a name="other-considerations-when-preparing-a-ue-v-deployment"></a><a href="" id="considerations"></a>展開を準備する際のUE-V考慮事項


また、次の点も考慮して、展開の準備を行UE-V。

-   [資格情報の同期の管理](#creds)

-   [Windows設定の同期](#appxsettings)

-   [カスタム UE-V設定の場所テンプレート](#custom)

-   [意図しないユーザー設定の構成](#prevent)

-   [パフォーマンスと容量](#capacity)

-   [高可用性](#high)

-   [コンピューターのクロック同期](#clocksync)

### <a name="managing-credentials-synchronization-in-ue-v-21-and-ue-v-21-sp1"></a><a href="" id="creds"></a>2.1 および UE-V 2.1 SP1 UE-V資格情報の同期の管理

Microsoft Outlook Lync を含む多くのエンタープライズ アプリケーションは、ログイン時にユーザーにドメイン資格情報の入力を求めるプロンプトを表示します。 ユーザーは、資格情報をディスクに保存して、これらのアプリケーションを開く度に入力する必要を防ぐオプションがあります。 ローミング資格情報の同期を有効にすると、ユーザーは資格情報を 1 つのコンピューターに保存し、環境で使用するすべてのコンピューターで資格情報を再入力しないようにできます。 ユーザーは、一部のドメイン資格情報を 2.1 UE-V 2.1 SP1 と同期できます。

**重要**  
資格情報の同期は既定で無効になっています。 この機能を実装するには、展開中に資格情報の同期を明示的に有効にする必要があります。



UE-V 2.1 および 2.1 SP1 はエンタープライズ資格情報を同期できますが、ローカル コンピューターでのみ使用するための資格情報はローミングできません。

資格情報は同期設定で、同期後に初めてコンピューターにログインした場合にプロファイルにUE-Vされます。

資格情報の同期は、既定で無効になっている独自の設定場所テンプレートによって管理されます。 このテンプレートは、他のテンプレートと同じ方法で有効または無効にできます。 この機能のテンプレート識別子は RoamingCredentialSettings です。

**重要**  
ご使用の環境で Active Directory 資格情報ローミングを使用している場合は、資格情報の移動テンプレートを有効にUE-V勧めします。



資格情報の同期を有効にするには、次のいずれかの方法を使用します。

-   会社設定センター

-   PowerShell

-   グループ ポリシー

**備考**  
資格情報は同期中に暗号化されます。



[[会社設定センター](https://technet.microsoft.com/library/dn458903.aspx)**: 資格情報**の同期を有効にするには、[設定] の下の [Windows 設定資格情報の移動] チェック ボックスをオンにします。 ボックスのチェックを外して無効にします。 このチェック ボックスは、Microsoft アカウントを使用設定設定を同期するようにアカウントが構成されていない場合にのみ、Company 設定 センターに表示されます。

[PowerShell](https://technet.microsoft.com/library/dn458937.aspx)**: この** PowerShell コマンドレットを使用すると、資格情報の同期が有効になります。

``` syntax
Enable-UevTemplate RoamingCredentialSettings
```

この PowerShell コマンドレットは、資格情報の同期を無効にします。

``` syntax
Disable-UevTemplate RoamingCredentialSettings
```

[グループ ポリシー](https://technet.microsoft.com/library/dn458893.aspx)**: グループ** ポリシーを使用して資格情報の同期を有効にするには、最新の [MDOP ADMX](https://go.microsoft.com/fwlink/p/?LinkId=393944) テンプレートを展開する必要があります。 資格情報の同期は、ユーザー設定でWindowsされます。 グループ ポリシーを使用してこの機能を管理するには、同期設定ポリシー Windows有効にします。

1.  グループ ポリシー エディターを開き、[ユーザー構成] – [管理用テンプレート] **( [Windows コンポーネント] の**Microsoft User Experience Virtualization。

2.  [設定の同期]**をダブルクリックWindowsします**。

3.  このポリシーが有効になっている場合は、[資格情報の移動] チェック**** ボックスをオンにして資格情報の同期を有効にするか、資格情報の同期をオフにして無効にできます。

4.  **[OK]** をクリックします。

### <a name="credential-locations-synchronized-by-ue-v"></a>資格情報の場所は、ユーザーによって同期UE-V

アプリケーションによって次の場所に保存された資格情報ファイルが同期されます。

-   %UserProfile%\\AppData\\Roaming\\Microsoft\\Credentials\\

-   %UserProfile%\\AppData\\Roaming\\Microsoft\\Crypto\\

-   %UserProfile%\\AppData\\Roaming\\Microsoft\\Protect\\

-   %UserProfile%\\AppData\\Roaming\\Microsoft\\SystemCertificates\\

他の場所に保存された資格情報は、ユーザーが同期UE-V。

### <a name="windows-app-settings-synchronization"></a><a href="" id="appxsettings"></a>Windows設定の同期

UE-VアプリWindows同期を管理するには、次の 3 つの方法があります。

-   **アプリWindows同期:** アプリの同期を許可またはWindowsする

-   **Windowsアプリの一覧:** アプリの一覧をWindowsする

-   **リストに登録されていない既定の同期動作:** アプリリストに含Windowsアプリの同期動作をWindowsします。

詳細については、「アプリ一覧」[をWindowsしてください](https://technet.microsoft.com/library/dn458925.aspx#win8applist)。

### <a name="custom-ue-v-settings-location-templates"></a><a href="" id="custom"></a>カスタム UE-V設定の場所テンプレート

カスタム アプリケーションの設定をUE-Vする場合は、UE-V Generator を使用して、それらのデスクトップ アプリケーションのカスタム設定場所テンプレートを作成します。 テスト環境でカスタム設定場所テンプレートを作成してテストした後、設定場所テンプレートを企業のコンピューターに展開できます。

カスタム設定の場所テンプレートは、System Center Configuration Manager などのエンタープライズ ソフトウェア配布 (ESD) メソッド、基本設定、または UE-V 設定テンプレート カタログの構成など、既存の展開インフラストラクチャと一緒に展開する必要があります。 Configuration Manager またはグループ ポリシーを使用して展開されるテンプレートは、WMI またはグループ ポリシーを使用UE-V登録Windows PowerShell。

カスタム設定の場所テンプレートの詳細については[、「Deploy UE-V 2.x for Custom Applications」を参照してください](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)。 Configuration Manager での構成の使用UE-V詳細については[、「Configurationing UE-V 2.x with System Center Configuration Manager 2012」](configuring-ue-v-2x-with-system-center-configuration-manager-2012-both-uevv2.md)を参照してください。

### <a name="prevent-unintentional-user-settings-configuration"></a><a href="" id="prevent"></a>意図しないユーザー設定の構成を防止する

UE-V設定の保存場所から新しいユーザー設定情報をダウンロードし、これらのインスタンスのローカル コンピューターに設定を適用します。

-   登録されたテンプレートを持つアプリケーションが開始UE-Vです。

-   ユーザーがコンピューターにログオンする場合。

-   ユーザーがコンピューターのロックを解除するとします。

-   インストールされているリモート デスクトップ コンピューターに接続UE-V。

-   同期コントローラー アプリケーションのスケジュールされたタスクが実行される場合。

コンピューター UE-Vコンピューター B にインストールされ、アプリケーションに必要な設定がコンピューター A にインストールされている場合は、コンピューター A が最初にアプリケーションを開いて閉じる必要があります。 最初にコンピューター B でアプリケーションを開いて閉じた場合、コンピューター A のアプリケーション設定はコンピューター B のアプリケーション設定に構成されます。設定 は、アプリケーションごとにコンピューター間で同期されます。 時間がたつ間に、設定はコンピューター間で一貫性が保たれ、優先設定で開いて閉じられます。

このシナリオは、ユーザー設定Windows適用されます。 コンピューター B Windowsの設定がコンピューター A の Windows 設定と同じにする必要がある場合、ユーザーはログオンしてコンピューター A からログオフする必要があります。

ユーザーが必要なユーザー設定が誤った順序で適用されている場合は、設定が上書きされたコンピューター上の特定のアプリケーションまたは Windows 構成に対して復元操作を実行することで、ユーザーの設定を復元できます。 詳細については、「Manage [Administrative Backup and Restore in UE-V 2.x」を参照してください](manage-administrative-backup-and-restore-in-ue-v-2x-new-topic-for-21.md)。

### <a name="performance-and-capacity-planning"></a><a href="" id="capacity"></a>パフォーマンスと容量の計画

標準のディスク容量とネットワークUE-V監視を使用して、ユーザーの要件を指定します。

UE-V設定パッケージの記憶域にサーバー メッセージ ブロック (SMB) 共有を使用します。 設定パッケージのサイズは、各アプリケーションの設定情報によって異なります。 ほとんどの設定パッケージは小さいですが、デスクトップ イメージなどの潜在的に大きなファイルを同期すると、パフォーマンスが低下する可能性があります。特に低速なネットワークではパフォーマンスが低下します。

ネットワーク待機時間の問題を軽減するには、ユーザーのコンピューターが存在する同じローカル ネットワーク上に設定の保存場所を作成します。 設定の保存場所には、ユーザーごとに 20 MB のディスク領域を使用することをお勧めします。

既定では、UE-Vが 2 秒後にタイム アウトし、大きな設定パッケージによる過度の遅延を防ぐ必要があります。 グループ ポリシー オブジェクトを使用して、SyncMethod=SyncProvider 設定 [を構成できます](https://technet.microsoft.com/library/dn458893.aspx)。

### <a name="high-availability-for-ue-v"></a><a href="" id="high"></a>ユーザーの高可用性UE-V

このUE-V設定の保存場所と設定テンプレート カタログでは、書き込み可能な共有にユーザー データを格納できます。 高可用性を確保するには、次の条件に従います。

-   NTFS ファイル システムを使用してストレージ ボリュームを書式設定します。

-   共有では分散ファイル システム (DFS) を使用できますが、制限があります。
具体的には、分散ファイル システム名前空間 (DFS-N) の使用または指定なしの分散ファイル システム レプリケーション (DFS-R) 単一ターゲット構成がサポートされています。
同様に、DFS-N では単一のターゲット構成だけがサポートされます。
詳細については、「レプリケートされたユーザー プロファイル データに関する [Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=313991) のサポート ステートメント」および [「DFS-R および DFS-N](https://support.microsoft.com/kb/2533009)展開シナリオの Microsoft サポート ポリシーに関する情報」を参照してください。

    また、SYSVOL はレプリケーションに DFS-R を使用しますので、SYSVOL はデータ ファイルのレプリケーションUE-V使用できません。

-   [「2.x](https://technet.microsoft.com/library/dn458891.aspx#ssl)の共有の場所の展開」で指定されている共有アクセス許可と NTFS アクセス制御リスト (ACL) を設定 Storage構成UE-Vします。

-   通信エラーが発生した場合UE-V状態データのコピーへのアクセスを提供するには、ファイル サーバー クラスタリングを UE-V エージェントと共に使用します。

-   設定ストレージ パス データ (ユーザー データ) と設定テンプレート カタログ テンプレートは、クラスター化された共有、DFS-N 共有、または両方に保存できます。

### <a name="synchronize-computer-clocks-for-ue-v-settings-synchronization"></a><a href="" id="clocksync"></a>コンピューターのクロックを同期して、UE-V同期する

クライアント エージェントを実行するUE-Vは、一貫性のある設定エクスペリエンスを維持するためにタイム サーバーを使用する必要があります。 UE-Vタイム スタンプを使用して、設定を保存場所から同期する必要があるかどうかを判断します。 コンピューターの時計が不正確な場合は、古い設定で新しい設定が上書きされる場合や、新しい設定が設定の保存場所に保存されない場合があります。

## <a name="confirm-prerequisites-and-supported-configurations-for-ue-v"></a><a href="" id="prereqs"></a>前提条件とサポートされている構成を確認UE-V


続行する前に、環境にこれらの要件が含まれる必要があります。UE-V。

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
<th align="left"><strong>サービス パック</strong></th>
<th align="left"><strong>システム アーキテクチャ</strong></th>
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
<td align="left"><p>Windows PowerShell 3.0 以上</p></td>
<td align="left"><p>.NET Framework 2.1 の場合は 4.5 UE-V以上です。</p>
<p>.NET Framework 2.0 の場合UE-V 4 以上。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2008 R2</p></td>
<td align="left"><p>標準、Enterprise、データセンター、または Web サーバー</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 ビット</p></td>
<td align="left"><p>Windows PowerShell 3.0 以上</p></td>
<td align="left"><p>.NET Framework 2.1 の場合は 4.5 UE-V以上です。</p>
<p>.NET Framework 2.0 の場合UE-V 4 以上。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 8とWindows 8.1</p></td>
<td align="left"><p>EnterpriseまたはPro</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
<td align="left"><p>Windows PowerShell 3.0 以上</p></td>
<td align="left"><p>.NET Framework 4.5 以上</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 10 1607 より前のバージョン</p>
<div class="alert">
<strong>備考</strong><br/><p>2.1 SP1 UE-V 1607 より前のバージョンWindows 10 2.1 SP1 のみサポート</p>
</div>
<div>

</div></td>
<td align="left"><p>EnterpriseまたはPro</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
<td align="left"><p>Windows PowerShell 3.0 以上</p></td>
<td align="left"><p>.NET Framework 4.6</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012およびWindows Server 2012 R2</p></td>
<td align="left"><p>標準またはデータセンター</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>64 ビット</p></td>
<td align="left"><p>Windows PowerShell 3.0 以上</p></td>
<td align="left"><p>.NET Framework 4.5 以上</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2016</p></td>
<td align="left"><p>標準またはデータセンター</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>64 ビット</p></td>
<td align="left"><p>Windows PowerShell 3.0 以上</p></td>
<td align="left"><p>.NET Framework 4.6 以上</p></td>
</tr>
</tbody>
</table>



また。。。

-   **MDOP ライセンス:** このテクノロジは、Microsoft デスクトップ最適化パック (MDOP) の一部です。 Enterprise顧客は、MDOP を使用してデータを取得マイクロソフト ソフトウェア アシュアランス。 MDOP の取得とマイクロソフト ソフトウェア アシュアランス詳細については、「How Do I Get MDOP ( 」 を参照してください https://go.microsoft.com/fwlink/p/?LinkId=322049) 。

-   **インストールする** コンピューターの管理資格情報

**備考**  

-   WIndows 10 バージョン 1607 より、UE-V は Windows 10 for [Enterprise](https://www.microsoft.com/WindowsForBusiness/windows-for-enterprise)に含まれており、Microsoft デスクトップ最適化パックの一部ではなくなりました。

-   UE-V Windows PowerShellエージェントのUE-V機能.NET Framework 4 以上Windows PowerShell 3.0 以上を有効にする必要があります。 ダウンロード Windows PowerShell 3.0[こちら](https://go.microsoft.com/fwlink/?LinkId=309609)。

-   .NET Framework 4 または .NET Framework 4.5 を、Windows 7 または Windows Server 2008 R2 オペレーティング システムを実行するコンピューターにインストールします。 オペレーティング Windows 8、Windows 8.1、Windows Server 2012には、.NET Framework 4.5 がインストールされています。 オペレーティング Windows 10 4.6 が.NET Framework付属しています。
-   必須プロファイルの "ローミング キャッシュの削除" ポリシーは、UE-Vでサポートされていないので、使用できません。



ユーザーに固有の特別なランダム アクセス メモリ (RAM) 要件UE-V。

### <a name="synchronization-of-settings-through-the-sync-provider"></a>同期プロバイダー設定の同期

同期プロバイダーは、ユーザーの既定の設定で、ローカル キャッシュとこれらのインスタンスの設定ストレージの場所を同期します。

-   ログオン/ログオフ

-   ロック/ロック解除

-   リモート デスクトップの接続/切断

-   アプリケーションを開く/閉じる

スケジュールされたタスクは、30 分ごとに、または特定のアプリケーションの特定のトリガー イベントを通じて、この設定の同期を管理します。 詳細については、「2.x スケジュールされたタスクの頻度[UE-V変更する」を参照してください](changing-the-frequency-of-ue-v-2x-scheduled-tasks-both-uevv2.md)。

UE-V エージェントは、常にエンタープライズ ネットワーク (リモート コンピューターとラップトップ) に接続されていないコンピューターと、ネットワークに常に接続されているコンピューター (Windows Server を実行し、仮想デスクトップ インターフェイス (VDI) セッションをホストするコンピューター) のユーザー設定を同期します。

**常に使用可能な接続を持つコンピューターの同期:** ネットワークに常に接続されているコンピューターで UE-V を使用する場合は、設定ストレージ サーバーを標準ネットワーク共有として扱う*SyncMethod=None*パラメーターを使用して設定を同期する UE-V エージェントを構成する必要があります。 この構成では、アプリケーションUE-Vインポートが遅延した場合に通知するようにエージェントを構成できます。

次のいずれかの方法でこの構成を有効にしてください。

-   インストールUE-V、コマンド プロンプトまたはバッチ ファイルで、AgentSetup.exe*パラメーター SyncMethod = None を設定します*。 [2.x エージェントUE-V展開すると、詳細](https://technet.microsoft.com/library/dn458891.aspx#agent)が提供されます。

-   インストールUE-V、System Center 2012 Configuration Manager または MDOP ADMX テンプレートの 設定 管理機能を使用して *、SyncMethod = None*構成をプッシュします。

-   *SyncMethod* = Windows none 構成Windows PowerShell設定するには、WINDOWS POWERSHELLまたは管理インストルメンテーション (WMI) を使用します。

    **備考**  
    これらの最後の 2 つの方法は、プールされた仮想デスクトップ インフラストラクチャ (VDI) 環境では機能しません。



設定が同期を開始する前にコンピューターを再起動する必要があります。

**備考**  
*SyncMethod = None を設定すると*、設定の変更はサーバーに直接保存されます。 設定ストレージ パスへのネットワーク接続が見つからない場合、設定の変更はデバイスにキャッシュされ、次回同期プロバイダーが実行されると同期されます。 設定ストレージ パスが見つからない場合に、ログオフ時にプールされた VDI 環境からユーザー プロファイルが削除されると、設定の変更は失われ、コンピューターが設定ストレージ パスに再接続するときに変更を再適用する必要があります。



**外部同期エンジンの同期:***SyncMethod=External*パラメーターは、UE-V 設定をユーザー コンピューターのローカル フォルダーに書き込む場合、外部同期エンジン (OneDrive for Business、ワーク フォルダー、Sharepoint、Dropbox など) を使用して、ユーザーがアクセスする別のコンピューターにこれらの設定を適用できます。

**共有 VDI セッションのサポート:** UE-V 2.1 および 2.1 SP1 は、エンド ユーザー間で共有される VDI セッションをサポートします。 特別な VDI テンプレートを登録および構成すると、永続的でない VDI セッションUE-V機能がそのまま保持されます。

**備考**  
非永続的 VDI セッションで VDI モードを有効にしない場合、バックアップ/復元や最後の既知の良好 [な機能 (LKG)](https://technet.microsoft.com/library/dn878331.aspx)など、特定の機能が機能しません。



VDI テンプレートは UE-V 2.1 および 2.1 SP1 で提供され、通常、インストール後にここで使用できます。C:\\Program Files\\Microsoft User Experience Virtualization\\Templates\\VdiState.xml

### <a name="prerequisites-for-ue-v-generator-support"></a>ジェネレーターのサポートUE-V前提条件

カスタム設定の場所UE-V作成するために使用するコンピューターに、コンピューターにジェネレーターをインストールします。 このコンピューターは、設定が同期されているアプリケーションを実行できる必要があります。 ジェネレーター ソフトウェアを実行するコンピューターの Administrators グループのUE-V必要があります。

NTFS UE-Vを使用するコンピューターにジェネレーターをインストールする必要があります。 ジェネレーター UE-V 4 が必要.NET Frameworkです。 詳細については、「Deploy [UE-V 2.x for Custom Applications 」を参照してください](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)。

## <a name="other-resources-for-this-product"></a>この製品のその他のリソース


-   [Microsoft User Experience Virtualization (UE-V) 2.x](index.md)

-   [UE-V 2.x の概要](get-started-with-ue-v-2x-new-uevv2.md)

-   [UE-V 2.x の管理](administering-ue-v-2x-new-uevv2.md)

-   [UE-V 2.x のトラブルシューティング](troubleshooting-ue-v-2x-both-uevv2.md)

-   [UE-V 2.x のテクニカル リファレンス](technical-reference-for-ue-v-2x-both-uevv2.md)














