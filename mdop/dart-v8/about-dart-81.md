---
title: DaRT 8.1 について
description: DaRT 8.1 について
author: dansimp
ms.assetid: dcaddc57-0111-4a9d-8be9-f5ada0eefa7d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 29c7522b4f5a5da3b451b23f2fd200db44bb9481
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821264"
---
# DaRT 8.1 について


Microsoft 診断/回復ツールセット (DaRT) 8.1 には、このトピックで説明されている次の機能強化が用意されています。

## <a href="" id="what-s-new"></a>新機能


-   **WIMBoot のサポート**

    診断/回復ツールセット8.1 は、次の条件が満たされた場合に、Windows イメージファイル起動 (WIMBoot) 環境をサポートします。

    -   WIMBoot は、Windows 8.1 Update 1 以降に基づいています。

    -   DaRT 8.1 イメージは、Windows 8.1 Update 1 以降で作成されています。

    WIMBoot の詳細については、「 [Windows イメージファイルブート (WIMBoot) の概要](https://go.microsoft.com/fwlink/?LinkId=517536)」を参照してください。

-   **Windows Server 2012 R2 および Windows 8.1 のサポート**

    DaRT 画像を作成するには、Windows Server 2012 R2 または Windows 8.1 を使用します。

    **注**  
    以前のバージョンの Windows Server と Windows オペレーティングシステムの場合は、引き続き以前のバージョンの DaRT を使用してください。



-   **カスタマー フィードバック**

    DaRT 8.1 には、DaRT 8.0 SP1 のリリース以降に発生した問題に対処する更新が含まれています。

-   **Windows Defender**

    Windows 8.1 の windows Defender には、保護が強化されています。 この変更によって、Windows Defender での DaRT の使い方に影響はありません。

## 要件


-   **Windows アセスメント & 開発キット8.1**

    Windows アセスメント & 開発キット (ADK) 8.1 は、DaRT 回復イメージウィザードの必須条件です。 Windows ADK 8.1 には、Windows イメージのカスタマイズ、展開、およびサービスのために使用される展開ツールが含まれています。 また、Windows Preinstallation Environment (Windows PE) も含まれています。

    **注**  
    リモート接続ビューアーまたはクラッシュアナライザーのみをインストールする場合は、Windows ADK 8.1 は必要ありません。



~~~
To download Windows ADK 8.1, see [Windows Assessment and Deployment Kit (Windows ADK) for Windows 8.1](https://www.microsoft.com/download/details.aspx?id=39982) in the Microsoft Download Center.
~~~

-   **Microsoft .NET Framework 4.5.1**

    DaRT 8.1 には、.NET Framework 4.5.1 がインストールされている必要があります。 ダウンロードについては、Microsoft ダウンロードセンターの[Microsoft.NET Framework 4.5.1](https://go.microsoft.com/fwlink/?LinkId=329038)を参照してください。

-   **Windows 8.1 デバッグツール**

    DaRT 8.1 でクラッシュ解析ツールを使用するには、Windows 8.1 用ソフトウェア開発キットで利用できる必要なデバッグツールが必要です。

    ダウンロードについては、Microsoft ダウンロードセンターの[windows 8.1 用 Windows ソフトウェア開発キット (SDK)](https://msdn.microsoft.com/library/windows/desktop/bg162891.aspx)を参照してください。

## 使用可能な言語


DaRT 8.1 は以下の言語で利用できます。

-   英語 (米国) en-us

-   フランス語 (フランス) fr-fr

-   イタリア語 (イタリア) it IT IT

-   ドイツ語 (ドイツ) デデュープ

-   スペイン語、インターナショナルソート (スペイン) es

-   韓国語 (韓国) ko-KR

-   日本語 (日本) ja-jp

-   ポルトガル語 (ブラジル) pt-BR

-   ロシア語 (ロシア) ru-RU

-   繁体字中国語 zh-cn&platform

-   簡体字中国語 zh-cn&platform-CN

## MDOP 技術の入手方法


DaRT 8.1 は、Microsoft デスクトップ最適化パック (MDOP) に含まれています。 MDOP は、Microsoft ソフトウェアアシュアランスの一部です。 Microsoft ソフトウェアアシュアランスの詳細と MDOP の入手方法については、「 [mdop の入手方法](https://go.microsoft.com/fwlink/?LinkId=322049)」を参照してください https://go.microsoft.com/fwlink/?LinkId=322049) 。

## 関連トピック


[DaRT 8.1 のリリース ノート](release-notes-for-dart-81.md)









