---
title: エンドユーザーのコンピューター以外のコンピューターでスタンドアロン モードでクラッシュ アナライザーを実行する方法
description: エンドユーザーのコンピューター以外のコンピューターでスタンドアロン モードでクラッシュ アナライザーを実行する方法
author: dansimp
ms.assetid: b2f87144-6379-478a-802b-9cfef5242f34
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ebd3c50c373ba9687a3b7fcbbf34e86bd07c6207
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824374"
---
# エンドユーザーのコンピューター以外のコンピューターでスタンドアロン モードでクラッシュ アナライザーを実行する方法


Windows 用 Microsoft デバッグツールまたはエンドユーザーコンピューター上のシンボルファイルにアクセスできない場合は、問題のあるコンピューターからダンプファイルをコピーして、スタンドアロンバージョンの Crash Analyzer がインストールされているコンピューター (Microsoft 診断/回復ツールセット (DaRT) 8.0 が含まれているヘルプデスクコンピューターなど) で分析することができます。

Crash Analyzer をスタンドアロンモードで実行するには、問題のあるコンピューターからメモリダンプファイルをコピーして、**クラッシュアナライザー**がインストールされている別のコンピューター (ヘルプデスクコンピューターなど) で分析します。

**スタンドアロンモードでクラッシュアナライザーを実行するには**

1.  DaRT 8.0 がインストールされているコンピューターで、[**スタート**] をクリックし、「 **crash analyzer**」と入力して、[**クラッシュアナライザー**] をクリックします。

2.  「[エンドユーザーコンピューターでクラッシュアナライザーを実行する方法](how-to-run-the-crash-analyzer-on-an-end-user-computer-dart-8.md)」の説明に従って、ウィザードの手順に従います。

## 関連トピック


[DaRT 8.0 の操作](operations-for-dart-80-dart-8.md)

[クラッシュ アナライザーを使用したシステム障害の診断](diagnosing-system-failures-with-crash-analyzer--dart-8.md)

[クラッシュ アナライザーがシンボル ファイルにアクセスできるようにする方法](how-to-ensure-that-crash-analyzer-can-access-symbol-files.md)

 

 





