---
title: 回復パーティションの一部として DaRT の回復イメージを展開する方法
description: 回復パーティションの一部として DaRT の回復イメージを展開する方法
author: dansimp
ms.assetid: 07c5d539-51d9-4759-adc7-72b40d5d7bb3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e3647d684f64a0635e2875314498bde841204369
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824384"
---
# 回復パーティションの一部として DaRT の回復イメージを展開する方法


Microsoft 診断/回復ツールセット (DaRT) 8.0 回復イメージウィザードの実行と回復イメージの作成が完了したら、ISO イメージファイルから boot.ini ファイルを抽出し、Windows 8 イメージの回復パーティションとして展開することができます。 Windows オペレーティングシステムを起動できない破損の問題によっては、回復イメージも開始できないため、パーティションをお勧めします。 別のパーティションを使うと、BitLocker 回復キーを2回入力する必要もなくなります。 ユーザーがファイルを保存できないように、パーティションを非表示にすることを検討してください。

**Windows 8 イメージの回復パーティションに DaRT を展開するには**

1.  **DaRT 8.0 の回復イメージウィザード**を使って作成した ISO イメージファイルのサイズと等しい、またはそれ以上のサイズのターゲットパーティションを Windows 8 イメージで作成します。

    DaRT のパーティションに必要な最小サイズは、DaRT のリモート接続機能に合わせて500MB ます。

2.  DaRT ISO イメージファイルから boot.ini ファイルを抽出します。

    1.  会社の推奨される方法を使用して、[**スタートアップイメージの作成**] ページで作成した ISO イメージファイルをマウントします。

    2.  ISO イメージファイルを開き、マウントされた画像の \\ ソースフォルダーからコンピューター上または外部ドライブ上の場所に boot.ini ファイルをコピーします。

        **注** 回復イメージの CD、DVD、または USB を書き込んだ場合は、リムーバブルメディア上のファイルを開いて、\\ ソースフォルダーから boot.ini ファイルをコピーできます。 Boot.ini ファイルをコピーする場合は、イメージをマウントする必要はありません。

         

3.  Boot.ini ファイルを使用して、ユーザー設定の Windows RE イメージを作成するための会社の標準的な方法を使用して、起動可能な回復パーティションを作成します。

    回復パーティションを作成またはカスタマイズする方法の詳細については、「 [WINDOWS RE エクスペリエンスをカスタマイズ](https://go.microsoft.com/fwlink/?LinkId=214222)する」を参照してください。

4.  Windows 8 イメージのターゲットパーティションを回復パーティションと置き換えます。

    システム障害が発生した場合に、回復ソリューションを展開してファクトリイメージを再インストールする方法について詳しくは、「[システム回復イメージの展開](https://go.microsoft.com/fwlink/?LinkId=214221)」をご覧ください。

## 関連トピック


[DaRT 8.0 の回復イメージの作成](creating-the-dart-80-recovery-image-dart-8.md)

[DaRT の回復イメージの展開](deploying-the-dart-recovery-image-dart-8.md)

[DaRT 8.0 の計画](planning-for-dart-80-dart-8.md)

 

 





