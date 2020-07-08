---
title: USB フラッシュ ドライブを使用して DaRT の回復イメージを展開する方法
description: USB フラッシュ ドライブを使用して DaRT の回復イメージを展開する方法
author: dansimp
ms.assetid: 5b7aa843-731e-47e7-b5f9-48d08da732d6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 1228c9cb5f870162f285d726d48721dde1185107
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823667"
---
# USB フラッシュ ドライブを使用して DaRT の回復イメージを展開する方法


**DaRT Recovery イメージウィザード**の実行が完了したら、のツールを使って、 <https://go.microsoft.com/fwlink/?LinkId=218888> USB フラッシュドライブ (UFD) に ISO 画像ファイルをコピーできます。

このセクションで説明する手順に従って、手動で ISO イメージファイルを UFD にコピーすることもできます。

**DaRT リカバリ画像を USB フラッシュドライブに保存するには**

1.  USB フラッシュドライブの書式を設定します。

    1.  実行されている有効なオペレーティングシステムまたは WindowsPE セッションから、UFD を挿入します。

    2.  管理者権限を持つコマンドプロンプトで、「 **DISKPART** 」と入力して、「 **LIST DISK**」と入力します。

        [コマンドプロンプト] ウィンドウに、**ディスク 1**などの UFD のディスク番号が表示されます。

    3.  コマンドプロンプトで、次のコマンドを一度に1つずつ入力します。

        ``` syntax
        SELECT DISK 1
        CLEAN
        CREATE PARTITION PRIMARY
        SELECT PARTITION 1
        ACTIVE
        FORMAT FS=NTFS
        ASSIGN
        EXIT
        ```

        **注** 前のコード例では、Disk1 が UFD であることを前提としています。 必要に応じて、ディスク1をディスク番号に置き換えます。

         

2.  会社の推奨される方法でイメージをマウントすることによって、 **DaRT 回復イメージウィザード**の [**スタートアップイメージの作成**] ダイアログボックスで作成した ISO イメージファイルをマウントします。 このためには、画像ファイルをマウントするためのメソッドを用意する必要があります。

3.  マウントされた ISO イメージファイルを開き、そのすべての内容を、書式設定された USB フラッシュドライブにコピーします。

    **注** 回復イメージの CD または DVD を書き込んだ場合、CD または DVD 上のファイルを開いて、コンテンツを UFD にコピーできます。 これにより、イメージのマウントの必要性をスキップできます。

     

## 関連トピック


[DaRT 7.0 の回復イメージの展開](deploying-the-dart-70-recovery-image-dart-7.md)

 

 





