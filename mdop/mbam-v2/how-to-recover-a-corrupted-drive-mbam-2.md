---
title: 破損しているドライブを回復する方法
description: 破損しているドライブを回復する方法
author: dansimp
ms.assetid: b0457a00-f72e-4ad8-ab3b-7701851ca87e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5bbd4c2a1f5ef3fde78a9f72c1f77ccb0cdea377
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822874"
---
# 破損しているドライブを回復する方法


BitLocker によって保護されている破損したドライブを回復するには、Microsoft BitLocker 管理および監視 (MBAM) ヘルプデスクユーザーは回復キーパッケージファイルを作成する必要があります。 このパッケージファイルは、破損したドライブが含まれているコンピューターにコピーして、ドライブの回復に使用することができます。 この操作を実行するために必要な手順については、次の手順に従います。

**重要** データが失われる可能性を回避するために、次の手順を完了する前に、"修復-bde" のヘルプを読み、コマンドの使い方を明確に理解しておくことをお勧めします。

 

**破損したドライブを回復するには**

1.  破損したドライブを復元するために必要な回復キーパッケージを作成するには、web ブラウザーを起動して、MBAM 管理と監視 web サイトを開きます。

2.  左側のナビゲーションウィンドウから [**ドライブの回復**] を選びます。 ユーザーのドメイン名、ユーザー名、ドライブのロックを解除する理由、ユーザーの回復パスワード ID を入力します。

    **注** ヘルプデスク管理者ロールのメンバーである場合は、ユーザーのドメイン名またはユーザー名を入力する必要はありません。

     

3.  **[送信]** をクリックします。 回復キーが表示されます。

4.  [**保存**] をクリックし、[**回復キーパッケージ**] を選択します。 回復キーパッケージはコンピューター上に作成されます。

5.  破損したドライブがあるコンピューターに回復キーパッケージをコピーします。

6.  管理者特権でコマンド プロンプトを開きます。 この操作を行うには、[**スタート**] をクリックし `cmd` 、[**プログラムとファイルの検索] ボックス**に入力します。 **cmd.exe**を右クリックし、[**管理者として実行**] を選択します。

7.  コマンドプロンプトで、次のように入力します。

    `repair-bde <corrupted drive> <fixed drive> -kp <location of keypackage> -rp <recovery password>`

    **注** &lt;破損した &gt; ドライブ上のデータと同サイズ以上の空き領域がある、使用可能なハードディスクドライブに固定ドライブを置きます。 破損したドライブ上のデータが回復され、指定されたハードディスクドライブに移動されます。

     

## 関連トピック


[MBAM での BitLocker 管理の実行](performing-bitlocker-management-with-mbam-mbam-2.md)

 

 





