---
title: エンドユーザーのコンピューター以外のコンピューターでスタンドアロン モードでクラッシュ アナライザーを実行する方法
description: エンドユーザーのコンピューター以外のコンピューターでスタンドアロン モードでクラッシュ アナライザーを実行する方法
author: dansimp
ms.assetid: 881d573f-2f18-4c5f-838e-2f5320179f94
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6f398c56b7c631145388541b71229d69c16bf6f3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822787"
---
# エンドユーザーのコンピューター以外のコンピューターでスタンドアロン モードでクラッシュ アナライザーを実行する方法


Windows 用 Microsoft デバッグツールまたはエンドユーザーコンピューター上のシンボルファイルにアクセスできない場合は、問題のあるコンピューターからダンプファイルをコピーし、スタンドアロンバージョンの Crash Analyzer がインストールされているコンピューター (ヘルプデスクの管理者のコンピューターなど) で分析することができます。

**スタンドアロンモードでクラッシュアナライザーを実行するには**

1.  DaRT7 がインストールされているコンピューターで、[すべてのプログラムを**起動**する  /  **All Programs**  /  **Microsoft DaRT 7**] をクリックします。

2.  次の項目に必要な情報を入力します。

    -   Windows 用 Microsoft デバッグツール

    -   シンボルファイル

        シンボルファイルの詳細については、「 [Crash Analyzer がシンボルファイルにアクセスできることを確認する方法](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-7.md)」を参照してください。

    -   クラッシュダンプファイル

        **注** DaRT7 の検索ツールを使用して、コピーしたクラッシュダンプファイルを特定します。

         

3.  クラッシュ**ダンプファイルがスキャンさ**れ、クラッシュの原因と思われるエラーが報告されます。 クラッシュの詳細については、具体的なクラッシュメッセージと説明、クラッシュの発生時に読み込まれたドライバー、分析の完全な出力などを参照してください。

4.  問題を解決するための適切な戦略を決定します。 これには、DaRT の**コンピューター管理**ツールの [**サービスとドライバー** ] ノードを使用して、クラッシュの原因となったデバイスドライバーの無効化または更新が必要になることがあります。

## 関連トピック


[クラッシュ アナライザーを使用したシステム障害の診断](diagnosing-system-failures-with-crash-analyzer--dart-7.md)

 

 





