---
title: DaRT の回復イメージを使用してリモート コンピューターを回復する方法
description: DaRT の回復イメージを使用してリモート コンピューターを回復する方法
author: dansimp
ms.assetid: 66bc45fb-dc40-4d47-b583-5bb1ff5c97a7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 885ab1d1cf8f51dc4fd4613e41a20a2525ea7d6d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822794"
---
# DaRT の回復イメージを使用してリモート コンピューターを回復する方法


Microsoft 診断/回復ツールセット (DaRT) 7 のリモート接続機能により、IT 管理者は、エンドユーザーのコンピューターで DaRT ツールをリモートで実行できます。 エンドユーザー (またはエンドユーザーのコンピューターでのヘルプデスクプロフェッショナル) によって特定の情報が提供されると、IT 管理者またはヘルプデスクエージェントは、エンドユーザーのコンピューターを制御し、必要な DaRT ツールをリモートで実行することができます。

**重要**  
リモート接続を確立する2台のコンピューターは、同じネットワークの一部である必要があります。



**DaRT を使用してリモートコンピューターを回復するには**

1.  DaRT 回復イメージを使用して、エンドユーザーのコンピューターを起動します。

    通常、次のいずれかの方法を使用して、dart の回復イメージの展開方法に応じて DaRT を起動し、リモートコンピューターを回復します。 DaRT リカバリ画像の展開について詳しくは、「 [dart 7.0 リカバリイメージの展開](deploying-the-dart-70-recovery-image-dart-7.md)」をご覧ください。

    -   問題のあるコンピューターの回復パーティションから DaRT に起動します。

    -   ネットワーク上のリモートパーティションから DaRT に起動します。

    各方法の長所と短所については、「 [DaRT 7.0 回復イメージの保存と展開の計画](planning-how-to-save-and-deploy-the-dart-70-recovery-image.md)」を参照してください。

    DaRT を起動するために使用する方法にかかわらず、エンドユーザーが使用できるようにするブートオプションについては、BIOS でブートデバイスを有効にする必要があります。

    **注**  
    BIOS の構成は、ハードディスクドライブの種類、ネットワークアダプター、および組織で使用されているその他のハードウェアに応じて固有です。



2.  コンピュータが DaRT リカバリイメージとして起動すると、 **Netstart**ダイアログボックスが表示されます。 ネットワークサービスを初期化するかどうかを確認するメッセージが表示されます。 [**はい**] をクリックすると、ネットワークに DHCP サーバーが存在し、サーバーから IP アドレスを取得しようとしたと見なされます。 ネットワークで DHCP の代わりに静的 IP アドレスを使用している場合は、後で DaRT の**Tcp/ip 構成**ツールを使って静的 ip アドレスを指定できます。

    ネットワーク初期化プロセスをスキップするには、[**いいえ**] をクリックします。

3.  [ネットワークの初期化] ダイアログボックスで、ドライブ文字を再マップするかどうかを確認するメッセージが表示されます。 Windows online を実行すると、通常、システムボリュームは C ドライブにマップされます。ただし、WinRE で Windows オフラインを実行すると、元のシステムボリュームが別のドライブにマップされている可能性があります。これによって混乱が生じることがあります。 再マッピングする場合、DaRT はオンラインのドライブ文字と一致するように、オフラインのドライブ文字をマッピングしようとします。 再マッピングは、起動プロセスでオフラインのオペレーティングシステムが選択されている場合にのみ実行されます。

4.  [再マッピング] ダイアログボックスで、[**システム回復オプション**] ダイアログボックスが表示され、キーボードレイアウトを選択するように求められます。 次に、システムルートディレクトリ、インストールされているオペレーティングシステムの種類、パーティションサイズが表示されます。 使用しているオペレーティングシステムが表示されず、ドライバーが見つからないことが原因で問題が発生している可能性がある場合は、[**ドライバーの読み込み**] をクリックして問題のあるドライバーを読み込みます。 デバイスのインストールメディアを挿入して、ドライバーを選択するように求められます。 修復または診断するインストールを選択し、[**次へ**] をクリックします。

    **注**  
    Windows 回復環境 (WinRE) で、前回の試用時に Windows 7 が正常に起動しなかったことが検出された場合は、**スタートアップ修復**が自動的に開始されることがあります。 この問題を解決する方法などの状況については、「 [DaRT 7.0 のトラブルシューティング](troubleshooting-dart-70-new-ia.md)」を参照してください。



~~~
If any of the registry hives are corrupted or missing, Registry Editor, and several other DaRT utilities, will have limited functionality. If no operating system is selected, some tools will not be available.

The **System Recovery Options** window appears and lists various recovery tools.
~~~

5. [**システム回復オプション**] ウィンドウで、[ **Microsoft 診断/回復ツールセット**] を選択し、[**診断/回復ツールセット**] ウィンドウを開きます。

6. [**診断/回復ツールセット**] ウィンドウで、[**リモート接続**] をクリックして**DaRT リモート接続**ウィンドウを開きます。 ヘルプデスクのリモートアクセスの指定を求められたら、[ **OK]** をクリックします。

   DaRT リモート接続ウィンドウが開き、チケット番号、IP アドレス、ポート情報が表示されます。

7. ヘルプデスクエージェントのコンピューターで、 **DaRT リモート接続ビューアー**を開きます。

   [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Dart 7**]、[ **dart リモート接続ビューアー**] の順にクリックします。

8. **DaRT リモート接続**ウィンドウで、必要なチケット、IP アドレス、ポート情報を入力します。

   **注**  
   この情報は、エンドユーザーのコンピューター上に作成され、エンドユーザーによって提供される必要があります。 エンドユーザーコンピューターで利用可能な IP アドレスの数に応じて、複数の IP アドレスを選ぶことができます。



9. **[接続]** をクリックします。

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


[DaRT 7.0 を使用したコンピューターの回復](recovering-computers-using-dart-70-dart-7.md)









