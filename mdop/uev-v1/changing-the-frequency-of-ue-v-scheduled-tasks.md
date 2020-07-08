---
title: UE-V のスケジュールされたタスクの頻度の変更
description: UE-V のスケジュールされたタスクの頻度の変更
author: dansimp
ms.assetid: 33c2674e-0df4-4717-9c3d-820a90b16e19
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ced608608ffae82a29fb5ca84cfca281082b8127
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822687"
---
# UE-V のスケジュールされたタスクの頻度の変更


Microsoft User Experience Virtualization (UE-V) Agent installer、AgentSetup.exe は、UE-V Agent のインストール中に2つのスケジュールされたタスクを作成します。 この2つのタスクは、**テンプレートの自動更新**タスクと、**保存場所の状態の設定**タスクの設定です。 これらのスケジュールされたタスクは、UE-V ツールで構成することはできません。 これらのアイテムのスケジュールされたタスクを変更しようとしている管理者は、Schtasks.exe のコマンドラインオプションを使用するスクリプトを作成できます。

Schtasks.exe の詳細については、「 [Schtasks、exe を使用して Windows Server 2003 でタスクをスケジュールする方法](https://go.microsoft.com/fwlink/?LinkID=264854)」を参照してください。

## テンプレートの自動更新


**テンプレートの自動更新**タスクは、新規作成、更新、または削除されたテンプレートの設定テンプレートカタログをチェックします。 このタスクは、SettingsTemplateCatalog が構成されている場合にのみ実行されます。 **テンプレートの自動更新**タスクは、ue-v agent のインストールディレクトリにある ApplySettingsCatalog.exe ファイルを実行します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">タスク名</th>
<th align="left">既定のトリガー</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>\Microsoft\UE-V\Template の自動更新</p></td>
<td align="left"><p>毎日 3:30 AM</p></td>
</tr>
</tbody>
</table>

 

**例:** 次のコマンドは、設定テンプレートカタログストアを1時間おきに確認するようにエージェントを構成します。

``` syntax
schtasks /change /tn "Microsoft\UE-V\Template Auto Update" /ri 60
```

## 設定の保存場所の状態


**記憶域の場所の状態の設定**タスクは、次の操作を実行します。

1.  UE-V フォルダーがオフラインファイル機能に固定されているか、登録されているかを確認します。

2.  設定の保存場所がオフラインかオンラインかを確認します。

3.  オフラインファイルの既定の間隔ではなく、指定した間隔で強制的に同期を実行します。

4.  事前に取得されるように構成されている設定パッケージを同期します。

5.  Active Directory のホームディレクトリのパスが変更されたかどうかを確認します。

6.  次の場所に現在の設定の記憶域構成を書き込みます

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">タスク名</th>
    <th align="left">既定のトリガー</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>\Microsoft\UE-V\Settings の保存場所の状態</p></td>
    <td align="left"><p>任意のユーザーのログオン時–トリガー後は、30分間隔で何度も繰り返すことができます。</p></td>
    </tr>
    </tbody>
    </table>

     

**例:** 次のコマンドは、1時間ごとに操作を実行するようにエージェントを構成します。

``` syntax
schtasks /change /tn "\Microsoft\UE-V\Settings Storage Location Status" /ri 60
```

## 関連トピック


[UE-V 1.0 の管理](administering-ue-v-10.md)

[UE-V 1.0 の操作](operations-for-ue-v-10.md)

 

 





