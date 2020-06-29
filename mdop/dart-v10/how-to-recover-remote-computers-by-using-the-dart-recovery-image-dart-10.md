---
title: DaRT 回復イメージを使用してリモート コンピューターを回復する方法
description: DaRT 回復イメージを使用してリモート コンピューターを回復する方法
author: dansimp
ms.assetid: c0062208-39cd-4e01-adf8-36a11386e2ea
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 42d49c6c5c494da866785764e1c93a6bda2d667e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822594"
---
# DaRT 回復イメージを使用してリモート コンピューターを回復する方法


Microsoft 診断/回復ツールセット (DaRT) 10 のリモート接続機能を使用して、エンドユーザーのコンピューターで DaRT ツールをリモートで実行します。 エンドユーザーが管理者またはヘルプデスクの担当者に特定の情報を提供した後、IT 管理者またはヘルプデスクのワーカーは、エンドユーザーのコンピューターを制御し、必要な DaRT ツールをリモートで実行することができます。

回復イメージを作成したときに DaRT ツールを無効にした場合でも、すべてのツールにアクセスできます。 リモート接続を除くすべてのツールは、エンドユーザーが利用できません。

**DaRT リカバリイメージを使用してリモートコンピューターを回復するには**

1.  DaRT 回復イメージを使用して、エンドユーザーのコンピューターを起動します。

    通常、次のいずれかの方法を使用して、dart の回復イメージの展開方法に応じて DaRT を起動し、リモートコンピューターを回復します。 DaRT リカバリ画像の展開について詳しくは、「 [dart 10 の展開](deploying-dart-10.md)」をご覧ください。

    -   問題のあるコンピューターの回復パーティションから DaRT に起動します。

    -   ネットワーク上のリモートパーティションから DaRT に起動します。

    各方法の長所と短所については、「 [DaRT 10 の回復イメージを保存して展開する方法を計画する](planning-how-to-save-and-deploy-the-dart-10-recovery-image.md)」を参照してください。

    DaRT を起動するために使用する方法にかかわらず、エンドユーザーが使用できるようにするブートオプションについては、BIOS でブートデバイスを有効にする必要があります。

    **注**  
    BIOS の構成は、ハードディスクドライブの種類、ネットワークアダプター、および組織で使用されているその他のハードウェアに応じて固有です。



~~~
As the computer is booting into the DaRT recovery image, the **NetStart** dialog box appears.
~~~

2. ネットワークサービスを初期化するかどうかを確認するメッセージが表示されたら、次のいずれかを選択します。

   **はい**。ネットワーク上に DHCP サーバーが存在し、サーバーから IP アドレスを取得しようとしていることを前提としています。 ネットワークで DHCP の代わりに静的 IP アドレスを使用している場合は、後で DaRT の**Tcp/ip 構成**ツールを使って静的 ip アドレスを指定できます。

   **いいえ**。ネットワーク初期化プロセスをスキップします。

3. ドライブ文字を再マッピングするかどうかを指定します。 Windows online を実行すると、通常、システムボリュームは C ドライブにマップされます。ただし、WinRE で Windows オフラインを実行すると、元のシステムボリュームが別のドライブにマップされている可能性があります。これによって混乱が生じることがあります。 再マッピングする場合、DaRT はオンラインのドライブ文字と一致するように、オフラインのドライブ文字をマッピングしようとします。 再マッピングは、起動プロセスでオフラインのオペレーティングシステムが選択されている場合にのみ実行されます。

4. [**システム回復オプション**] ダイアログボックスで、キーボードレイアウトを選択します。

5. 表示されたシステムルートディレクトリ、インストールされているオペレーティングシステムの種類、およびパーティションサイズを確認します。 使用しているオペレーティングシステムが表示されず、ドライバーが見つからないことが原因で問題が発生している可能性がある場合は、[**ドライバーの読み込み**] をクリックして問題のあるドライバーを読み込み、デバイスのインストールメディアを挿入して、ドライバーを選びます。

6. 修復または診断するインストールを選択し、[**次へ**] をクリックします。

   **注**  
   Windows 回復環境 (WinRE) で、前回の試用時に Windows 10 が正しく開始されなかったことが検出された場合は、**スタートアップ修復**が自動的に開始されることがあります。 この問題を解決する方法については、「 [DaRT 10 のトラブルシューティング](troubleshooting-dart-10.md)」を参照してください。



~~~
If any of the registry hives are corrupted or missing, Registry Editor and several other DaRT utilities will have limited functionality. If no operating system is selected, some tools will not be available.

The **System Recovery Options** window appears and lists various recovery tools.
~~~

7. [**システム回復オプション**] ウィンドウで、[ **Microsoft 診断/回復ツールセット**] をクリックし、**診断/回復ツールセット**を開きます。

8. [**診断/回復ツールセット**] ウィンドウで、[**リモート接続**] をクリックして**DaRT リモート接続**ウィンドウを開きます。 ヘルプデスクのリモートアクセスの指定を求められたら、[ **OK]** をクリックします。

   DaRT リモート接続ウィンドウが開き、チケット番号、IP アドレス、ポート情報が表示されます。

