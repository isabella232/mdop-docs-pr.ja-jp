---
title: クライアント ログ ファイルを構成する方法
description: クライアント ログ ファイルを構成する方法
author: dansimp
ms.assetid: dd79f8ce-61e2-4dc8-af03-2a353554a1b2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 729089d683c5d102eb7eb45314583023d3362639
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817797"
---
# クライアント ログ ファイルを構成する方法


次の手順を使用して、Application Virtualization (App-v) クライアントログファイルを構成することができます。

**ログファイルの場所を変更するには**

-   次のレジストリキーの値を編集して、ログファイルの新しいパスを指定します。 この値を変更した後で、 **sftlist**サービスを再起動する必要があります。 この場所は、インストール後に対話的に変更することもできます。

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\LogFileName

**ログレポートのレベルを変更するには**

-   既定では、ログに書き込まれるメッセージの種類には、重大度レベル 4 (情報) 以上のすべてのイベントが含まれます。 重大度レベルは、次のキー値に格納されます。 詳細ログを有効にするには、このキー値を5に設定します。 詳細ログは、非常に大量のメッセージを生成し、ログがすぐにいっぱいになるため、トラブルシューティングの際には短い期間のみ使用してください。

    HKEY \ _LOCAL \ _MACHINE ¥ $ ¥ (英語) \ のソフトの最小の構成 \\ logminseverity

**ログサイズを変更するには**

-   Application Virtualization (App-v) 4.5 では、ログサイズは次のレジストリキー値によって制御されます。 この値は既定で256MB になり、リセットされるまでにログが増加する最大サイズ (MB 単位) を定義します。

    HKEY \ _LOCAL \ _MACHINE ¥ $ ¥ (英語) \ すべてのソフト (\\) \ logmaxsize

    **注意** ログファイルがリセットされるようにするには、このレジストリキーの値を0より大きい値に設定する必要があります。

     

**バックアップコピーの数を変更するには**

-   ログファイルが最大サイズに達すると、ログの次の書き込みが発生するときにリセットが強制されます。 リセットすると、新しいログファイルが作成され、古いファイルはバックアップとして名前が変更されます。 次のレジストリ設定は、ファイルがリセットされたときに保持されるログファイルのバックアップコピーの数を制御します。 既定値は4です。

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\LogRolloverCount

    バックアップログファイル名の形式は次のとおりです。再設定時刻 (UTC) でのリセット時間に基づいて、 **sftlog\_YYYYMMDD\_hhmmss-uuu.txt**が表示されます。 次の表に、ファイル名とその説明の作成に使用する記号を示します。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">シンボル</th>
    <th align="left">説明</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>YYYY</p></td>
    <td align="left"><p>4桁の年</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>TU</p></td>
    <td align="left"><p>2桁の月 (01 ~ 12)</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>DD</p></td>
    <td align="left"><p>月を2桁の日付で表記します (01 ~ 31)。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>かつ</p></td>
    <td align="left"><p>hour (00 ~ 23)</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>tu</p></td>
    <td align="left"><p>分 (00 ~ 59)</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>ss</p></td>
    <td align="left"><p>秒 (00 ~ 59)</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>uuu</p></td>
    <td align="left"><p>ミリ秒 (000 ~ 999)</p></td>
    </tr>
    </tbody>
    </table>

     

## 関連トピック


[コマンド ラインを使用して App-V Client レジストリ設定を構成する方法](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

 

 





