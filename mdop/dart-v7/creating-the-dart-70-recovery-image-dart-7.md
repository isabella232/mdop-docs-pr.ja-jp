---
title: DaRT 7.0 の回復イメージの作成
description: DaRT 7.0 の回復イメージの作成
author: dansimp
ms.assetid: ebb2ec58-0349-469d-a23f-3f944fe4c1fa
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f19ff144cac61ca7ea5a8498f67caf8a99229d77
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823284"
---
# DaRT 7.0 の回復イメージの作成


Microsoft 診断/回復ツールセット (DaRT) 7 には、Windows で使用される**Dart Recovery イメージウィザード**が含まれており、これを使って、起動可能な国際標準化機関 (ISO) 画像を作成します。 ISO 画像は、CD の生のコンテンツを表すファイルです。

## DaRT Recovery イメージウィザードを使用して回復イメージを作成する


DaRT リカバリ画像ウィザードによって作成された ISO には、問題のあるコンピュータを起動できる DaRT リカバリ画像が含まれています。これは、それ以外の方法でも起動できます。 DaRT にコンピューターを起動した後、さまざまな DaRT ツールを実行して、コンピュータの診断と修復を試すことができます。

書き込み可能な CD または DVD に ISO を書き込んだり、USB フラッシュドライブに保存したり、リモートパーティションまたは回復パーティションから DaRT を起動するために使用できる形式で保存したりすることができます。 詳細については、「 [DaRT 7.0 回復イメージの展開](deploying-the-dart-70-recovery-image-dart-7.md)」を参照してください。

**注** コンピューターに CD-RW ドライブが含まれている場合、ウィザードは、ISO イメージを空の CD または DVD に書き込むことを提供します。 使用しているコンピューターに、ウィザードでサポートされているドライブが含まれていない場合は、CD または DVD に書き込み可能なほとんどのプログラムを使用して、ISO イメージを CD または DVD に書き込むことができます。

 

ISO イメージからブーブート CD または DVD を作成するには、次のものが必要です。

-   CD-RW ドライブ。

-   書き込み可能な CD または DVD (書き込み可能なドライブでサポートされている形式)。

-   書き込み可能ドライブをサポートし、CD または DVD への直接 ISO イメージの書き込みをサポートするソフトウェア。

    **重要** すべての種類の書き込み可能なメディアから起動できないコンピューターがあるため、サポートする必要があるすべての種類のコンピューターで、作成した CD または DVD をテストします。

     

USB フラッシュドライブ (UFD) に ISO 画像を保存するには、次のものが必要です。

-   正しい書式の UFD。

-   ISO イメージをマウントするために使用できるプログラム。

[DaRT の回復イメージ ウィザードを使用して回復イメージを作成する方法](how-to-use-the-dart-recovery-image-wizard-to-create-the-recovery-image-dart-7.md)

## 時間限定の回復イメージを作成する


生成された特定の日数にのみ使用できる DaRT 回復イメージを作成することができます。 これを行うには、コマンドプロンプトで**DaRT リカバリイメージウィザード**を実行し、日数を指定する必要があります。

[期限付きの回復イメージを作成する方法](how-to-create-a-time-limited-recovery-image-dart-7.md)

## DaRT7 回復イメージの作成に関するその他のリソース


-   [DaRT 7.0 の展開](deploying-dart-70-new-ia.md)

 

 





