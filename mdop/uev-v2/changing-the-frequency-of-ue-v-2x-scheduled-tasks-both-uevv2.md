---
title: UE-V 2. x のスケジュールされたタスクの頻度の変更
description: UE-V 2. x のスケジュールされたタスクの頻度の変更
author: dansimp
ms.assetid: ee486570-c6cf-4fd9-ba48-0059ba877c10
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 09/29/2016
ms.openlocfilehash: 1c1e3c091431dc56068dcd1fe0e849b0df1f6aa0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824427"
---
# UE-V 2. x のスケジュールされたタスクの頻度の変更


Microsoft User Experience Virtualization (UE-V) 2.0、2.1、または 2.1 SP1 Agent installer の AgentSetup.exe では、UE-V エージェントのインストール中に次のスケジュールされたタスクが作成されます。

-   **アプリケーションの設定を監視する**

-   **同期コントローラーアプリケーション**

-   **ログオフ時に設定を同期する**

-   **テンプレートの自動更新**

-   **CEIP データを収集する**

-   **CEIP データをアップロードする**

**注** 収集した CEIP データを除き、UE-V は使用できないため、これらのタスクは有効のままにしておく必要があります。

 

これらのスケジュールされたタスクは、UE-V ツールで構成することはできません。 これらのアイテムのスケジュールされたタスクを変更する管理者は、Schtasks.exe のコマンドラインオプションを使用するスクリプトを作成できます。

