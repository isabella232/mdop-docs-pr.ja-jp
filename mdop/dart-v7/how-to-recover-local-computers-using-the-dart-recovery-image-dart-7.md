---
title: DaRT の回復イメージを使用してローカル コンピューターを回復する方法
description: DaRT の回復イメージを使用してローカル コンピューターを回復する方法
author: dansimp
ms.assetid: be29b5a8-be08-4cf2-822e-77a51d3f3b65
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4c605db895b5ea812d90db51d3c2de9653e2dd2d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823764"
---
# DaRT の回復イメージを使用してローカル コンピューターを回復する方法


Microsoft Diagnostics and Recovery ツールセット (DaRT) 7 を使用してローカルコンピューターを回復するには、DaRT を必要とする問題が発生しているエンドユーザーのコンピューターに物理的に存在している必要があります。 Dart[リカバリ画像を使ってリモートコンピューターを回復する方法](how-to-recover-remote-computers-using-the-dart-recovery-image-dart-7.md)については、次の手順に従って dart をリモートで実行することもできます。

**DaRT を使用してローカルコンピューターを回復するには**

1.  コンピュータが DaRT リカバリイメージとして起動すると、 **Netstart**ダイアログボックスが表示されます。 ネットワークサービスを初期化するかどうかを確認するメッセージが表示されます。 [**はい**] をクリックすると、ネットワークに DHCP サーバーが存在し、サーバーから IP アドレスを取得しようとしたと見なされます。 ネットワークで DHCP の代わりに静的 IP アドレスを使用している場合は、後で DaRT の**Tcp/ip 構成**ツールを使って静的 ip アドレスを指定できます。

    ネットワーク初期化プロセスをスキップするには、[**いいえ**] をクリックします。

2.  [ネットワークの初期化] ダイアログボックスで、ドライブ文字を再マップするかどうかを確認するメッセージが表示されます。 Windows online を実行すると、通常、システムボリュームは C ドライブにマップされます。ただし、WinRE で Windows オフラインを実行すると、元のシステムボリュームが別のドライブにマップされている可能性があります。これによって混乱が生じることがあります。 再マッピングする場合、DaRT はオンラインのドライブ文字と一致するように、オフラインのドライブ文字をマッピングしようとします。 再マッピングは、起動プロセスでオフラインのオペレーティングシステムが選択されている場合にのみ実行されます。

3.  [再マッピング] ダイアログボックスで、[**システム回復オプション**] ダイアログボックスが表示され、キーボードレイアウトを選択するように求められます。 次に、システムルートディレクトリ、インストールされているオペレーティングシステムの種類、パーティションサイズが表示されます。 使用しているオペレーティングシステムが表示されず、ドライバーが見つからないことが原因で問題が発生している可能性がある場合は、[**ドライバーの読み込み**] をクリックして問題のあるドライバーを読み込みます。 デバイスのインストールメディアを挿入して、ドライバーを選択するように求められます。 修復または診断するインストールを選択し、[**次へ**] をクリックします。

    **注**  
    Windows 回復環境 (WinRE) で、前回の試用時に Windows 7 が正常に起動しなかったことが検出された場合は、**スタートアップ修復**が自動的に開始されることがあります。



~~~
If any of the registry hives are corrupted or missing, Registry Editor, and several other DaRT utilities, will have limited functionality. If no operating system is selected, some tools will not be available.

The **System Recovery Options** window appears and lists various recovery tools.
~~~

4. [**システム回復オプション**] ウィンドウで、[ **Microsoft 診断/回復ツールセット**] をクリックします。

   [**診断/回復ツールセット**] ウィンドウが開きます。 DaRT リカバリ画像の作成時に含まれていた個々のツールまたはウィザードを実行できるようになりました。

**診断/回復ツールセット**ウィンドウの [**ヘルプ**] をクリックすると、個々の DaRT ツールの実行に必要な詳しい手順と情報を提供しているクライアントヘルプファイルを開くことができます。 [**診断/回復ツールセット**] ウィンドウで**ソリューションウィザード**をクリックして、ウィザードで提供される短い面接に基づいて、状況に最適なツールを選ぶこともできます。

DaRT ツールについての一般的な情報については、「 [dart 7.0 でのツールの概要](overview-of-the-tools-in-dart-70-new-ia.md)」をご覧ください。

**コマンドプロンプトで DaRT を実行するには**

1. コマンドプロンプトで DaRT を実行するには、 **netstart.exe**コマンドを指定し、次のいずれかのパラメーターを使用します。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">パラメーター</th>
   <th align="left">説明</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>-ネットワーク</p></td>
   <td align="left"><p>ネットワークサービスを初期化します。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>-再マウント</p></td>
   <td align="left"><p>ドライブ文字を再マッピングします。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>-プロンプト</p></td>
   <td align="left"><p>ネットワークを初期化してドライブを再マッピングするかどうかをエンドユーザーに指定するように求めるメッセージを表示します。</p>
   <div class="alert">
   <strong>重要</strong><br/><p>プロンプトに対するエンドユーザーの応答は、ネットワークと再マウントのスイッチを上書きします。</p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



2. Dart をブートしているコンピュータが**リモート**接続ツールを自動的に起動するように dart をカスタマイズして、ヘルプデスクとのリモート接続を確立することができます。

## 関連トピック


[DaRT 7.0 を使用したコンピューターの回復](recovering-computers-using-dart-70-dart-7.md)









