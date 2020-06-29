---
title: コマンド ラインを使用して新しいアプリケーションをシーケンス処理する方法
description: コマンド ラインを使用して新しいアプリケーションをシーケンス処理する方法
author: dansimp
ms.assetid: c3b5c842-6a91-4d0a-9a22-c7b8d1aeb09a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ea7b1222dc00a0a4649cb342ac1ba41338484889
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816687"
---
# <span data-ttu-id="ec4c2-103">コマンド ラインを使用して新しいアプリケーションをシーケンス処理する方法</span><span class="sxs-lookup"><span data-stu-id="ec4c2-103">How to Sequence a New Application by Using the Command Line</span></span>


<span data-ttu-id="ec4c2-104">コマンドラインを使用して、新しいアプリケーションの順序を調整することができます。</span><span class="sxs-lookup"><span data-stu-id="ec4c2-104">You can use a command line to sequence a new application.</span></span> <span data-ttu-id="ec4c2-105">コマンドラインを使用すると、多数の仮想アプリケーションを作成する必要がある場合や、連続したアプリケーションを定期的に作成する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="ec4c2-105">Using a command line is useful when you have to create a large number of virtual applications or when you need to create sequenced applications on a recurring basis.</span></span>

**<span data-ttu-id="ec4c2-106">重要</span><span class="sxs-lookup"><span data-stu-id="ec4c2-106">Important</span></span>**  
<span data-ttu-id="ec4c2-107">コマンドラインの順序指定では、既定のシーケンスのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ec4c2-107">Command-line sequencing allows for default sequencing only.</span></span> <span data-ttu-id="ec4c2-108">順序を指定するアプリケーションの既定のインストール設定を変更する必要がある場合は、Application Virtualization (App-v) Sequencer を使用して、仮想アプリケーションを手動で変更するか、仮想アプリケーションを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec4c2-108">If you need to change default installation settings for the application you are sequencing, you must either manually modify the virtual application or update the virtual application by using the Application Virtualization (App-V) Sequencer.</span></span> <span data-ttu-id="ec4c2-109">App-v Sequencer を使用した仮想アプリケーションの更新の詳細については、「[既存の仮想アプリケーションをアップグレードする方法](how-to-upgrade-an-existing-virtual-application.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec4c2-109">For more information about updating a virtual application by using the App-V Sequencer, see [How to Upgrade an Existing Virtual Application](how-to-upgrade-an-existing-virtual-application.md).</span></span>



<span data-ttu-id="ec4c2-110">コマンドラインを使用して仮想アプリケーションを作成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="ec4c2-110">Use the following procedure to create a virtual application by using the command line.</span></span>

**<span data-ttu-id="ec4c2-111">コマンドラインを使用してアプリケーションをシーケンスするには</span><span class="sxs-lookup"><span data-stu-id="ec4c2-111">To sequence an application by using the command line</span></span>**

1.  <span data-ttu-id="ec4c2-112">App-v Sequencer を実行しているコンピューターで、[**スタート**]、[**実行**] の順に選択してコマンドプロンプトを開き、「 **cmd**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="ec4c2-112">On the computer that is running the App-V Sequencer, open the command prompt by selecting **Start**, **Run**, and then type **cmd**.</span></span> <span data-ttu-id="ec4c2-113">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec4c2-113">Click **OK**.</span></span>

2.  <span data-ttu-id="ec4c2-114">コマンドプロンプトを使用して、App-v Sequencer がインストールされている場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="ec4c2-114">Use the command prompt to specify the location of where the App-V Sequencer is installed.</span></span> <span data-ttu-id="ec4c2-115">たとえば、コマンドプロンプトでは、次のように入力します。 **cd c: cd c/l Microsoft Application Virtualization Sequencer**</span><span class="sxs-lookup"><span data-stu-id="ec4c2-115">For example, at the command prompt, you could type the following: **cd C:\\Program Files\\Microsoft Application Virtualization Sequencer**.</span></span>

3.  <span data-ttu-id="ec4c2-116">コマンドプロンプトで、次のコマンドを入力します。引用符で囲まれたテキストを値で置き換えます。</span><span class="sxs-lookup"><span data-stu-id="ec4c2-116">At the command prompt, type the following command, replacing the text in quotation marks with your values:</span></span>

    `SFTSequencer /INSTALLPACKAGE:"pathtoMSI" /INSTALLPATH:"pathtopackageroot" /OUTPUTFILE:"pathtodestinationSPRJ"`

    **<span data-ttu-id="ec4c2-117">注</span><span class="sxs-lookup"><span data-stu-id="ec4c2-117">Note</span></span>**  
    <span data-ttu-id="ec4c2-118">順序を設定するアプリケーションの複雑さに応じてコマンドラインを使用して、追加のパラメーターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ec4c2-118">You can specify additional parameters by using the command line, depending on the complexity of the application you are sequencing.</span></span> <span data-ttu-id="ec4c2-119">App-v の Sequencer で使用できるパラメーターの完全な一覧については、「 [Sequencer コマンドラインパラメーター](sequencer-command-line-parameters.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ec4c2-119">For a complete list of parameters that are available for use with the App-V Sequencer, see [Sequencer Command-Line Parameters](sequencer-command-line-parameters.md).</span></span>



~~~
Use the value descriptions in the following table to help you determine the actual text you will use in the preceding command.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Value</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><em>pathtoMSI</em></p></td>
<td align="left"><p>Specifies the Windows Installer or a batch file that will be used to install an application so that it can be sequenced.</p></td>
</tr>
<tr class="even">
<td align="left"><p><em>pathtopackageroot</em></p></td>
<td align="left"><p>Specify the package root directory.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>pathtodestinationSPRJ</em></p></td>
<td align="left"><p>Specifies the path and file name of the SPRJ file that will be created.</p></td>
</tr>
</tbody>
</table>
~~~



4. <span data-ttu-id="ec4c2-120">Enter**キーを押します**。</span><span class="sxs-lookup"><span data-stu-id="ec4c2-120">Press **Enter**.</span></span>

## <span data-ttu-id="ec4c2-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ec4c2-121">Related topics</span></span>


[<span data-ttu-id="ec4c2-122">App-v Sequencer を使用して仮想アプリケーションを作成またはアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="ec4c2-122">How to Create or Upgrade Virtual Applications Using the App-V Sequencer</span></span>](how-to-create-or-upgrade-virtual-applications-using--the-app-v-sequencer.md)

[<span data-ttu-id="ec4c2-123">Sequencer コマンド ライン エラー コード</span><span class="sxs-lookup"><span data-stu-id="ec4c2-123">Sequencer Command-Line Error Codes</span></span>](sequencer-command-line-error-codes.md)

[<span data-ttu-id="ec4c2-124">Sequencer コマンド ライン パラメーター</span><span class="sxs-lookup"><span data-stu-id="ec4c2-124">Sequencer Command-Line Parameters</span></span>](sequencer-command-line-parameters.md)









