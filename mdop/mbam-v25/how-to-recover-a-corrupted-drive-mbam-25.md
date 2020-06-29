---
title: 破損しているドライブを回復する方法
description: 破損しているドライブを回復する方法
author: dansimp
ms.assetid: fa5b846b-dda6-4ae4-bf6c-39e4f1d8aa00
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: fd9fd8a65d57cbfe965197fa26b57319ee046784
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822554"
---
# 破損しているドライブを回復する方法


この手順は、BitLocker で保護されている破損したドライブを回復するために、管理と監視の Web サイト (ヘルプデスクとも呼ばれます) と共に使用できます。 これを行うには、次の表で説明されているタスクを実行します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">タスク</th>
<th align="left">詳細と詳細情報</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong> </strong> 管理と監視の web サイトのドライブ回復領域にアクセスして、回復キーパッケージファイルを作成します。</p></td>
<td align="left"><p>[ドライブ回復] 領域にアクセスするには、 <strong> </strong> Mbam ヘルプデスクユーザーロールまたは Mbam Advanced ヘルプデスクユーザーの役割が割り当てられている必要があります。 これらの役割は、作成時に異なる名前を指定した可能性があります。 詳細については、「 <a href="planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles" data-raw-source="[Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles)"> MBAM 2.5 のグループとアカウントの計画」を参照してください </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>破損したドライブが含まれているコンピューターにパッケージファイルをコピーします。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>このコマンドを使用し <code>repair-bde</code> て回復プロセスを完了します。</p></td>
<td align="left"><p>データが失われる可能性を回避するには、 <a href="https://go.microsoft.com/fwlink/?LinkId=393567" data-raw-source="[Manage-bde](https://go.microsoft.com/fwlink/?LinkId=393567)"> 使用前に manage-bde コマンドを確認することを強くお勧めし </a> ます。</p></td>
</tr>
</tbody>
</table>

 

**破損したドライブを回復するには**

1.  Web ブラウザーを開き、**管理と監視の Web サイト**に移動します。

2.  左側のウィンドウで、[**ドライブの回復**] を選択して、[**暗号化されたドライブへのアクセスを回復**する] ページを開きます。

3.  エンドユーザーの Windows ログオンドメインとユーザー名、ドライブのロックを解除する理由、およびエンドユーザーの回復パスワード ID を入力します。

    **注** 上級のヘルプデスクユーザーアクセスグループのメンバーである場合は、ユーザーのドメイン名またはユーザー名を入力する必要はありません。

     

4.  **[送信]** をクリックします。 回復キーが表示されます。

5.  [**保存**] をクリックし、[**回復キーパッケージ**] を選択します。 回復キーパッケージはコンピューター上に作成されます。

6.  破損したドライブがあるコンピューターに回復キーパッケージをコピーします。

7.  管理者特権でコマンド プロンプトを開きます。 この操作を行うには、[**スタート**] をクリックし `cmd` 、[**プログラムとファイルの検索**] テキストボックスに入力します。 [ **cmd.exe**] を右クリックし、[**管理者として実行**] を選択します。

8.  コマンドプロンプトで、次のように入力します。

    `repair-bde <corrupted drive> <fixed drive> -kp <location of keypackage> -rp <recovery password>`

    **注** 破損した &lt; ドライブ上のデータと同サイズ以上の空き領域がある、使用可能なハードディスクドライブに*固定ドライブ*を置き &gt; ます。 破損したドライブ上のデータが回復され、指定されたハードディスクドライブに移動されます。

     


## 関連トピック


[MBAM 2.5 での BitLocker 管理の実行](performing-bitlocker-management-with-mbam-25.md)

 
## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。
 





