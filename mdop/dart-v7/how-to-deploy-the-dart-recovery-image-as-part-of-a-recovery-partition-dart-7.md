---
title: 回復パーティションの一部として DaRT の回復イメージを展開する方法
description: 回復パーティションの一部として DaRT の回復イメージを展開する方法
author: dansimp
ms.assetid: 462f2d08-f03b-4a07-b2d3-c69205dc6f70
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e75c3f9e58d784c13003feb84001f89c4607115d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823557"
---
# 回復パーティションの一部として DaRT の回復イメージを展開する方法


DaRT Recovery イメージウィザードの実行と回復イメージの作成が完了したら、ISO イメージファイルから boot.ini ファイルを抽出して、Windows 7 イメージの回復パーティションとして展開することができます。

**Windows 7 イメージの回復パーティションに DaRT を展開するには**

1.  **DaRT 回復イメージウィザード**を使用して作成した ISO イメージファイルと同じサイズまたは大きいサイズのターゲットパーティションを Windows 7 イメージで作成します。

    DaRT パーティションに必要な最小サイズは約300MB です。 ただし、DaRT のリモート接続機能に対応する450MB をお勧めします。

2.  DaRT ISO イメージファイルから boot.ini ファイルを抽出します。

    1.  画像をマウントするための会社の推奨される方法を使用して、[**スタートアップイメージの作成**] ダイアログボックスで作成した ISO イメージファイルをマウントします。

    2.  ISO イメージファイルを開き、マウントされた画像の \\ ソースフォルダーからコンピューター上または外部ドライブ上の場所に boot.ini ファイルをコピーします。

        **注** 回復イメージの CD または DVD を書き込んだ場合、CD または DVD 上のファイルを開いて、\\ ソースフォルダーから boot.ini ファイルをコピーできます。 これにより、イメージのマウントの必要性をスキップできます。

         

3.  Boot.ini ファイルを使用して、ユーザー設定の Windows RE イメージを作成するための会社の標準的な方法を使用して、起動可能な回復パーティションを作成します。

    回復パーティションを作成またはカスタマイズする方法の詳細については、「 [WINDOWS RE エクスペリエンスをカスタマイズ](https://go.microsoft.com/fwlink/?LinkId=214222)する」を参照してください。

4.  Windows 7 イメージのターゲットパーティションを回復パーティションと置き換えます。

Windows 7 の画像の準備ができたら、会社の標準の画像展開プロセスを使用して、画像を社内のコンピューターに配布します。 Windows 7 イメージの作成方法の詳細については、「 [windows 7 の標準イメージの構築: ステップバイステップガイド](https://go.microsoft.com/fwlink/?LinkId=212103)」を参照してください。

システム障害が発生した場合に、回復ソリューションを展開してファクトリイメージを再インストールする方法について詳しくは、「[システム回復イメージの展開](https://go.microsoft.com/fwlink/?LinkId=214221)」をご覧ください。

## 関連トピック


[DaRT 7.0 の回復イメージの展開](deploying-the-dart-70-recovery-image-dart-7.md)

 

 





