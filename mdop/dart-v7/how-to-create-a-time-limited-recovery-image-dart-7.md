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
# <span data-ttu-id="cc69b-103">期限付きの回復イメージを作成する方法</span><span class="sxs-lookup"><span data-stu-id="cc69b-103">How to Create a Time Limited Recovery Image</span></span>


<span data-ttu-id="cc69b-104">生成された特定の日数にのみ使用できる DaRT 回復イメージを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="cc69b-104">You can create a DaRT recovery image that can only be used for a certain number of days after it is generated.</span></span> <span data-ttu-id="cc69b-105">これを行うには、コマンドプロンプトで**DaRT リカバリイメージウィザード**を実行し、日数を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc69b-105">To do this, you must run the **DaRT Recovery Image Wizard** at a command prompt and specify the number of days.</span></span>

**<span data-ttu-id="cc69b-106">時間制限のある回復イメージを作成するには</span><span class="sxs-lookup"><span data-stu-id="cc69b-106">To create a recovery image that has a time limit</span></span>**

1.  <span data-ttu-id="cc69b-107">管理者の資格情報を使ってコマンドプロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="cc69b-107">Open a Command Prompt with administrator credentials.</span></span>

2.  <span data-ttu-id="cc69b-108">ディレクトリを ERDC.exe プログラムの場所に変更します。</span><span class="sxs-lookup"><span data-stu-id="cc69b-108">Change the directory to the location of the ERDC.exe program.</span></span>

3.  <span data-ttu-id="cc69b-109">次の構文を使用して、 **DaRT Recovery イメージウィザード**を実行します。</span><span class="sxs-lookup"><span data-stu-id="cc69b-109">Using the following syntax, run the **DaRT Recovery Image Wizard**.</span></span> <span data-ttu-id="cc69b-110">*Numberofdays*は、DaRT リカバリ画像が使用可能になる日数を表す正の整数です。</span><span class="sxs-lookup"><span data-stu-id="cc69b-110">*NumberOfDays* is a positive integer that represents the number of days that the DaRT recovery image will be usable.</span></span>

    ``` syntax
    ERDC /e NumberOfDays
    ```

## <span data-ttu-id="cc69b-111">関連トピック</span><span class="sxs-lookup"><span data-stu-id="cc69b-111">Related topics</span></span>


[<span data-ttu-id="cc69b-112">DaRT 7.0 の回復イメージの作成</span><span class="sxs-lookup"><span data-stu-id="cc69b-112">Creating the DaRT 7.0 Recovery Image</span></span>](creating-the-dart-70-recovery-image-dart-7.md)

 

 





