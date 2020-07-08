---
title: パフォーマンス カウンターを使用して App-V Client のキャッシュを管理する方法
description: パフォーマンス カウンターを使用して App-V Client のキャッシュを管理する方法
author: dansimp
ms.assetid: 49d6c3f2-68b8-4c69-befa-7598a8737d05
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 396cceaf9a3bde661200be2771a85596a512732f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817134"
---
# パフォーマンス カウンターを使用して App-V Client のキャッシュを管理する方法


次の手順を使用して、Application Virtualization (App-v) クライアントキャッシュで利用可能な空き領域を調べることができます。これにより、パフォーマンスモニターを使用して情報をグラフィカルに表示することができます。 この情報は、クライアントコンピューターで "App Virt Client Cache" という名前のパフォーマンスカウンターを使ってキャプチャされ、次のカウンターが含まれます。 "キャッシュサイズ (MB)," キャッシュの空き領域 (MB) "と"% の空き領域を増やす "というカウンターがあります。

**クライアントキャッシュスペース使用量を確認するには**

1.  管理者としてコマンドプロンプトを開くか、[**開始**]、[**実行**] の**perfmon.exe**入力して、[ **OK**] をクリックします。

2.  使用している Windows オペレーティングシステムに応じて、MMC ウィンドウが開いたら、パフォーマンスモニターまたはシステムモニターツールをクリックします。

3.  カウンターを追加するには、グラフの領域を右クリックし、[**カウンターの追加**] を選択します。

4.  ドロップダウンをクリックして利用可能なカウンターの一覧を表示し、スクロールして [ **App Virt Client Cache**] を見つけ、3つのカウンターを追加します。

    **重要** App-v のパフォーマンスカウンターは、32ビットの DLL に実装されているため、そのためには、次のコマンドを使用して、32ビットバージョンのパフォーマンスモニター ( **mmc/32 perfmon.exe**) を起動する必要があります。 このコマンドは、監視されているコンピューターで直接実行する必要があります。また、64ビットオペレーティングシステムを実行しているリモートコンピューターを監視するために使うことはできません。

     

## 関連トピック


[コマンド ラインを使用して仮想アプリケーションを管理する方法](how-to-manage-virtual-applications-by-using-the-command-line.md)

 

 





