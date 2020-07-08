---
title: MED-V ワークスペースの構成設定の管理
description: MED-V ワークスペースの構成設定の管理
author: dansimp
ms.assetid: 517d04de-c31f-4b50-b2b3-5f8c312ed37b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 97add695f605b71547b564789cce07a1d58763f2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826157"
---
# MED-V ワークスペースの構成設定の管理


Microsoft Enterprise デスクトップ仮想化 (MED-V) 2.0 では、構成設定がレジストリに格納されます。 ここに記載されているレジストリに関する情報は、MED-V サービスをより適切に管理するのに役立ちます。

MED-V では、設定値を検索するときに、次の検索パスが使用されます。

MED は、まずマシンのポリシーを検索します。

値が見つからない場合、MED-V はユーザーポリシーで検索されます。

この値が見つからない場合、MED-V は HKEY \ _LOCAL \ _MACHINE \\ システムハイブで検索されます。

この値が見つからない場合、MED-V は HKEY \ _CURRENT USER registry ハイブで検索されます。

それでも値が見つからない場合、MED-V は既定値を使います。

一般的なベストプラクティスは、HKEY \ _LOCAL \ _MACHINE \\ システムハイブまたはコンピューターポリシーの値を設定することです。 ただし、エンドユーザーが特定の設定を構成できるようにする場合は、そのままにしておく必要があります。

**注**  
MED-V ワークスペースを展開する前に、スクリプトエディターを使って、MED-V ワークスペースパッケージャーで作成された Windows PowerShell スクリプト (ps1 ファイル) を変更できます。 詳細については、「 [Windows PowerShell を使用して詳細設定を構成する](configuring-advanced-settings-by-using-windows-powershell.md)」を参照してください。

MED-V のワークスペースを展開したら、レジストリエントリを編集することで、特定の MED-V 構成の設定を変更できます。



このセクションには、すべての構成可能な MED-V レジストリキーの一覧とその使用方法が記載されています。

## 診断キー


次の表では、HKEY \ _LOCAL \ _MACHINE ¥ $ ¥¥¥¥¥¥¥¥¥¥¥¥¥¥¥¥¥¥¥¥¥ # # # の各診断キーに関連付けられたレジストリ値に関する情報を提供します。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名前 </th>
<th align="left">型 </th>
<th align="left">データ/既定 </th>
<th align="left">説明 </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>EventLogLevel </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>既定値 = 3</p></td>
<td align="left"><p>イベントログに記録される情報の種類。 レベルには次の情報が含まれます: 0 (なし)、1 (エラー)、2 (警告)、3 (情報)、4 (デバッグ)。</p></td>
</tr>
</tbody>
</table>



## Fts キー


