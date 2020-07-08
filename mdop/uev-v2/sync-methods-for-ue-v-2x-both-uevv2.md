---
title: UE-V 2.x の同期方法
description: UE-V 2.x の同期方法
author: dansimp
ms.assetid: af0ae894-dfdc-41d2-927b-c2ab1b355ffe
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a163442e2ab3dbd777aca133b13b0086cdb8ae1a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823577"
---
# UE-V 2.x の同期方法


Microsoft User Experience Virtualization (UE-V) 2.0、2.1、2.1 SP1 エージェントを使用すると、ユーザーのアプリケーションと Windows の設定を設定の保存場所と同期することができます。 *同期方法*の構成では、ue-v Agent がアップロードし、これらの設定を設定の保存場所にダウンロードする方法を定義します。 UE-V は、 *Syncmethod*と呼ばれる新しい syncmethod を紹介します。 アプリケーションと Windows の設定の同期を開始するトリガーイベントについて詳しくは、「 [ue-v 2. x の同期トリガーイベント](sync-trigger-events-for-ue-v-2x-both-uevv2.md)」をご覧ください。

## 同期メソッドの構成


次の表では、UE-V V 1.0 から v 2.0 への変更、および各構成の設定について説明します。

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>同期メソッドの構成</strong></p></td>
<td align="left"><p><strong>V 1.0</strong></p></td>
<td align="left"><p><strong>V 2.0</strong></p></td>
<td align="left"><p><strong>V 2.1 および V 2.1 SP1</strong></p></td>
<td align="left"><p><strong>説明</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>SyncProvider</p></td>
<td align="left"><p>n/a</p></td>
<td align="left"><p>既定値</p></td>
<td align="left"><p>既定値</p></td>
<td align="left"><p>特定のアプリケーションまたはグローバル Windows デスクトップ設定の設定の変更は、キャッシュフォルダーにローカルに保存されます。 これらの変更は、同期トリガーイベントが発生したときの設定の保存場所と同期されます。 変更を反映すると、設定の保存パスにローカルの変更が保存されます。</p>
<p>この既定の設定は、コンピューターの標準です。 このオプションでは、アプリケーションまたはオペレーティングシステムの起動時の遅延が長期間に合わない場合に、しばらくの間、設定の同期とタイムアウトが試行されます。</p>
<p>この機能は、スケジュールされたタスク–同期コントローラーアプリケーションにも関連付けられています。 スケジュールされたタスクの頻度は管理者が管理します。 既定では、コンピューターはログオン後30分ごとに設定を同期します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>OfflineFiles</p></td>
<td align="left"><p>既定値</p></td>
<td align="left"><p>非推奨</p></td>
<td align="left"><p>非推奨</p></td>
<td align="left"><p>V 2.0 の SyncProvider と同じように動作します。</p>
<p>オフラインファイルが有効になっていて、フォルダーがピン留めされている場合、UE-V はこのフォルダーの固定を解除し、中央の SMB ディレクトリに直接同期します。</p>
<p><strong>注: ネットワーク </strong> 接続されていない方法 (ノート pc を使用している場合) で ue-v を使用する場合は、オフラインファイルを使用して設定を移動することをお勧めします。オフラインファイルを有効にするためのお客様からのフィードバックは、単純なエンタープライズブロックではありません。 したがって、UE-V 2 では、密結合の同期エンジンを作成してデータをローカルにキャッシュし、設定を中央のサーバーと同期します。 この機能エリアでは、オフラインファイルまたはフォルダーリダイレクションは置き換えられません。</p>
<p>UE-V 2 はオフラインフォルダーでは適切に動作しないため、このガイダンスでは、固定されたオフラインまたは CSC フォルダーへの設定の記憶域パスを設定しません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>外部</p></td>
<td align="left"><p>n/a</p></td>
<td align="left"><p>n/a</p></td>
<td align="left"><p>サポートされています</p></td>
<td align="left"><p>UE-V 2.1 では、この構成メソッドを使用して、ユーザーコンピューター上のローカルフォルダーに UE-V 設定が書き込まれる場合に、任意の外部同期エンジン (OneDrive for Business、ワークフォルダー、Sharepoint、Dropbox など) を使って、これらの設定をユーザーがアクセスするさまざまなコンピューターに適用することができます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>なし</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>この構成設定は、主に仮想デスクトップインフラストラクチャ (VDI) とストリーミングされたアプリケーションエクスペリエンス向けに設計されています。 この設定は、データセンターで使用されている Windows Server のボックスで使用する必要があります。この設定は、接続を常に利用できます。</p>
<p>設定の変更は、サーバーに直接保存されます。 設定の記憶域パスへのネットワーク接続が利用できない場合は、設定の変更はデバイスにキャッシュされ、次に同期プロバイダーが実行されるときに同期されます。 設定の保存パスが見つからず、ログオフ時にプールされた VDI 環境からユーザープロファイルが削除された場合、これらの設定の変更は保存されません。ユーザーは、コンピューターがもう一度設定の記憶域のパスに到達したときに変更を再適用する必要があります。</p>
<p>アプリと OS は、場所が存在するまで無期限に待機します。 これにより、アプリの読み込みまたは OS のログオン時間が、場所が見つからない場合に大幅に増大する可能性があります。</p></td>
</tr>
</tbody>
</table>

 

同期方法は、次の方法で構成できます。

-   コマンドラインパラメーターまたはバッチスクリプトを使用[して Ue-v agent を展開](https://technet.microsoft.com/library/dn458891.aspx#agent)する場合

-   [グループポリシー](https://technet.microsoft.com/library/dn458893.aspx)設定を使用する

-   UE-V の[System Center 構成パック](https://technet.microsoft.com/library/dn458917.aspx)

-   UE-V Agent をインストールした後、 [Windows PowerShell または Windows Management Instrumentation (WMI)](https://technet.microsoft.com/library/dn458937.aspx)を使用する






## 関連トピック


[UE-V 2.x の必要な機能を展開する](deploy-required-features-for-ue-v-2x-new-uevv2.md#ssl)

[UE-V 2.x の必要な機能を展開する](deploy-required-features-for-ue-v-2x-new-uevv2.md#config)

[UE-V 2.x のテクニカル リファレンス](technical-reference-for-ue-v-2x-both-uevv2.md)

 

 





