---
title: アプリケーションをインポートする方法
description: アプリケーションをインポートする方法
author: dansimp
ms.assetid: ab40acad-1025-478d-8e13-0e1ff1bd37e4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7d9cd6d065ca28b5d856acdae7d10a1280105e9d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817404"
---
# アプリケーションをインポートする方法


通常は、アプリケーションをインポートして、アプリケーションの仮想化管理サーバーからストリーミングできるようにします。 アプリケーションを手動で追加することもできますが、そのためには、アプリケーションに関する詳細な情報を提供する必要があります。 詳細については、「[手動でアプリケーションを追加する方法](how-to-manually-add-an-application.md)」を参照してください。

**注** アプリケーションをインポートするには、シーケンシャルオープンソフトウェア記述子 (OSD) ファイルまたはその Sequencer プロジェクト (SPRJ) ファイルがサーバーで利用できる状態になっている必要があります。

 

アプリケーションをインポートするときは、[**システムオプション**] ダイアログの **[全般**] タブにある [**既定のコンテンツパス**] フィールドにサーバーが設定されていることを確認する必要があります (このプロパティは、App-v server 本体の**application Virtualization System**ノードを右クリックするとアクセスできます)。 既定のコンテンツパスの値は、アプリケーションをインポートする場所を定義するもので、インポートプロセス時には、SFT ファイルとアイコンのショートカットの OSD ファイルで定義されたパスを変更するためにこの値を使用します。 OSD ファイルの場合、SFT ファイルのパスは CODEBASE HREF エントリで指定され、アイコンのパスはショートカットエントリで指定されます。

インポートプロセス中には、OSD ファイルの2つのパスで指定された port、server、および (存在する場合) が、既定のコンテンツパスの値に置き換えられます。 次の表では、インポートパスの影響について例を示します。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">既定のコンテンツパス</th>
<th align="left">OSD ファイルのコードベース HREF</th>
<th align="left">結果の値</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>\ \ ターミナルコンテンツ &lt; /p&gt;</td>
<td align="left"><p><a href="http://WebServer/myFolder/package.sft" data-raw-source="http://WebServer/myFolder/package.sft">http://WebServer/myFolder/package.sft</a></p></td>
<td align="left"><p>\server\content\myFolder\package.sft</p></td>
</tr>
</tbody>
</table>

 

**アプリケーションをインポートするには**

1.  左側のウィンドウで [**アプリケーション**] ノードを右クリックし、[**アプリケーションのインポート**] を選択します。

2.  [**開く**] ダイアログボックスで、アプリケーションの SPRJ または OSD ファイルに移動します。 ファイルを強調表示し、[**開く**] をクリックします。

3.  **新しいアプリケーションウィザード**で、ストリーミングするアプリケーションに対し**て [有効**] ボックスがオンになっていることを確認します。 また、説明を入力して、サーバーとファイルのパスを確認することもできます。 また、ライセンスおよびサーバーグループを設定してある場合は、それらを選ぶこともできます。

4.  **[次へ]** をクリックします。

5.  [公開された**ショートカット**] 画面で、クライアントコンピューターにアプリケーションのショートカットを表示する場所のチェックボックスをオンにします。

6.  **[次へ]** をクリックします。

7.  [**ファイルの関連付け**] 画面で、このアプリケーションに新しいファイルの関連付けを追加できます。 そのためには、[**追加**] をクリックし、拡張機能 (前のドットは不要) を入力して、説明を入力し、[ **OK]** をクリックします。

    **注** Sequencer 4.0 でシーケンス処理されたアプリケーションは、管理コンソールを使用してインポートまたは作成するときに、[**ファイルの関連付け**] ダイアログボックスを作成します。 以前のバージョンの Sequencer パッケージを使用したアプリケーションは実行されません。

     

8.  **[次へ]** をクリックします。

9.  [**アクセス許可**] 画面で、[**追加**] をクリックします。

10. **[グループの選択**] ダイアログボックスに入力します。 完了したら、[ **OK]** をクリックします。

11. **[次へ]** をクリックします。

12. [**概要**] 画面では、インポート設定を確認できます。 [**完了**] をクリックするか、[**戻る**] をクリックしてインポートを変更するか、[**キャンセル**] をクリックしてインポートをキャンセルします。

## 関連トピック


[サーバー管理コンソールでアプリケーション グループを管理する方法](how-to-manage-application-groups-in-the-server-management-console.md)

[サーバー管理コンソールでアプリケーションを管理する方法](how-to-manage-applications-in-the-server-management-console.md)

[アプリケーションを手動で追加する方法](how-to-manually-add-an-application.md)

 

 