次の表では、HKEY \ _LOCAL \ _MACHINE \ ソフトウェア¥のバージョンに関連付けられているレジストリ値について説明します。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名前</th>
<th align="left">型</th>
<th align="left">データ/既定</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>AddUserToAdminGroupEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 0</p></td>
<td align="left"><p>初めてセットアップするときに、エンドユーザーを管理者&#39;s グループに自動的に追加するかどうかを構成します。 0 = false;1 = true。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false: 初回セットアップでは、管理者&#39;s グループにエンドユーザーが自動的に追加されることはありません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true: 初回セットアップでは、エンドユーザーが管理者&#39;s グループに自動的に追加されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ComputerNameMask </p></td>
<td align="left"><p>SZ</p></td>
<td align="left"><p>MEDV* </p></td>
<td align="left"><p>ゲスト仮想マシン&#39;s コンピューター名の作成に使用するコンピューター名マスク。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>マスクには、コンピューター名の一部としてユーザー名を挿入するための% username% タグを含めることができます。 同様に、% hostname% タグによって、ホストコンピューターの名前が挿入されます。</p>
<p>&quot; # &quot; マスク内の各文字はランダムな数字に置き換えられます。 マスクの末尾にあるアスタリスク (*) 文字は、ランダムな英数字に置き換えられます。</p>
<p>% Hostname% と% username% の特定の文字数は、角かっこを使ってキャプチャできます。 たとえば、 &quot; % username% [3] は、 &quot; ユーザー名の最初の3文字を使います。</p></td>
</tr>
<tr class="even">
<td align="left"><p>DeleteVMStateTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 90</p></td>
<td align="left"><p>初回セットアップで仮想マシンを削除しようとしたときのタイムアウト値 (秒単位)。 範囲 = 0 ~ 2147483647</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DetachVfdTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 120</p></td>
<td align="left"><p>初めてセットアップしたときに仮想マシンから仮想フロッピーディスクがデタッチされるまでのタイムアウト値 (秒単位)。 範囲 = 0 ~ 2147483647</p></td>
</tr>
<tr class="even">
<td align="left"><p>指定 Url </p></td>
<td align="left"><p>SZ</p></td>
<td align="left"><p></p></td>
<td align="left"><p>内部 web ページへのリンクを含むカスタマイズ可能な URL。また、初回セットアップのダイアログメッセージで表示されます。 </p></td>
</tr>
<tr class="odd">
<td align="left"><p>ExplorerTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 900</p></td>
<td align="left"><p>Windows エクスプローラーで最初にセットアップが待機するタイムアウト値 (秒)。 範囲 = 0 ~ 2147483647</p></td>
</tr>
<tr class="even">
<td align="left"><p>障害メッセージ </p></td>
<td align="left"><p>MULTI_SZ</p></td>
<td align="left"><p>リソースファイルにメッセージがあります </p></td>
<td align="left"><p>初めてセットアップを完了できない場合にエンドユーザーに表示されるカスタマイズ可能なメッセージ。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>GiveUserGroupRightsMaxRetryCount </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>既定値 = 3</p></td>
<td align="left"><p>MED-V がエンドユーザーグループの権限を付与する最大の回数。 指定された再試行値を超えても、エンドユーザーグループの権限を与えられていない場合は、仮想マシンの準備エラーが原因である可能性が高くなります。その後、MaxRetryCount 値が適用されます。 範囲 = 0 ~ 2147483647</p></td>
</tr>
<tr class="even">
<td align="left"><p>GiveUserGroupRightsTimeout </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 300</p></td>
<td align="left"><p>ユーザーグループの権限を付与するときのタイムアウト値 (秒単位) です。 範囲 = 0 ~ 2147483647</p></td>
</tr>
<tr class="odd">
<td align="left"><p>LogFilePaths </p></td>
<td align="left"><p>MULTI_SZ</p></td>
<td align="left"><p></p></td>
<td align="left"><p>初回のセットアップ時に、MED-V で収集されるログファイルパスの一覧。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>MaxPostponeTime </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 120</p></td>
<td align="left"><p>エンドユーザーが初めてセットアップを延期できる時間の最大数。 範囲 = 0 ~ 2147483647</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MaxRetryCount </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 3</p></td>
<td align="left"><p>各試行がソフトウェアエラー以外のエラーで終了した場合に、MED-V が仮想マシンの準備を試みる最大回数。 仮想マシンの準備に失敗し、初回のセットアップの再試行回数が超過した場合、MED-V は、エンドユーザーにエラーを通知し、再試行するオプションを提供しません。 MED-V が開始されるたびに、カウントが再設定されます。 範囲 = 0 ~ 2147483647</p></td>
</tr>
<tr class="even">
<td align="left"><p>モード </p></td>
<td align="left"><p>SZ</p></td>
<td align="left"><p>既定値 = 無人</p></td>
<td align="left"><p>初めて設定したユーザーとの対話方法を構成します。 次の値を指定できます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong>対話.</strong> エンドユーザーは、初回のセットアップ中に情報を入力する必要があります。</p>
<div class="alert">
<strong>注</strong><br/><p>Mini-setup ファイルを作成して、ミニセットアップでユーザーの入力を完了する必要があるようにする場合は、有人モードを選択する必要があり <strong> </strong> ます。または、初回のセットアップ時に問題が発生する可能性があります。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong>無人 </strong> 。 仮想マシンは、初回のセットアップ時にエンドユーザーには表示されませんが、最初のセットアップが開始される前にエンドユーザーに確認が求められます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong>Silent </strong> 。 仮想マシンは、初回のセットアップ時にエンドユーザーには表示されません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>NonInteractiveRetryTimeoutInc </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 15</p></td>
<td align="left"><p>セットアップを再実行するときの初回セットアップ対話モードでのタイムアウト値 (分単位) を指定します。 範囲 = 0 ~ 2147483647</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ノン Interactivetimeout </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 45</p></td>
<td align="left"><p>初回のセットアップ対話モードで初めてセットアップするときのタイムアウト値 (分単位)。 範囲 = 0 ~ 2147483647</p></td>
</tr>
<tr class="even">
<td align="left"><p>PostponeUtcDateTimeLimit </p></td>
<td align="left"><p>SZ</p></td>
<td align="left"><p></p></td>
<td align="left"><p>初めてセットアップを延期できる日付と時刻 (UTC 形式)。 &quot; &quot; 24 時間制の標準を使用して時間を指定して、yyyy-mm-dd hh: mm の形式で入力します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Retrymsg メッセージ </p></td>
<td align="left"><p>MULTI_SZ</p></td>
<td align="left"><p>リソースファイルにメッセージがあります </p></td>
<td align="left"><p>初めてセットアップするときにエンドユーザーに表示されるカスタマイズ可能なメッセージ。</p></td>
</tr>
<tr class="even">
<td align="left"><p>SetComputerNameEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 0</p></td>
<td align="left"><p>ゲストの Sysprep.inf ファイルの [UserData] セクションの下にある ComputerName エントリを、指定された ComputerNameMask に応じて更新するかどうかを構成します。   0 = false;1 = true。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false: Sysprep.inf ファイルの ComputerName エントリは、ComputerNameMask によって更新されません。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true: Sysprep.inf ファイルの ComputerName エントリは、ComputerNameMask に従って更新されます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SetJoinDomainEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 0</p></td>
<td align="left"><p>ゲストの Sysprep.inf ファイルの [Id] セクションにある JoinDomain 設定を、ホスト上の設定と一致するように更新する必要があるかどうかを構成します。  0 = false;1 = true。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false: Sysprep.inf ファイルの JoinDomain 設定は、ホストの設定に一致するように更新されません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true: Sysprep.inf ファイルの JoinDomain 設定が、ホストの設定と一致するように更新されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>SetMachineObjectOUEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 0</p></td>
<td align="left"><p>ゲストの Sysprep.inf ファイルの [識別] セクションにある MachineObjectOU 条件設定が、ホストに一致するように更新されるかどうかを構成します。  0 = false;1 = true。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false: Sysprep.inf ファイルの Machineの条件設定は、ホスト上の設定に一致するように更新されません。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true: Sysprep.inf ファイルの Machineの条件設定が、ホストの設定と一致するように更新されます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SetRegionalSettingsEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 0</p></td>
<td align="left"><p>ゲストの Sysprep.inf ファイルの [RegionalSettings] セクションの下にある設定が、ホストに一致するように更新されるかどうかを構成します。  0 = false;1 = true。</p>
<div class="alert">
<strong>注</strong><br/><p>既定では、ゲストのタイムゾーンの設定は、常にホストのタイムゾーンの設定と同期されます。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false: ゲストの Sysprep.inf ファイルの [RegionalSettings] セクションの下にある設定は、ホストに一致するように更新されません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true: ゲストの Sysprep.inf ファイルの [RegionalSettings] セクションの下にある設定が、ホストと一致するように更新されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>SetUserDataEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 0</p></td>
<td align="left"><p>ゲストの Sysprep.inf ファイルの [UserData] セクションにある FullName と OrgName の設定が、ホストの設定と一致するように更新されるかどうかを構成します。  0 = false;1 = true。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false: Sysprep.inf ファイルの FullName と OrgName の設定は、ホストの設定と一致するように更新されません。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true: Sysprep.inf ファイルの FullName と OrgName の設定が、ホストの設定と一致するように更新されます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>StartDialogMsg </p></td>
<td align="left"><p>MULTI_SZ</p></td>
<td align="left"><p>リソースファイルにメッセージがあります </p></td>
<td align="left"><p>初めてセットアップを開始する準備ができた時点でエンドユーザーに表示されるカスタマイズ可能なメッセージ。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>TaskCancelTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 30</p></td>
<td align="left"><p>1回目のセットアップで、キャンセル操作のために仮想マシンからの応答を待機するタイムアウト値 (秒単位)。 範囲 = 0 ~ 2147483647</p></td>
</tr>
<tr class="odd">
<td align="left"><p>TaskVMTurnOffTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 60</p></td>
<td align="left"><p>仮想マシンのシャットダウンが最初に実行されるときに設定されるタイムアウト値 (秒単位) です。 範囲 = 0 ~ 2147483647</p></td>
</tr>
<tr class="even">
<td align="left"><p>アップグレードタイムアウト</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 600</p></td>
<td align="left"><p>MED-V ゲストエージェントソフトウェアのアップグレードを試行するまでの時間 (秒単位) です。範囲 = 0 ~ 2147483647</p></td>
</tr>
</tbody>
</table>