Schtasks.exe の詳細については、「 [Schtasks、exe を使用して Windows Server 2003 でタスクをスケジュールする方法](https://go.microsoft.com/fwlink/?LinkID=264854)」を参照してください。

詳細情報

## UE-V のスケジュールされたタスク


スケジュールされたタスクの設定コマンドを使用して、次のスケジュールされたタスクが UE-V 2 に含まれています。

### CEIP データを収集する

インストール時に、ユーザーまたは管理者によって、カスタマーエクスペリエンス向上プログラム (CEIP) に参加するようになります。 UE-V は、将来のリリースで製品の改善に役立つデータを収集します。 このスケジュールされたタスクは、ログオン時にのみ実行されます。 **CEIP データ収集**タスクは、ue-v agent のインストールディレクトリにある UevSqmSession.exe を実行します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">タスク名</th>
<th align="left">既定のイベント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>\Microsoft\UE-V\Collect CEIP データ</p></td>
<td align="left"><p>ログオン</p></td>
</tr>
</tbody>
</table>

 

### アプリケーションの設定を監視する

[**アプリケーション設定の監視**] タスクは、Windows アプリの設定を同期するために使用されます。 ログオン時に実行されますが、ログオン detrimentally に影響しないため、30秒ほど遅延します。 アプリケーションの状態の監視タスクは、UE-V Agent のインストールディレクトリにある UevAppMonitor.exe ファイルを実行します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">タスク名</th>
<th align="left">既定のイベント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>\Microsoft\UE-V\Monitor アプリケーションの状態</p></td>
<td align="left"><p>ログオン</p></td>
</tr>
</tbody>
</table>

 

### 同期コントローラーアプリケーション

**同期コントローラーアプリケーション**タスクを使って、設定をコンピューターから設定の保存場所に同期する同期コントローラーを開始します。 既定では、タスクは30分ごとに実行されます。 この時点では、ローカル設定が設定の保存場所に同期され、設定の保存場所の更新された設定がコンピューターに同期されます。 同期コントローラーアプリケーションは、UE-V Agent のインストールディレクトリにある Microsoft.Uev.SyncController.exe を実行します。
**注:**[**アプリケーション設定の監視**] タスクでは、このタスクはログオン時に実行されますが、ログオン detrimentally に影響を与えないために30秒ほど遅延します。
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">タスク名</th>
<th align="left">既定のイベント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>\Microsoft\UE-V\Sync Controller アプリケーション</p></td>
<td align="left"><p>ログオンとその後30分ごと</p></td>
</tr>
</tbody>
</table>

 

たとえば、次のコマンドは、既定の30分ではなく15分ごとに設定を同期するようにエージェントを構成します。

``` syntax
Schtasks /change /tn “Microsoft\UE-V\Sync Controller Application” /ri 15
```

### ログオフ時に設定を同期する

ログオフ時の**同期設定**は、ue-v のログオフ時のアプリケーションの同期を制御する、ログオン時にアプリケーションを起動するために使用されます。 ログオフタスクで設定を同期すると、UE-V Agent のインストールディレクトリにある Microsoft.Uev.SyncController.exe ファイルが実行されます。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">タスク名</th>
<th align="left">既定のイベント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>\Microsoft\UE-V\Synchronize 設定のログオフ</p></td>
<td align="left"><p>ログオン</p></td>
</tr>
</tbody>
</table>

 

### テンプレートの自動更新

**テンプレートの自動更新**タスクは、新規作成、更新、または削除されたテンプレートの設定テンプレートカタログをチェックします。 このタスクは、SettingsTemplateCatalog が構成されている場合にのみ実行されます。 **テンプレートの自動更新**タスクは、ue-v agent のインストールディレクトリにある ApplySettingsCatalog.exe ファイルを実行します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">タスク名</th>
<th align="left">既定のイベント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>\Microsoft\UE-V\Template の自動更新</p></td>
<td align="left"><p>システムの起動時と 3:30 AM (1 時間のウィンドウ内のランダムな時刻)</p></td>
</tr>
</tbody>
</table>

 

**例:** 次のコマンドは、UE-V Agent を構成して、設定テンプレートカタログストアを1時間おきに確認します。

``` syntax
schtasks /change /tn "Microsoft\UE-V\Template Auto Update" /ri 60
```

### CEIP データをアップロードする

ユーザーまたは管理者がカスタマーエクスペリエンス向上プログラム (CEIP) に参加することを選択した場合、 **Ceip データのアップロード**タスクはインストール中に実行されます。 このタスクにより、データが CEIP サーバーにアップロードされ、将来のリリースでの製品の改善に役立てることができます。 このスケジュールされたタスクは、ログオン時と4時間おきに実行されます。 **CEIP データのアップロード**タスクは、ue-v agent のインストールディレクトリにある UevSqmUploader.exe ファイルを実行します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">タスク名</th>
<th align="left">既定のイベント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>\Microsoft\UE-V\Upload CEIP データ</p></td>
<td align="left"><p>ログオン時と4時間ごと</p></td>
</tr>
</tbody>
</table>

 

## UE-V 2 スケジュールされたタスクの詳細


次の表は、UE-V 2 のスケジュールされたタスクに関する追加情報を示しています。

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>タスク名 </strong> (ファイル名)</p></td>
<td align="left"><p><strong>既定の頻度</strong></p></td>
<td align="left"><p><strong>Power トグル</strong></p></td>
<td align="left"><p><strong>Idle のみ</strong></p></td>
<td align="left"><p><strong>ネットワーク接続</strong></p></td>
<td align="left"><p><strong>説明</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>アプリケーションの設定を監視する </strong> (UevAppMonitor.exe)</p></td>
<td align="left"><p>ログオン後30秒で開始し、ログオフするまで続行します。</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>Windows (AppX) アプリの設定を同期します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>同期コントローラーアプリケーション </strong> (Microsoft.Uev.SyncController.exe)</p></td>
<td align="left"><p>ログオン時と30分間隔。</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>要</p></td>
<td align="left"><p>ネットワークが接続されている場合のみ</p></td>
<td align="left"><p>ローカル設定と設定の保存場所を同期する同期コントローラーを開始します。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>ログオフ時に設定を同期する </strong> (Microsoft.Uev.SyncController.exe)</p></td>
<td align="left"><p>ログオン時に実行され、ログオフの間待機して設定を同期します。</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>ログオン時に、ログオフ時のアプリケーションの同期を制御するアプリケーションを起動します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>テンプレートの自動更新 </strong> (ApplySettingsCatalog.exe)</p></td>
<td align="left"><p>最初のログオン時と3:30 午前時に実行されます。</p></td>
<td align="left"><p>可</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>該当せず</p></td>
<td align="left"><p>新規、更新、または削除されたテンプレートの設定テンプレートカタログを確認します。 このタスクは、SettingsTemplateCatalog が構成されている場合にのみ実行されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>CEIP データの収集 </strong> (UevSqmSession.exe)</p></td>
<td align="left"><p>ログオン時にサービスを起動する</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>該当せず</p></td>
<td align="left"><p>ユーザーまたは管理者がカスタマーエクスペリエンス向上プログラム (CEIP) に参加した場合、このタスクでは、UE-V の将来のリリースを改善するために役立つデータが収集されます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>CEIP データをアップロードする </strong> (UevSqmUploader.exe)</p></td>
<td align="left"><p>ログオン時に実行され、その後は 4:00 AM に実行されます。</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>ネットワークが接続されている場合のみ</p></td>
<td align="left"><p>ユーザーまたは管理者がカスタマーエクスペリエンス向上プログラム (CEIP) に参加した場合、このタスクはデータを CEIP サーバーにアップロードします。</p></td>
</tr>
</tbody>
</table>

 

**伝説**

-   **Power トグル**–タスクスケジューラは、AC 電源に接続されていないときに電力消費を最適化します。 コンピューターがバッテリ電源に切り替わった場合、タスクの実行が停止することがあります。

-   [**アイドルのみ**]-コンピューターがアイドル状態になっていない場合、タスクは実行を停止します。 既定では、コンピューターがもう一度アイドル状態になると、タスクは再起動されません。 代わりに、次のタスクトリガーでタスクが再び開始されます。

-   **ネットワーク接続**–コンピューターにネットワーク接続がある場合にのみ、"はい" とマークされたタスクを実行します。 "N/A" とマークされたタスクは、ネットワーク接続に関係なく実行されます。

### スケジュールされたタスクを管理する方法

スケジュールされたタスクを見つけるには、次の手順を実行します。

1.  ユーザーのコンピューターで、[タスクのスケジュール] を開きます。

2.  移動先: タスクスケジューラ- &gt; タスクスケジューラライブラリ- &gt; Microsoft- &gt; ue-v

3.  [詳細] ウィンドウで、管理して構成するスケジュールされたタスクを選びます。

### 追加情報

次の追加情報は、UE-V のスケジュールされたタスクに適用されます。

-   ll タスクシーケンスプログラムは、既定で UE-V Agent のインストールフォルダーにあり `%programFiles%\Microsoft User Experience Virtualization\Agent\[architecture]\` ます。

-   同期コントローラーアプリケーションのスケジュールされたタスクは、UE-V SyncMethod が "Syncmethod" (UE-V 2 の既定の構成) に設定されている場合に、重要なコンポーネントです。 このスケジュールされたタスクは、設定パッケージファイルのローカルにキャッシュされたバージョンとの SettingsSToragePath の同期を維持します。 設定が十分な頻度で同期されないとユーザーから苦情があった場合、スケジュールされたタスクの設定を1分以内に減らすことができます。必要に応じて、30分の既定値をより高い金額に増やすこともできます。 ログオン時に設定が十分な速度で同期されないという苦情がある場合は、スケジュールされたタスクの遅延設定を削除します。 ([**トリガーの編集**] ダイアログボックスで遅延設定を確認できます)

-   他の方法を使用してクライアントのテンプレートを同期しておく場合 (グループポリシーまたは Configuration Manager のベースラインなど)、別の方法でテンプレートの自動更新を無効にする必要はありません。 SettingsTemplateCatalog プロパティ値を空のままにすると、UE-V はカスタムテンプレートの設定カタログを確認できなくなります。 このスケジュールされたタスクは ApplySettingsCatalog.exe 実行され、実質的にすぐに戻ります。

-   [アプリケーション設定の監視] スケジュールされたタスクは、各アプリに組み込まれている Windows アプリプログラムの設定トリガーに基づいて、リアルタイムで Windows アプリ (AppX) 設定を更新します。






## 関連トピック


[UE-V 2. x の管理](administering-ue-v-2x-new-uevv2.md)

[カスタムアプリケーションの UE-V 2. x の展開](deploy-ue-v-2x-for-custom-applications-new-uevv2.md#deploycatalogue)

 

 





