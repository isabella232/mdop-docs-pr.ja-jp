---
title: 高度なファイル転送のオプションを設定する方法
description: 高度なファイル転送のオプションを設定する方法
author: dansimp
ms.assetid: 5e9f8749-a5a9-48c6-9bfc-6b8e0cbe6cab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7319374c9a79d42c5d2e668eb8431a2c083fb40d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824654"
---
# <span data-ttu-id="3f910-103">高度なファイル転送のオプションを設定する方法</span><span class="sxs-lookup"><span data-stu-id="3f910-103">How to Set Advanced File Transfer Options</span></span>


**<span data-ttu-id="3f910-104">ファイル転送の詳細オプションを設定するには</span><span class="sxs-lookup"><span data-stu-id="3f910-104">To set advanced file transfer options</span></span>**

1.  <span data-ttu-id="3f910-105">**展開**ウィンドウで [**詳細設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f910-105">In the **Deployment** pane, click **Advanced**.</span></span>

2.  <span data-ttu-id="3f910-106">[**ファイル転送オプション**] ダイアログボックスで、次の表の説明に従ってパラメーターを構成します。</span><span class="sxs-lookup"><span data-stu-id="3f910-106">In the **File Transfer Options** dialog box, configure the parameters as described in the following table.</span></span>

3.  <span data-ttu-id="3f910-107">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f910-107">Click **OK**.</span></span>

**<span data-ttu-id="3f910-108">ファイル転送オプションのプロパティ</span><span class="sxs-lookup"><span data-stu-id="3f910-108">File Transfer Options Properties</span></span>**

<span data-ttu-id="3f910-109">*ホストに対する*プロパティの説明ワークスペース</span><span class="sxs-lookup"><span data-stu-id="3f910-109">Property Description *Workspace to Host*</span></span>

<span data-ttu-id="3f910-110">受信したファイルに対してコマンドを実行する</span><span class="sxs-lookup"><span data-stu-id="3f910-110">Run command on received files</span></span>

<span data-ttu-id="3f910-111">このチェックボックスをオンにすると、ホストに転送されたすべてのファイルでコマンドラインが実行されます。</span><span class="sxs-lookup"><span data-stu-id="3f910-111">Select this check box to run a command line on all files transferred to the host.</span></span> <span data-ttu-id="3f910-112">[コマンドライン] ボックスに、受信したすべてのファイルに対して実行するコマンドラインを入力します。</span><span class="sxs-lookup"><span data-stu-id="3f910-112">In the command-line box, enter the command line to run on all received files.</span></span>

<span data-ttu-id="3f910-113">ファイルの種類</span><span class="sxs-lookup"><span data-stu-id="3f910-113">File types</span></span>

-   <span data-ttu-id="3f910-114">[**すべてのファイル拡張子を許可する**] —をクリックして、ファイル名拡張子のファイルを med-v ワークスペースからホストに転送できるようにします。</span><span class="sxs-lookup"><span data-stu-id="3f910-114">**Allow all file extensions**—Click to enable transferring files of any file name extension from the MED-V workspace to the host.</span></span>

-   <span data-ttu-id="3f910-115">[**次のファイル拡張子を許可**する] —指定したファイル名拡張子のファイルのみを転送できるようにするには、をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f910-115">**Allow the following file extensions**—Click to enable only files with specified file name extensions to be transferred.</span></span> <span data-ttu-id="3f910-116">空のフィールドに、許可されているすべてのファイル名拡張子をコンマで区切って入力します。</span><span class="sxs-lookup"><span data-stu-id="3f910-116">In the empty field, enter all file name extensions allowed, separated by commas.</span></span>

*<span data-ttu-id="3f910-117">ワークスペースへのホスト</span><span class="sxs-lookup"><span data-stu-id="3f910-117">Host to Workspace</span></span>*

<span data-ttu-id="3f910-118">受信したファイルに対してコマンドを実行する</span><span class="sxs-lookup"><span data-stu-id="3f910-118">Run command on received files</span></span>

<span data-ttu-id="3f910-119">このチェックボックスをオンにすると、MED-V ワークスペースに転送されたすべてのファイルに対してコマンドラインが実行されます。</span><span class="sxs-lookup"><span data-stu-id="3f910-119">Select this check box to run a command line on all files transferred to the MED-V workspace.</span></span> <span data-ttu-id="3f910-120">[コマンドライン] ボックスに、転送されたすべてのファイルに対して実行するコマンドラインを入力します。</span><span class="sxs-lookup"><span data-stu-id="3f910-120">In the command-line box, enter the command line to run on all transferred files.</span></span>

<span data-ttu-id="3f910-121">ファイルの種類</span><span class="sxs-lookup"><span data-stu-id="3f910-121">File types</span></span>

-   <span data-ttu-id="3f910-122">[**すべてのファイル拡張子を許可する**] —すべてのファイル名拡張子のファイルを転送できるようにします。</span><span class="sxs-lookup"><span data-stu-id="3f910-122">**Allow all file extensions**—Click to enable transferring files of any file name extension.</span></span>

-   <span data-ttu-id="3f910-123">[**次のファイル拡張子を許可**する] —指定したファイル名拡張子を持つファイルのみがホストから med-v ワークスペースに転送されるようにするには、をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f910-123">**Allow the following file extensions**—Click to enable only files with specified file name extensions to be transferred from the host to the MED-V workspace.</span></span> <span data-ttu-id="3f910-124">空のフィールドに、許可されているすべてのファイル名拡張子をコロンで区切って入力します。</span><span class="sxs-lookup"><span data-stu-id="3f910-124">In the empty field, enter all file name extensions allowed, separated by colons.</span></span>

 

## <span data-ttu-id="3f910-125">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3f910-125">Related topics</span></span>


[<span data-ttu-id="3f910-126">ドメイン ユーザーまたはグループを構成する方法</span><span class="sxs-lookup"><span data-stu-id="3f910-126">How to Configure a Domain User or Group</span></span>](how-to-configure-a-domain-user-or-groupmedvv2.md)

 

 