## UserExperience キー


次の表では、HKEY \ _LOCAL \ _MACHINE \\ ¥ the _USER userexperience キーと、HKEY \ _CURRENT \ \ ソフトウェア¥のユーザーエクスペリエンスキーに関連付けられているレジストリ値について説明します。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名前</th>
<th align="left">型</th>
<th align="left">データ/既定</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Appはっこう Enabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>Default = 1</p></td>
<td align="left"><p>ゲストからホストへのアプリケーションのパブリケーションが有効であるかどうかを構成します。  0 = false;1 = true。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false: ゲストからホストへのアプリケーションの発行を無効にします。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true: ゲストからホストへのアプリケーションの発行を有効にします。</p></td>
</tr>
<tr class="even">
<td align="left"><p>AudioSharingEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>Default = 1</p></td>
<td align="left"><p>ゲストとホストの間でオーディオ i/o デバイスの共有が有効になっているかどうかを構成します。  0 = false;1 = true。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false: ゲストとホストの間のオーディオ i/o デバイスの共有を無効にします。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true: ゲストとホストの間でのオーディオ i/o デバイスの共有を有効にします。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>クリップボード共有の有効化 </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>Default = 1</p></td>
<td align="left"><p>ゲストとホストの間でクリップボードの共有が有効になっているかどうかを構成します。  0 = false;1 = true。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false: ゲストとホストの間でクリップボードの共有を無効にします。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true: ゲストとホストの間でクリップボードの共有を有効にします。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/値のタイムアウト</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 300</p></td>
<td align="left"><p>初回のセットアップ開始のダイアログがタイムアウトするまでの時間 (秒単位) です。範囲 = 0 ~ 2147483647</p></td>
</tr>
<tr class="odd">
<td align="left"><p>HideVmTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 30</p></td>
<td align="left"><p>フルスクリーンの仮想マシンのウィンドウが、長いログオン試行中にエンドユーザーから非表示になっているタイムアウト値 (分単位)。</p></td>
</tr>
<tr class="even">
<td align="left"><p>LogonStartEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>Default = 1</p></td>
<td align="left"><p>エンドユーザーがデスクトップにログオンしたとき、または最初のゲストアプリケーションが開始されたときにゲストを開始するかどうかを構成します。  0 = false;1 = true。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false: 最初のゲストアプリケーションが開始されたときにゲストが開始されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true: エンドユーザーがデスクトップにログオンしたときにゲストが開始されます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>プリンター共有の有効化 </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>Default = 1</p></td>
<td align="left"><p>ゲストとホストの間のプリンターの共有を有効にするかどうかを構成します。  0 = false;1 = true。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false: ゲストとホストの間のプリンターの共有を無効にします。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true: ゲストとホストの間でプリンターの共有を有効にします。</p></td>
</tr>
<tr class="even">
<td align="left"><p>RebootAbsoluteDelayTimeout </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 1440</p></td>
<td align="left"><p>初回のセットアップで再起動が待機するタイムアウト値 (分単位) です。 範囲 = 0 ~ 2147483647</p></td>
</tr>
<tr class="odd">
<td align="left"><p>RedirectUrls </p></td>
<td align="left"><p>MULTI_SZ</p></td>
<td align="left"><p>指定した URL リスト</p></td>
<td align="left"><p>ホストからゲストにリダイレクトされる Url のリストを指定します。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>SmartCardLogonEnabled</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 0</p></td>
<td align="left"><p>スマートカードを使用して、ユーザーを MED-V で認証できるかどうかを構成します。 0 = false;1 = true。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false: スマートカードは、MED-V を使用してエンドユーザーを認証しません。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true: スマートカードがエンドユーザーを MED-V に対して認証できるようにします。</p>
<div class="alert">
<strong>重要</strong><br/><p>SmartCardLogonEnabled と CredentialCacheEnabled が両方とも有効になっている場合は、SmartCardLogonEnabled が CredentialCacheEnabled をオーバーライドします。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>SmartCardSharingEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>Default = 1</p></td>
<td align="left"><p>ゲストとホストの間でスマートカードの共有を有効にするかどうかを構成します。  0 = false;1 = true。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false: ゲストとホストの間でスマートカードの共有を無効にします。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true: ゲストとホストの間でスマートカードの共有を有効にします。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Usbデバイスの使用を許可する </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>Default = 1</p></td>
<td align="left"><p>ゲストとホストの間で USB デバイスの共有を有効にするかどうかを構成します。  0 = false;1 = true。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false: ゲストとホスト間の USB デバイスの共有を無効にします。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true: ゲストとホスト間での USB デバイスの共有を有効にします。</p></td>
</tr>
</tbody>
</table>



