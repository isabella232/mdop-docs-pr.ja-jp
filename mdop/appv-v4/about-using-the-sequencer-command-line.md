---
title: Sequencer コマンド ラインの使用について
description: Sequencer コマンド ラインの使用について
author: dansimp
ms.assetid: 0fd5f81b-17f9-4065-bce2-8785e8aac7c7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: afb3fb8608c78a3b9237a80529a6c22d792661ba
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819904"
---
# <span data-ttu-id="bb2f0-103">Sequencer コマンド ラインの使用について</span><span class="sxs-lookup"><span data-stu-id="bb2f0-103">About Using the Sequencer Command Line</span></span>


<span data-ttu-id="bb2f0-104">コマンドラインを使って、シーケンスが適用されたアプリケーションパッケージを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="bb2f0-104">You can use the command line to create sequenced application packages.</span></span> <span data-ttu-id="bb2f0-105">コマンドラインを使用して仮想アプリケーションを作成することは、次のシナリオで役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bb2f0-105">Using the command line to create virtual applications is useful in the following scenarios:</span></span>

-   <span data-ttu-id="bb2f0-106">多数の順序が付けられたアプリケーションパッケージを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb2f0-106">You need to create a large number of sequenced application packages.</span></span>

-   <span data-ttu-id="bb2f0-107">順序付けされたアプリケーションパッケージを定期的に作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb2f0-107">You need to create a sequenced application package on a recurring basis.</span></span>

<span data-ttu-id="bb2f0-108">**重要** コマンドプロンプトでシーケンス処理を行うと、既定のシーケンスのみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="bb2f0-108">**Important** Sequencing at the command prompt allows for default sequencing only.</span></span> <span data-ttu-id="bb2f0-109">既定のシーケンスパラメーターを変更する必要がある場合は、シーケンス処理されたアプリケーションパッケージを手動で変更するか、アプリケーションを再順序付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb2f0-109">If you need to change default sequencing parameters, you must either manually modify a sequenced application package or re-sequence the application.</span></span>

 

<span data-ttu-id="bb2f0-110">シーケンスウィザードを使用して、既存のシーケンスされたアプリケーションパッケージに対する以降のすべての変更を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb2f0-110">All subsequent modifications to existing sequenced application packages must be made using the sequencing wizard.</span></span>

## <span data-ttu-id="bb2f0-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="bb2f0-111">Prerequisites</span></span>


<span data-ttu-id="bb2f0-112">コマンドプロンプトを使用してアプリケーションを順序指定するには、次の条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb2f0-112">To sequence an application by using the command prompt, the following conditions must be met:</span></span>

-   <span data-ttu-id="bb2f0-113">シーケンスを実行しようとしているアプリケーションは、インストーラまたは Windows インストーラパッケージの外部で、変更または回避策を要求する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="bb2f0-113">The application that is about to be sequenced must not require changes or workarounds made to it outside the installer or Windows Installer package.</span></span>

-   <span data-ttu-id="bb2f0-114">シーケンス処理の前に、シーケンス処理されたアプリケーションパッケージを作成するためのバッチファイルの一覧を準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb2f0-114">Before sequencing, you must prepare a list of batch files for creating the sequenced application packages.</span></span>

-   <span data-ttu-id="bb2f0-115">レビューコマンドラインパラメーターの詳細については、「[コマンドラインパラメーター](command-line-parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb2f0-115">Review For more information about the command line parameters, see [Command-Line Parameters](command-line-parameters.md).</span></span>

-   <span data-ttu-id="bb2f0-116">コマンドラインを使用して、シーケンス付きのアプリケーションパッケージを作成するときに表示される可能性のあるエラーを確認します。</span><span class="sxs-lookup"><span data-stu-id="bb2f0-116">Review the errors that might be displayed when creating a sequenced application package by using the command line.</span></span> <span data-ttu-id="bb2f0-117">詳細については、「これらのエラー」を参照してください。[コマンドラインエラー](command-line-errors.md)について説明します。</span><span class="sxs-lookup"><span data-stu-id="bb2f0-117">For more information, see these errors, see [Command-Line Errors](command-line-errors.md).</span></span>

## <span data-ttu-id="bb2f0-118">関連トピック</span><span class="sxs-lookup"><span data-stu-id="bb2f0-118">Related topics</span></span>


[<span data-ttu-id="bb2f0-119">コマンド ラインを使用して仮想アプリケーションを管理する方法</span><span class="sxs-lookup"><span data-stu-id="bb2f0-119">How to Manage Virtual Applications Using the Command Line</span></span>](how-to-manage-virtual-applications-using-the-command-line.md)

 

 





