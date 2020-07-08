---
title: 破損しているドライブを回復する方法
description: 破損しているドライブを回復する方法
author: dansimp
ms.assetid: 715491ae-69c0-4fae-ad3f-3bd19a0db2f2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 545ff5c7e6bea29d5f89cce1cf18212b7d0e2870
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812946"
---
# 破損しているドライブを回復する方法


BitLocker によって保護されている破損したドライブを回復するために、Microsoft BitLocker 管理および監視 (MBAM) ヘルプデスクユーザーは回復キーパッケージファイルを作成する必要があります。 このパッケージファイルは、破損したドライブが含まれているコンピューターにコピーして、ドライブの回復に使用することができます。 これを実現するには、次の手順を実行します。

**破損したドライブを回復するには**

1.  MBAM 管理 web サイトを開きます。

2.  ナビゲーションウィンドウから [**ドライブの回復**] を選びます。 ユーザーのドメイン名とユーザー名、ドライブのロックを解除する理由、およびユーザーの回復パスワード ID を入力します。

    **注** ヘルプデスク管理者ロールのメンバーである場合は、ユーザーのドメイン名またはユーザー名を入力する必要はありません。

     

3.  **[送信]** をクリックします。 回復キーが表示されます。

4.  [**保存**] をクリックし、[**回復キーパッケージ**] を選択します。 回復キーパッケージはコンピューター上に作成されます。

5.  破損したドライブがあるコンピューターに回復キーパッケージをコピーします。

6.  管理者特権でコマンド プロンプトを開きます。 この操作を行うには、[**スタート**] をクリックし `cmd` 、[**プログラムとファイルの検索**] ボックスに入力します。 検索結果の一覧で**cmd.exe**を右クリックし、[**管理者として実行**] を選択します。

7.  コマンドプロンプトで、次のように入力します。

    `repair-bde <fixed drive> <corrupted drive> -kp <location of keypackage> -rp <recovery password>`

    **注** コマンドの &lt; 固定ドライブの場合は &gt; 、破損したドライブ上のデータと同等またはそれ以上の空き領域がある利用可能な記憶域デバイスを指定します。 破損したドライブ上のデータが回復され、指定された固定ドライブに移動されます。

     

## 関連トピック


[MBAM での BitLocker 管理の実行](performing-bitlocker-management-with-mbam.md)

 

 