## VM キー


次の表では、HKEY \ _LOCAL \ _MACHINE ¥のように、または、hkey \ _CURRENT \ _USER ¥という値に関連付けられているレジストリ値に関する情報を提供しています。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名前</th>
<th align="left">型</th>
<th align="left">データ/既定</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>CloseAction </p></td>
<td align="left"><p>SZ</p></td>
<td align="left"><p>Default = HIBERNATE</p></td>
<td align="left"><p>実行されている最後のアプリケーションが終了した後に仮想マシンで実行されるアクション。 LogonStartEnabled 値が有効になっている場合は、この設定は無視されます。 以下のオプションがあります。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong>休止状態 </strong> 。 このオプションは、仮想マシンで使用されているすべての物理リソース (メモリや CPU など) を解放し、実行されているすべてのアプリケーションと操作の状態を保存します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong>シャットダウン </strong> します。 このオプションでは、ゲストオペレーティングシステムを安全にシャットダウンし、仮想マシンで使用されているすべての物理リソース (メモリや CPU など) を解放します。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong>オフに </strong> します。 このオプションをオンにすると、power button をオフにするか、物理コンピューターの電源コードを引き出すのと同じように、データが失われる可能性があります。 このオプションは、他の2つのオプションのいずれかを使用できない場合にのみ使用します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>GuestMemFromHostMem </p></td>
<td align="left"><p>MULTI_SZ</p></td>
<td align="left"><p>378、512、1024、1536、2048 </p></td>
<td align="left"><p>ゲストのメモリ (MB) 値の一覧。 この値は、ゲストが使用できる RAM の量を決定するために使用されます。 HostMemToGuestMem と組み合わせると、参照テーブルが作成され、ゲスト仮想マシンに割り当てる RAM の量を決定します。 指定可能な値は、128から3712までです。</p></td>
</tr>
<tr class="even">
<td align="left"><p>GuestUpdateDuration </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 240</p></td>
<td align="left"><p>ゲストが自動的に更新されないようにするには、GuestUpdateTime 値で指定された時刻から開始するまでの時間を分単位で指定します。 範囲 = 0 ~ 1440 この値をゼロ (0) に設定すると、ゲストの修正プログラム機能は無効になります。</p>
<p>自動更新のゲストの更新プログラムの詳細については、「 <a href="managing-automatic-updates-for-med-v-workspaces.md" data-raw-source="[Managing Automatic Updates for MED-V Workspaces](managing-automatic-updates-for-med-v-workspaces.md)"> Med-v ワークスペースの自動更新を管理する」を参照してください </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>GuestUpdateTime </p></td>
<td align="left"><p>SZ</p></td>
<td align="left"><p>既定値 = 00:00</p></td>
<td align="left"><p>MED-V が自動更新のためにゲストをスリープ状態にする曜日と時間 (分)。24時間制の標準を使用します。 HH: MM の形式で時刻を指定します。  </p>
<p>自動更新のゲストの更新プログラムの詳細については、「 <a href="managing-automatic-updates-for-med-v-workspaces.md" data-raw-source="[Managing Automatic Updates for MED-V Workspaces](managing-automatic-updates-for-med-v-workspaces.md)"> Med-v ワークスペースの自動更新を管理する」を参照してください </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>HostMemToGuestMem </p></td>
<td align="left"><p>MULTI_SZ</p></td>
<td align="left"><p>1024、2048、4096、8192、16384 </p></td>
<td align="left"><p>ホストで利用可能な RAM によって決定される、ゲストのメモリ (MB) 値の一覧。 GuestMemFromHostMem と組み合わせると、参照テーブルが作成され、ゲスト仮想マシンに割り当てる RAM の量を決定します。 指定可能な値は、1024から16384までです。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>HostMemToGuestMemCalcEnabled</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>Default = 1</p></td>
<td align="left"><p>ゲストに割り当てられているメモリがホスト上にあるメモリから計算されるかどうかを構成します。  0 = false;1 = true。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false: ゲストに割り当てられているメモリは、ホスト上にあるメモリから計算されません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true: ゲストに割り当てられているメモリは、ホスト上にあるメモリから計算されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>メモリ </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 512</p></td>
<td align="left"><p>ゲスト仮想マシンに割り当てる必要がある RAM (MB)。 HostMemToGuestMemEnabled 設定が有効になっている場合、この設定は無視されます。 範囲 = 128 ~ 2048</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MultiUserEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 0</p></td>
<td align="left"><p>複数のユーザーが同じ MED-V ワークスペースを共有するかどうかを構成します。  0 = false;1 = true。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false: 複数のユーザーが、同じ MED-V ワークスペースを共有していません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true: 複数のユーザーが同じ MED-V ワークスペースを共有します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>NetworkingMode </p></td>
<td align="left"><p>SZ</p></td>
<td align="left"><p>Default = NAT</p></td>
<td align="left"><p>ゲストで使用されているネットワーク接続の種類。 次の値を指定できます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong>ブリッジ </strong> 。 MED-V には独自のネットワークアドレスがあります。通常は DHCP 経由で取得します。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong>NAT </strong> 。 MED-V は、ネットワークアドレス変換 (NAT) を使って、発信トラフィック用にホスト&#39;s IP を共有します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>TaskTimeout </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 600</p></td>
<td align="left"><p>通常のタイムアウト値は秒で、MED-V は、タスクが完了するまで待機します。たとえば、再起動やシャットダウンなどの処理が実行されます。 範囲 = 0 ~ 2147483647</p></td>
</tr>
</tbody>
</table>



