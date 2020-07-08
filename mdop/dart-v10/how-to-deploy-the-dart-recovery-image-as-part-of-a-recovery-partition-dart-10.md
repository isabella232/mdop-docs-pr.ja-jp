---
title: 回復パーティションの一部として DaRT の回復イメージを展開する方法
description: 回復パーティションの一部として DaRT の回復イメージを展開する方法
author: dansimp
ms.assetid: 0d2192c1-4058-49fb-b0b6-baf4699ac7f5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: bc5f295d35dff1e4fc2a84c47188be40153b85c6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813067"
---
# 回復パーティションの一部として DaRT の回復イメージを展開する方法


Microsoft 診断/回復ツールセット (DaRT) 10 回復イメージウィザードの実行と回復イメージの作成が完了したら、ISO イメージファイルから boot.ini ファイルを抽出し、Windows 10 イメージの回復パーティションとして展開することができます。 Windows オペレーティングシステムを起動できない破損の問題によっては、回復イメージも開始できないため、パーティションをお勧めします。 別のパーティションを使うと、BitLocker 回復キーを2回入力する必要もなくなります。 ユーザーがファイルを保存できないように、パーティションを非表示にすることを検討してください。

**Windows 10 イメージの回復パーティションに DaRT を展開するには**

1.  **DaRT 10 の回復イメージウィザード**を使って作成した ISO イメージファイルのサイズ以上のターゲットパーティションを Windows 10 イメージで作成します。

    DaRT のパーティションに必要な最小サイズは、DaRT のリモート接続機能に合わせて500MB ます。

2.  DaRT ISO イメージファイルから boot.ini ファイルを抽出します。

    1.  会社の推奨される方法を使用して、[**スタートアップイメージの作成**] ページで作成した ISO イメージファイルをマウントします。

    2.  ISO イメージファイルを開き、マウントされた画像の \\ ソースフォルダーからコンピューター上または外部ドライブ上の場所に boot.ini ファイルをコピーします。

        **注** 回復イメージの CD、DVD、または USB を書き込んだ場合は、リムーバブルメディア上のファイルを開いて、\\ ソースフォルダーから boot.ini ファイルをコピーできます。 Boot.ini ファイルをコピーする場合は、イメージをマウントする必要はありません。

         

3.  Boot.ini ファイルを使用して、ユーザー設定の Windows RE イメージを作成するための会社の標準的な方法を使用して、起動可能な回復パーティションを作成します。

    回復パーティションを作成またはカスタマイズする方法の詳細については、「 [WINDOWS RE エクスペリエンスをカスタマイズ](https://go.microsoft.com/fwlink/?LinkId=214222)する」を参照してください。

4.  Windows 10 イメージのターゲットパーティションを回復パーティションと置き換えます。

    システム障害が発生した場合に、回復ソリューションを展開してファクトリイメージを再インストールする方法について詳しくは、「[システム回復イメージの展開](https://go.microsoft.com/fwlink/?LinkId=214221)」をご覧ください。

## 関連トピック


[DaRT 10 の回復イメージの作成](creating-the-dart-10-recovery-image.md)

[DaRT の回復イメージの展開](deploying-the-dart-recovery-image-dart-10.md)

[DaRT 10 の計画](planning-for-dart-10.md)

 

 