9. ヘルプデスクコンピューターで、 **DaRT リモート接続ビューアー**を開きます。

10. [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Dart 10**]、[ **dart リモート接続ビューアー**] の順にクリックします。

11. **DaRT リモート接続**ウィンドウで、必要なチケット、IP アドレス、ポート情報を入力します。

   **注**  
   この情報は、エンドユーザーのコンピューター上に作成され、エンドユーザーによって提供される必要があります。 エンドユーザーコンピューターで利用可能な IP アドレスの数に応じて、複数の IP アドレスを選ぶことができます。



12. **[接続]** をクリックします。

IT 管理者は、エンドユーザーのコンピューターの制御を前提としており、DaRT ツールをリモートで実行できます。

**注**  
inv32.xml という名前のファイルが用意されており、ポート番号や IP アドレスなどのリモート接続情報が含まれています。 既定では、ファイルは%windir%\\system32. にあります。



**リモート接続プロセスをカスタマイズするには**

1. winpeshl.ini ファイルを編集することで、リモート接続プロセスをカスタマイズできます。 winpeshl.ini ファイルを編集する方法の詳細については、「 [Winpeshl.ini ファイル](https://go.microsoft.com/fwlink/?LinkId=219413)」を参照してください。

   次のコマンドとパラメーターを指定して、エンドユーザーのコンピューターとのリモート接続の確立方法をカスタマイズします。

   <table>
   <colgroup>
   <col width="33%" />
   <col width="33%" />
   <col width="33%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">コマンド</th>
   <th align="left">パラメーター</th>
   <th align="left">説明</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong>RemoteRecovery.exe</strong></p></td>
   <td align="left"><p>-nomessage</p></td>
   <td align="left"><p>確認メッセージが表示されないように指定します。 <strong>リモート接続は </strong> 、エンドユーザーによって &quot; [はい] が確認プロンプトに応答した場合と同じように継続さ &quot; れます。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>WaitForConnection.exe</strong></p></td>
   <td align="left"><p>なし</p></td>
   <td align="left"><p><strong>リモート接続が実行されて </strong> いないか、エンドユーザーのコンピューターとの接続が確立されるまで、カスタムスクリプトが続行されないようにします。</p>
   <div class="alert">
   <strong>重要</strong><br/><p>このコマンドは、個別に指定されている場合は関数を提供しません。 正しく機能するためには、スクリプトで指定する必要があります。</p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



2. DaRT を起動しようとするとすぐに**リモート接続**ツールを開くようにカスタマイズされた winpeshl.ini ファイルの例を次に示します。

   ```ini
   [LaunchApps]
   "%windir%\system32\netstart.exe -network -remount"
   "cmd /C start %windir%\system32\RemoteRecovery.exe -nomessage"
   "%windir%\system32\WaitForConnection.exe"
   "%SYSTEMDRIVE%\sources\recovery\recenv.exe"
   ```

DaRT が起動すると、RAM ディスク上の \\Windows\\System32\\ にファイル inv32.xml が作成されます。 このファイルには、IP アドレス、ポート、チケット番号などの接続情報が含まれます。 このファイルをネットワーク共有にコピーして、ヘルプデスクワークフローをトリガーすることができます。 たとえば、カスタムプログラムで接続ファイルのネットワーク共有を確認し、サポートチケットを作成したり、メール通知を送信したりすることができます。

**コマンドプロンプトでリモート接続ビューアーを実行するには**

1.  コマンドプロンプトで**DaRT リモート接続ビューアー**を実行するには、 **DartRemoteViewer.exe**コマンドを指定し、次のパラメーターを使用します。

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
    <td align="left"><p>-ticket = &lt; <em> ticketnumber</em>&gt;</p></td>
    <td align="left"><p>ここで &lt; <em> </em> &gt; 、Ticketnumber は、リモート接続によって生成される、ダッシュを含むチケット番号です。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>-ipaddress = &lt; <em> ipaddress</em>&gt;</p></td>
    <td align="left"><p>&lt; <em> Ipaddress </em> &gt; は、リモート接続によって生成される IP アドレスです。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>-port = &lt; <em> port</em>&gt;</p></td>
    <td align="left"><p>&lt; <em> Port </em> &gt; は、指定された IP アドレスに対応するポートです。</p></td>
    </tr>
    </tbody>
    </table>



~~~
**Note**  
The variables for these parameters are created on the end-user computer and must be provided by the end user.
~~~



2. 3つのパラメーターがすべて指定されていて、データが有効である場合は、プログラムが起動すると直ちに接続が試行されます。 いずれかのパラメーターが有効でない場合は、パラメーターが指定されていないかのようにプログラムが開始します。

## 関連トピック


[DaRT 10 の操作](operations-for-dart-10.md)

[DaRT 10 を使用したコンピューターの回復](recovering-computers-using-dart-10.md)









