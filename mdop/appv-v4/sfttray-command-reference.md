---
title: SFTTRAY コマンド リファレンス
description: SFTTRAY コマンド リファレンス
author: dansimp
ms.assetid: 6fa3a939-b047-4d6c-bd1d-dfb93e065eb2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 45a664b91ff7edd5f8536f035417cc3b0f52d7ca
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815354"
---
# SFTTRAY コマンド リファレンス


Microsoft Application Virtualization (App-v) クライアントトレイアプリケーションである sfttray.exe は、通常の使用時にユーザーが操作する app-v クライアントのメインユーザーインターフェイス要素です。 このプログラムは、すべての仮想アプリケーションのストリーミングと開始を制御し、通知領域に表示されるアイコンを右クリックしてクライアント機能のメニューを表示することによってアクセスされます。 メニューを使用すると、ユーザーはアプリケーションの読み込み、発行の更新の開始、要求のキャンセル、またはクライアントのオフラインモードへの変更を行うことができます。 ユーザーは、[**終了**] をクリックして、Application Virtualization クライアントトレイアプリケーションとアクティブなすべてのアプリケーションを終了することもできます。

既定では、仮想アプリケーションが開始されるたびにアイコンが表示されますが、この動作は、SFTTRAY コマンドを使って制御できます。 Application Virtualization クライアントトレイアプリケーションには、起動された各アプリケーションの進行状況バーと、アクティブなアプリケーションに関する状態メッセージも表示されます。 進行状況バーをクリックすると、アプリケーションの読み込みまたは開始をキャンセルできることを示すメッセージが表示されます。

## SFTTRAY コマンド


コマンドウィンドウから次のコマンドを実行すると、コマンドとコマンドラインスイッチの一覧を表示できます。

**注**  
アプリケーションの仮想化クライアントのトレイインスタンスは、ユーザーコンテキストごとに1つしかありません。そのため、新しい SFTTRAY コマンドを開始すると、既に実行されているプログラムに渡されます。



`Sfttray.exe /?`

### コマンドの使用方法

`Sfttray.exe [/HIDE | /SHOW]`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] [/EXE alternate-exe] /LAUNCH app [args]`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] /LOAD app [/SFTFILE sft]`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] /LOADALL`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] /REFRESHALL`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] /LAUNCHRESULT <UNIQUE ID>  /LAUNCH app [args]`

`Sfttray.exe /EXIT`

### コマンドラインスイッチ

SFTTRAY コマンドラインスイッチについては、次の表を参照してください。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">スイッチ</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>/非表示</p></td>
<td align="left"><p>Windows 通知領域の SFTTRAY アイコンを非表示にします。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/SHOW</p></td>
<td align="left"><p>Windows 通知領域に SFTTRAY アイコンを表示します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/QUIET</p></td>
<td align="left"><p>ユーザーの確認が必要なメッセージボックスの表示を回避して、無人使用をサポートします。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/Exe &lt; 代替 exe&gt;</p></td>
<td align="left"><p>/LAUNCH と共に使用して、OSD で指定されたターゲットファイルの代わりに仮想アプリケーションが開始される場合に、実行可能プログラムを仮想環境で開始することを指定します。</p>
<div class="alert">
<strong>注</strong><br/><p>たとえば、"SFTTRAY.EXE/EXE REGEDIT.EXE/LAUNCH app" を使って、 &lt; &gt; アプリケーションが実行されている仮想環境のレジストリを調べることができます。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>/LAUNCH &lt; アプリ &gt; [ &lt; args &gt; ]</p></td>
<td align="left"><p>仮想アプリケーションを起動します。 アプリケーションの名前とバージョン、または OSD ファイルへのパスを指定します。 必要に応じて、コマンドライン引数を仮想アプリケーションに渡すことができます。</p>
<div class="alert">
<strong>注</strong><br/><p>使用可能な仮想アプリケーションの名前とバージョンの一覧を取得するには、"SFTMIME.EXE/QUERY OBJ: APP/SHORT" というコマンドを使用します。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>/読み込み</p></td>
<td align="left"><p>仮想アプリケーションを読み込むか、インポートします。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>すべて loadall</p></td>
<td align="left"><p>すべてのアプリケーションをキャッシュに読み込みます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/REFRESHALL</p></td>
<td align="left"><p>すべてのアプリケーションの公開更新を開始します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/LAUNCHRESULT の &lt; 固有 ID&gt;</p></td>
<td align="left"><p>グローバルイベントと、固有の ID の指定されたルート名に基づくメモリマップトファイルを使用して sfttray.exe を起動するプロセスに対して、起動結果コードを返します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/SFTFILE &lt; sft&gt;</p></td>
<td align="left"><p>アプリケーションの SFT ファイルへのパスを指定するために、/LOAD と共にオプションのスイッチを使用します。 指定すると、アプリは読み込まれずにインポートされます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/終了</p></td>
<td align="left"><p>SFTTRAY プログラムとすべてのアクティブな仮想アプリケーションを閉じ、Windows 通知領域からアイコンを削除します。</p></td>
</tr>
</tbody>
</table>



**注**  
¹ */launchresult*コマンドラインパラメーターは、グローバルイベントのルート名を指定するために sfttray.exe を起動するための手段を提供します。また、プロセスに起動結果コードを返すために使用されるメモリマップファイルが用意されています。 仮想環境内で起動プロセスが呼び出されたときに、イベント名が仮想化されないようにするには、一意の識別子の名前を "SFT-" で開始する必要があります。 メモリマップ領域は、64ビットのサイズになります。

このパラメーターを使うには、"一意の id-result \ _event" という名前のイベントを作成します。このイベントには、"一意の id- &lt; &gt; result \ _value" という名前のメモリマップファイル &lt; と、必要に応じて &gt; "一意の &lt; id &gt; -shutdown \ _event sfttray.exe" という名前のイベントが生成されます。 イベント " &lt; 一意 &gt; の ID-result \ _event" がシグナル状態になると、起動プロセスで、メモリマップ領域から64ビットのリターンコードが取得されます。

&lt; &gt; 仮想アプリケーションの終了時に、"一意の ID-shutdown \ _event" という省略可能なイベントが発生すると、sfttray.exe が開き、イベントが通知されます。 起動プロセスは、仮想アプリケーションが終了するタイミングを判断する必要がある場合に、このシャットダウンイベントを待機します。











