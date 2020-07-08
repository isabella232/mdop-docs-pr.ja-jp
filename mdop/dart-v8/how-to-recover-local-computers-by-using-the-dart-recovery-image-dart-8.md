---
title: DaRT 回復イメージを使用してローカル コンピューターを回復する方法
description: DaRT 回復イメージを使用してローカル コンピューターを回復する方法
author: dansimp
ms.assetid: f679d522-49ab-429c-93d0-294c3f3e5639
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1b5faa0eb9ac24b33c66f1d5262a050b92e11e52
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824307"
---
# DaRT 回復イメージを使用してローカル コンピューターを回復する方法


問題が発生しているエンドユーザーのコンピューターに物理的に表示されているコンピューターを回復するには、次の手順を使用します。

**DaRT リカバリイメージを使用してローカルコンピューターを復元する方法**

1.  Microsoft 診断/回復ツールセット (DaRT) 8.0 回復イメージを使用して、エンドユーザーのコンピューターを起動します。

    コンピューターが DaRT 8.0 リカバリイメージに起動すると、 **Netstart**ダイアログボックスが表示されます。

2.  ネットワークサービスを初期化するかどうかを確認するメッセージが表示されたら、次のいずれかを選択します。

    **はい**。ネットワーク上に DHCP サーバーが存在し、サーバーから IP アドレスを取得しようとしていることを前提としています。 ネットワークで DHCP の代わりに静的 IP アドレスを使用している場合は、後で DaRT の**Tcp/ip 構成**ツールを使って静的 ip アドレスを指定できます。

    **いいえ**。ネットワーク初期化プロセスをスキップします。

3.  ドライブ文字を再マッピングするかどうかを指定します。 Windows online を実行すると、通常、システムボリュームは C ドライブにマップされます。ただし、WinRE で Windows オフラインを実行すると、元のシステムボリュームが別のドライブにマップされている可能性があります。これによって混乱が生じることがあります。 再マッピングする場合、DaRT はオンラインのドライブ文字と一致するように、オフラインのドライブ文字をマッピングしようとします。 再マッピングは、起動プロセスでオフラインのオペレーティングシステムが選択されている場合にのみ実行されます。

4.  [**システム回復オプション**] ダイアログボックスで、キーボードレイアウトを選択します。

5.  表示されたシステムルートディレクトリ、インストールされているオペレーティングシステムの種類、およびパーティションサイズを確認します。 使用しているオペレーティングシステムが表示されず、ドライバーが見つからないことが原因で問題が発生している可能性がある場合は、[**ドライバーの読み込み**] をクリックして問題のあるドライバーを読み込み、デバイスのインストールメディアを挿入して、ドライバーを選びます。

6.  修復または診断するインストールを選択し、[**次へ**] をクリックします。

    **注**  
    Windows 回復環境 (WinRE) で、前回の試用時に Windows 8 が正しく開始されなかったことが検出された場合は、**スタートアップ修復**が自動的に開始されることがあります。



~~~
If any of the registry hives are corrupted or missing, Registry Editor and several other DaRT utilities will have limited functionality. If no operating system is selected, some tools will not be available.

The **System Recovery Options** window appears and lists various recovery tools.
~~~

7. [**システム回復オプション**] ウィンドウで、[ **Microsoft 診断/回復ツールセット**] をクリックします。

   [**診断/回復ツールセット**] ウィンドウが開きます。 DaRT リカバリ画像の作成時に含まれていた個々のツールまたはウィザードを実行できるようになりました。

**診断/回復ツールセット**ウィンドウの [**ヘルプ**] をクリックすると、個々の DaRT ツールの実行に必要な詳しい手順と情報を提供しているクライアントヘルプファイルを開くことができます。 [**診断/回復ツールセット**] ウィンドウで**ソリューションウィザード**をクリックして、ウィザードで提供される短い面接に基づいて、状況に最適なツールを選ぶこともできます。

DaRT ツールについての一般的な情報については、「 [dart 8.0 でのツールの概要](overview-of-the-tools-in-dart-80-dart-8.md)」をご覧ください。

**コマンドプロンプトで DaRT を実行する方法**

- コマンドプロンプトで DaRT を実行するには、 **netstart.exe**コマンドを指定し、次のいずれかのパラメーターを使用します。

  <table>
  <colgroup>
  <col width="50%" />
  <col width="50%" />
  </colgroup>
  <tbody>
  <tr class="odd">
  <td align="left"><p><strong>パラメーター</strong></p></td>
  <td align="left"><p><strong>説明</strong></p></td>
  </tr>
  <tr class="even">
  <td align="left"><p>-ネットワーク</p></td>
  <td align="left"><p>ネットワークサービスを初期化します。</p></td>
  </tr>
  <tr class="odd">
  <td align="left"><p>-再マウント</p></td>
  <td align="left"><p>ドライブ文字を再マッピングします。</p></td>
  </tr>
  <tr class="even">
  <td align="left"><p>-プロンプト</p></td>
  <td align="left"><p>ネットワークを初期化してドライブを再マップするかどうかをエンドユーザーに指定するように求めるメッセージを表示します。</p>
  <div class="alert">
  <strong>Warning</strong><br/><p>プロンプトに対するエンドユーザーの応答は、–ネットワークと再マウントのスイッチを上書きします。</p>
  </div>
  <div>

  </div></td>
  </tr>
  </tbody>
  </table>



## 関連トピック


[DaRT 8.0 の操作](operations-for-dart-80-dart-8.md)

[DaRT 8.0 を使用したコンピューターの回復](recovering-computers-using-dart-80-dart-8.md)









