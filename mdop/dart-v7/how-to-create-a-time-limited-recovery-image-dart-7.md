---
title: 期限付きの回復イメージを作成する方法
description: 期限付きの回復イメージを作成する方法
author: dansimp
ms.assetid: d2e29cac-c24c-4239-997f-0320b8a830ae
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a11891753f80d41f0089311771b906865950337c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812634"
---
# 期限付きの回復イメージを作成する方法


生成された特定の日数にのみ使用できる DaRT 回復イメージを作成することができます。 これを行うには、コマンドプロンプトで**DaRT リカバリイメージウィザード**を実行し、日数を指定する必要があります。

**時間制限のある回復イメージを作成するには**

1.  管理者の資格情報を使ってコマンドプロンプトを開きます。

2.  ディレクトリを ERDC.exe プログラムの場所に変更します。

3.  次の構文を使用して、 **DaRT Recovery イメージウィザード**を実行します。 *Numberofdays*は、DaRT リカバリ画像が使用可能になる日数を表す正の整数です。

    ``` syntax
    ERDC /e NumberOfDays
    ```

## 関連トピック


[DaRT 7.0 の回復イメージの作成](creating-the-dart-70-recovery-image-dart-7.md)

 

 





