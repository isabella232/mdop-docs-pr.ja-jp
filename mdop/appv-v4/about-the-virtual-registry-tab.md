---
title: '[仮想レジストリ] タブについて'
description: '[仮想レジストリ] タブについて'
author: dansimp
ms.assetid: ca8d837f-8218-4f86-95fd-13a44dccd022
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 77decee4a8e07333b466db0a1bd0513efe859c9a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819894"
---
# <span data-ttu-id="ba434-103">[仮想レジストリ] タブについて</span><span class="sxs-lookup"><span data-stu-id="ba434-103">About the Virtual Registry Tab</span></span>


<span data-ttu-id="ba434-104">シーケンス中に仮想レジストリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ba434-104">A virtual registry is created during sequencing.</span></span> <span data-ttu-id="ba434-105">[**仮想レジストリ**] タブには、シーケンス形式のアプリケーションパッケージを実行するために必要なすべてのレジストリキーと値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ba434-105">The **Virtual Registry** tab displays all the registry keys and values that are required for a sequenced application package to run.</span></span> <span data-ttu-id="ba434-106">このタブを使用して、レジストリキーとレジストリ値の追加、編集、削除を行います。</span><span class="sxs-lookup"><span data-stu-id="ba434-106">Use this tab to add, edit, and delete registry keys and registry values.</span></span>

<span data-ttu-id="ba434-107">[**ローカルキーの上書き**] を選択してホストシステムのキーを無視することもできます。また、仮想環境内からキーのマージされたビューを作成するには、[**ローカルキーと結合**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ba434-107">You can also choose to ignore the hosting system’s keys by selecting **Override Local Key**, or you can create a merged view of the key from within the virtual environment by selecting **Merge with Local Key**.</span></span>

<span data-ttu-id="ba434-108">[仮想レジストリ**設定**] タブの変更は、特定のシーケンスされたアプリケーションパッケージの一部であるアプリケーションに影響しますが、アプリケーションの仮想化デスクトップクライアントにストリーミングまたはローカルにインストールされている他のアプリケーションの動作には影響しません。</span><span class="sxs-lookup"><span data-stu-id="ba434-108">The changes to the virtual registry **Settings** tab affect applications that are part of the specific sequenced application package, but they do not affect the operation of other applications that are streamed to or locally installed on the Application Virtualization Desktop Client.</span></span>

<span data-ttu-id="ba434-109">**注** 仮想レジストリキーと値を変更する場合は注意してください。</span><span class="sxs-lookup"><span data-stu-id="ba434-109">**Note** Exercise caution when changing virtual registry keys and values.</span></span> <span data-ttu-id="ba434-110">これらのキーと値を変更すると、シーケンス処理されたアプリケーションパッケージが動作しなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ba434-110">Changing these keys and values might render your sequenced application package inoperable.</span></span>

 

<span data-ttu-id="ba434-111">[**仮想レジストリ**] タブの左側のウィンドウには、アプリケーションのシーケンス中に作成された仮想レジストリの完全な一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ba434-111">The left pane of the **Virtual Registry** tab displays the full list of virtual registries created during the sequencing of an application.</span></span>

## <span data-ttu-id="ba434-112">行</span><span class="sxs-lookup"><span data-stu-id="ba434-112">Columns</span></span>


<a href="" id="name"></a>**<span data-ttu-id="ba434-113">名前</span><span class="sxs-lookup"><span data-stu-id="ba434-113">Name</span></span>**  
<span data-ttu-id="ba434-114">仮想レジストリ内のエントリの名前。</span><span class="sxs-lookup"><span data-stu-id="ba434-114">The name for the entry in the virtual registry.</span></span>

<a href="" id="type"></a>**<span data-ttu-id="ba434-115">型</span><span class="sxs-lookup"><span data-stu-id="ba434-115">Type</span></span>**  
<span data-ttu-id="ba434-116">エントリにデータが格納される方法。</span><span class="sxs-lookup"><span data-stu-id="ba434-116">How the entry stores its data.</span></span>

<a href="" id="data"></a>**<span data-ttu-id="ba434-117">データ</span><span class="sxs-lookup"><span data-stu-id="ba434-117">Data</span></span>**  
<span data-ttu-id="ba434-118">エントリによって保存された値。</span><span class="sxs-lookup"><span data-stu-id="ba434-118">The value stored by the entry.</span></span>

<a href="" id="attributes"></a>**<span data-ttu-id="ba434-119">属性</span><span class="sxs-lookup"><span data-stu-id="ba434-119">Attributes</span></span>**  
<span data-ttu-id="ba434-120">ファイルの属性を表示します。</span><span class="sxs-lookup"><span data-stu-id="ba434-120">Displays the file attributes.</span></span>

## <span data-ttu-id="ba434-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ba434-121">Related topics</span></span>


[<span data-ttu-id="ba434-122">仮想レジストリ キーの情報を変更する方法</span><span class="sxs-lookup"><span data-stu-id="ba434-122">How to Modify Virtual Registry Key Information</span></span>](how-to-modify-virtual-registry-key-information.md)

[<span data-ttu-id="ba434-123">Sequencer Console</span><span class="sxs-lookup"><span data-stu-id="ba434-123">Sequencer Console</span></span>](sequencer-console.md)

 

 





