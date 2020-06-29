---
title: UE-V 2.x の同期トリガー イベント
description: UE-V 2.x の同期トリガー イベント
author: dansimp
ms.assetid: 4ed71a13-6a4f-4376-996f-74b126536bbc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f3e89a0370790e7f462b2f469792128dba033460
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826797"
---
# UE-V 2.x の同期トリガー イベント


Microsoft User Experience Virtualization (UE-V) 2.0、2.1、2.1 SP1 を使用すると、ドメインに参加しているすべてのデバイスでアプリケーションと Windows の設定を同期することができます。 *同期トリガーイベント*は、ue-v エージェントが設定の保存場所とこれらの設定を同期するタイミングを定義します。 UE-V 2 には、 *Syncprovider*と呼ばれる新しい*同期メソッド*が導入されています。 同期メソッドの構成の詳細については、「 [ue-v の同期メソッド](sync-methods-for-ue-v-2x-both-uevv2.md)」を参照してください。

## UE-V 2 同期トリガーイベント


次の表では、従来のアプリケーションと Windows 設定のトリガーイベントについて説明します。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>UE-V 2 トリガーイベント</strong></p></td>
<td align="left"><p><strong>SyncMethod = Syncmethod</strong></p></td>
<td align="left"><p><strong>SyncMethod = None</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Windows ログオン</strong></p></td>
<td align="left"><ul>
<li><p>アプリケーションと Windows の設定は、設定の保存場所からローカルキャッシュにインポートされます。</p></li>
<li><p><a href="https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings2" data-raw-source="[Asynchronous Windows settings](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings2)">非同期の Windows 設定 </a> が適用されます。</p></li>
<li><p>同期ウィンドウの設定は、次の Windows ログオン時に適用されます。</p></li>
<li><p>アプリケーションの設定は、アプリケーションの起動時に適用されます。</p></li>
</ul></td>
<td align="left"><ul>
<li><p>アプリケーションと Windows の設定は、[設定の保存] の場所から直接読み取ります。</p></li>
<li><p>非同期および同期ウィンドウの設定が適用されます。</p></li>
<li><p>アプリケーションの設定は、アプリケーションの起動時に適用されます。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Windows のログオフ</strong></p></td>
<td align="left"><p>変更をローカルに保存して、非同期および同期の Windows 設定を設定のストレージロケーションサーバーにコピーして (使用可能な場合)</p></td>
<td align="left"><p>非同期および同期の Windows 設定の保存場所への変更を保存する</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Windows Connect (RDP)/ロック解除</strong></p></td>
<td align="left"><p>任意の非同期 Windows 設定を設定の保存場所からローカルキャッシュに同期します (可能な場合)。</p>
<p>キャッシュされた Windows の設定を適用する</p></td>
<td align="left"><p>設定の保存場所から非同期 windows 設定をダウンロードして適用する</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Windows Disconnect (RDP)/ロック</strong></p></td>
<td align="left"><p>非同期の Windows 設定の変更をローカルキャッシュに保存します。</p>
<p>任意の非同期 Windows 設定をローカルキャッシュから設定の保存場所に同期する (利用可能な場合)</p></td>
<td align="left"><p>非同期の Windows 設定の変更を設定の保存場所に保存する</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>アプリケーションの開始</strong></p></td>
<td align="left"><p>アプリケーションの起動時にローカルキャッシュからアプリケーションの設定を適用する</p></td>
<td align="left"><p>アプリケーションの起動時に、設定の保存場所からアプリケーション設定を適用する</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>アプリケーションが閉じる</strong></p></td>
<td align="left"><p>アプリケーション設定の変更をローカルキャッシュに保存し、[設定の保存場所] (使用可能な場合) に設定をコピーします。</p></td>
<td align="left"><p>アプリケーション設定の変更を設定の保存場所に保存する</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>同期コントローラーのスケジュールされたタスクまたは "今すぐ同期" が会社の設定センターから実行される</strong></p>
<p></p></td>
<td align="left"><p>アプリケーションと Windows の設定は、設定の保存場所とローカルキャッシュの間で同期されます。</p>
<div class="alert">
<strong>注</strong><br/><p>設定の変更は、アプリケーションが閉じるまでローカルにキャッシュされません。 このトリガーは、現在実行中のアプリケーションに加えられた変更をエクスポートしません。</p>
<p>Windows の設定では、次のロック (非同期) またはログオフ (非同期および同期) まで、すべての変更がローカルにキャッシュされ、エクスポートされることを意味します。</p>
</div>
<div>

</div>
<p>設定は次の場合に適用されます。</p>
<ul>
<li><p>非同期の Windows 設定が直接適用されます。</p></li>
<li><p>アプリケーションの設定は、アプリケーションの起動時に適用されます。</p></li>
<li><p>非同期と同期の両方の Windows の設定は、次の Windows ログオン時に適用されます。</p></li>
<li><p>Windows アプリ (AppX) の設定は、次の更新時に適用されます。 <a href="https://technet.microsoft.com/library/dn458944.aspx" data-raw-source="[Monitor Application Settings](https://technet.microsoft.com/library/dn458944.aspx)"> </a> 詳細については、「アプリケーションの設定を監視する」を参照してください。</p></li>
</ul></td>
<td align="left"><p>NA</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>リモートストアで更新された非同期設定 *</strong></p></td>
<td align="left"><p>キャッシュから新しい非同期設定を読み込んで適用します。</p></td>
<td align="left"><p>中央サーバーから設定を読み込んで適用する</p></td>
</tr>
</tbody>
</table>








## 関連トピック


[UE-V 2.x のテクニカル リファレンス](technical-reference-for-ue-v-2x-both-uevv2.md)

[UE-V 2. x のスケジュールされたタスクの頻度の変更](changing-the-frequency-of-ue-v-2x-scheduled-tasks-both-uevv2.md)

[UE-V 2. x の構成方法を選択します。](https://technet.microsoft.com/library/dn458891.aspx#config)









