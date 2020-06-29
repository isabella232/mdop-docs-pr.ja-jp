---
title: リモート パーティションとして DaRT の回復イメージを展開する方法
description: リモート パーティションとして DaRT の回復イメージを展開する方法
author: dansimp
ms.assetid: 757c9340-8eac-42e8-85de-4302e436713a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a3acdbf72a2c6dac0238f868c7280f1c389b1311
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823567"
---
# リモート パーティションとして DaRT の回復イメージを展開する方法


DaRT Recovery イメージウィザードの実行と回復イメージの作成が完了したら、ISO イメージファイルから boot.ini ファイルを抽出し、ネットワーク上のリモートパーティションとして展開することができます。

**DaRT をリモートパーティションとして展開するには**

1.  DaRT ISO イメージファイルから boot.ini ファイルを抽出します。

    1.  画像をマウントするための会社の推奨される方法を使用して、[**スタートアップイメージの作成**] ダイアログボックスで作成した ISO イメージファイルをマウントします。

    2.  ISO イメージファイルを開き、マウントされた画像の \\ ソースフォルダーからコンピューター上または外部ドライブ上の場所に boot.ini ファイルをコピーします。

        **注** 回復イメージの CD または DVD を書き込んだ場合、CD または DVD 上のファイルを開いて、\\ ソースフォルダーから boot.ini ファイルをコピーできます。 これにより、イメージのマウントの必要性をスキップできます。

         

2.  エンタープライズ内のエンドユーザーコンピューターからアクセスできる WDS サーバーに boot.ini ファイルを展開します。

3.  標準の WDS 展開手順に従って、DaRT 用の boot.ini ファイルを使用するように WDS サーバーを構成します。

DaRT をリモートパーティションとして展開する方法の詳細については、次を参照してください。

-   [チュートリアル: PXE を使用して画像を展開する](https://go.microsoft.com/fwlink/?LinkId=212108)

-   [Windows 展開サービスのクイックスタートガイド](https://go.microsoft.com/fwlink/?LinkId=212106)

## 関連トピック


[DaRT 7.0 の回復イメージの展開](deploying-the-dart-70-recovery-image-dart-7.md)

 

 





