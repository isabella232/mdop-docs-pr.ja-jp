---
title: DaRT 7.0 を展開する方法
description: DaRT 7.0 を展開する方法
author: dansimp
ms.assetid: 30522441-40cb-4eca-99b4-dff758f5c647
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c2059b64e5f3ae7af8926bc00e5965598ede4288
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813050"
---
# DaRT 7.0 を展開する方法


このトピックでは、お使いの環境に Microsoft Diagnostics and Recovery ツールセット (DaRT) 7 を展開する手順について説明します。 このトピックの最初の手順では、すべての機能を1つの管理者コンピューターにインストールすることを前提としています。 たとえば、電子的なソフトウェア配布システムを使用して、複数のコンピューターに DaRT を展開またはアンインストールする必要がある場合は、コマンドラインインストールオプションの使用が簡単になることがあります。 これらのオプションは、このトピックの2番目の手順で定義されています。ここでは、使用可能なコマンドラインオプションの使用例を示します。

**重要** DaRT をインストールする前に、コンピューターが[dart 7.0 でサポートされている構成](dart-70-supported-configurations-dart-7.md)の最小システム要件を満たしていることを確認してください。

 

**管理者コンピューターに DaRT をインストールするには**

1.  ソフトウェアのダウンロードの一部として受け取った DaRT インストールファイルを見つけます。

2.  システム要件に対応する DaRT インストールファイル (32 ビットまたは64ビット) をダブルクリックします。 DaRT のインストールファイルには**MSDaRT70.msi**という名前が付いています。

3.  Microsoft ソフトウェアライセンス条項に同意し、[**次へ**] をクリックします。

4.  DaRT をインストールする保存先フォルダーを選択し、すべてのユーザに対して DaRT をインストールするか、現在のユーザのみをインストールするかを選択して、「**次へ**」をクリックします。

5.  インストールを**標準**、**カスタム**、または**完全**のいずれにするかを選び、[**次へ**] をクリックします。

    -   **一般的**には、よく使われるツールをインストールします。 この方法は、ほとんどのユーザーにお勧めします。

    -   [**カスタム**] インストールされているツールとそのインストール場所を選択できます。 これは、特にさまざまなヘルプデスクのコンピューターにさまざまな DaRT ツールをインストールする場合に、上級ユーザーに推奨されます。

    -   **完了**すべての DaRT ツールをインストールし、最も多くのディスク領域を必要とします。

    インストール方法を選択したら、[**次へ**] をクリックします。

6.  インストールを開始するには、[**インストール**] をクリックします。

7.  インストールが正常に完了したら、[**完了**] をクリックしてウィザードを終了します。

**コマンドプロンプトで DaRT をインストールするには**

1.  次の例は、すべての DaRT 機能をインストールする方法を示しています。

    ``` syntax
    msiexec /i MSDaRT70.msi ADDLOCAL=CommonFiles,MSDaRTHelp,DaRTRecoveryImage,CrashAnalyzer,RemoteViewer 
    ```

2.  次の例は、 **DaRT Recovery イメージウィザード**のみをインストールする方法を示しています。

    ``` syntax
    msiexec /i MSDaRT70.msi ADDLOCAL=CommonFiles,MSDaRTHelp,DaRTRecoveryImage
    ```

3.  次の例は、Crash Analyzer と DaRT リモート接続ビューアーのみをインストールする方法を示しています。

    ``` syntax
    msiexec /i MSDaRT70.msi ADDLOCAL=CommonFiles,MSDaRTHelp,CrashAnalyzer,RemoteViewer 
    ```

4.  次の例では、Windows インストーラーのセットアップログを作成します。 これは、デバッグに役立ちます。

    ``` syntax
    msiexec.exe /i MSDaRT70.msi /l*v log.txt 
    ```

**注** すべての DaRT インストールコマンドプロンプトオプションに/qn または/qb を追加して、サイレントインストールを実行することができます。

 

## 関連トピック


[管理者用コンピューターへの DaRT 7.0 の展開](deploying-dart-70-to-administrator-computers-dart-7.md)

 

 





