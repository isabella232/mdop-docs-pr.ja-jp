---
title: App-V Client をアンインストールする方法
description: App-V Client をアンインストールする方法
author: dansimp
ms.assetid: 07591270-9651-4bb5-a5b3-e0fc009bd9e2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: acb3f53b42027ff2c1b84fd2ab2bdde3c52f96de
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816524"
---
# App-V Client をアンインストールする方法


次の手順を使用して、コンピューターからアプリケーションの仮想化クライアントをアンインストールします。

**Application Virtualization デスクトップクライアントをアンインストールするには**

1.  コントロールパネルで、[プログラムの**追加と削除**] (または Windows Vista、[**プログラムと機能**]) をダブルクリックして、[ **Microsoft Application Virtualization Desktop Client**] をダブルクリックします。

2.  ダイアログボックスが表示されたら、[**はい**] をクリックしてアンインストールプロセスを続行します。

    **重要** アンインストールプロセスをキャンセルまたは中断することはできません。

     

3.  続行する前に Microsoft Application Virtualization Client Tray アプリケーションを閉じておく必要があることを示すメッセージが表示されたら、通知領域の [App-V] アイコンを右クリックし、[**終了**] を選択してアプリケーションを閉じます。 次に、[**再試行**] をクリックして、アンインストールプロセスを続行します。

    **重要** 1つまたは複数の仮想アプリケーションが使用されていることを示すメッセージが表示されることがあります。 続行する前に、開いているアプリケーションを閉じてデータを保存します。 [ **OK** ] をクリックして、アンインストールプロセスを続行します。

     

4.  進行状況バーに残りの時間が表示されます。 この手順が完了したら、アンインストールプロセスを完了するために、関連するすべてのドライバーを停止できるように、コンピューターを再起動する必要があります。

    **注** アンインストールプロセスが完了すると、次のレジストリキーが保持されます。

    -   HKEY \ _LOCAL \ _MACHINE ¥¥¥¥¥¥ | |

    -   HKEY \ _LOCAL \ _MACHINE ¥¥¥¥¥¥¥¥¥¥¥¥ # softgrid¥5

    -   HKEY \ _LOCAL \ _MACHINE \ ソフトウェア \\ wow6432node¥¥ 5Softgrid\\ 4.8 5 \ systemguard "クライアント" = dword: 00000000

    -   HKEY \ _LOCAL \ _MACHINE ¥¥¥¥¥¥¥¥¥¥¥¥¥¥¥¥¥¥¥¥ |

     

## 関連トピック


[コマンド ラインを使用してクライアントをインストールする方法](how-to-install-the-client-by-using-the-command-line-new.md)

[Application Virtualization Client を手動でインストールする方法](how-to-manually-install-the-application-virtualization-client.md)

[クライアントで仮想アプリケーションを公開する方法](how-to-publish-a-virtual-application-on-the-client.md)

 

 