## ゲストのレジストリ設定


このセクションには、構成可能な MED-V ゲストのレジストリキーの一覧とその使用方法が記載されています。

### v2

次の表では、HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Medv\\v2\\ キーに関連付けられているゲストレジストリ値について説明します。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名前 </th>
<th align="left">型 </th>
<th align="left">データ/既定 </th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>EnableGPWorkarounds</p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>Default = 1 </p></td>
<td align="left"><p>キーバッファーポリシーの読み取りと GroupPolicyMinTransferRate を MED-V で処理する方法を構成します。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>既定では、MED-V は以下のキーを設定します。</p>
<p>BufferPolicyReads = 1 と GroupPolicyMinTransferRate = 0。</p>
<p>必要に応じて EnableGPWorkarounds キーを作成し、MED-V で BufferPolicyReads と GroupPolicyMinTransferRate の既定の設定を変更しない場合は、このキーを0に設定します。</p>
<div class="alert">
<strong>注</strong><br/><p>MED-V ワークスペースが NAT モードで実行されている場合、EnableGPWorkarounds は、レジストリキーのバッファーポリシーの読み取りと GroupPolicyMinTransferRate に影響します。 MED-V ワークスペースがブリッジモードで実行されている場合、EnableGPWorkarounds はレジストリキーバッファーの読み取りにのみ影響します。</p>
</div>
<div>

</div>
<p>1 = true: MED-V は、キーバッファーポリシーの読み取り = 1 と GroupPolicyMinTransferRate = 0 (NAT モードで実行されている場合)、または BufferPolicyReads = 1 だけ (ブリッジモードで実行されている場合) を設定します。</p>
<p>0 = false: MED-V は、キーバッファーポリシーの読み取りと GroupPolicyMinTransferRate に変更を加えません。</p></td>
</tr>
</tbody>
</table>



## 関連トピック


[MED-V ワークスペース アプリケーションを管理する](manage-med-v-workspace-applications.md)

[MED-V の URL リダイレクトの管理](manage-med-v-url-redirection.md)

[MED-V ワークスペースの設定を管理する](manage-med-v-workspace-settings.md)









