---
title: コマンド ラインを使用してシーケンス処理されたアプリケーション パッケージをアップグレードする方法
description: コマンド ラインを使用してシーケンス処理されたアプリケーション パッケージをアップグレードする方法
author: dansimp
ms.assetid: 682fac46-c71d-4731-831b-81bfd5032764
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: eade2ced43852419176f635918f0a6b7c3444aee
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816487"
---
# <span data-ttu-id="3fb6f-103">コマンド ラインを使用してシーケンス処理されたアプリケーション パッケージをアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="3fb6f-103">How to Upgrade a Sequenced Application Package Using the Command Line</span></span>


<span data-ttu-id="3fb6f-104">コマンドラインを使用して仮想アプリケーションをアップグレードするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="3fb6f-104">Use the following procedure to upgrade a virtual application by using a command line.</span></span> <span data-ttu-id="3fb6f-105">コマンドラインを使用して既存の仮想アプリケーションパッケージをアップグレードすると、元のバージョンの sft ファイルが削除されます。</span><span class="sxs-lookup"><span data-stu-id="3fb6f-105">When you upgrade an existing virtual application package by using the command line, the original version of the .sft file is deleted.</span></span> <span data-ttu-id="3fb6f-106">コマンドラインを使用してパッケージをアップグレードする前に、関連付けられた sft ファイルをバックアップしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="3fb6f-106">You should back up the associated .sft file before upgrading the package by using the command line.</span></span>

**<span data-ttu-id="3fb6f-107">仮想アプリケーションをアップグレードするには</span><span class="sxs-lookup"><span data-stu-id="3fb6f-107">To upgrade a virtual application</span></span>**

1.  <span data-ttu-id="3fb6f-108">Application Virtualization (App-v) Sequencer を実行しているコンピューターでコマンドプロンプトを開くには、[**スタート**]、[**実行**]、[ **cmd**] の各オプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="3fb6f-108">On the computer that is running the Application Virtualization (App-V) Sequencer, to open the command prompt, select **Start**, **Run**, and type **cmd**.</span></span> <span data-ttu-id="3fb6f-109">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3fb6f-109">Click **OK**.</span></span>

2.  <span data-ttu-id="3fb6f-110">コマンドプロンプトで、App-v Sequencer がインストールされている場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="3fb6f-110">At the command prompt, specify the location where the App-V Sequencer is installed.</span></span> <span data-ttu-id="3fb6f-111">たとえば、コマンドプロンプトでは、次のように入力します。 **cd c: cd c/l Microsoft Application Virtualization Sequencer**</span><span class="sxs-lookup"><span data-stu-id="3fb6f-111">For example, at the command prompt, you could type the following: **cd C:\\Program Files\\Microsoft Application Virtualization Sequencer**.</span></span>

3.  <span data-ttu-id="3fb6f-112">コマンドプロンプトで、次のコマンドを入力します。引用符で囲まれたテキストを値で置き換えます。</span><span class="sxs-lookup"><span data-stu-id="3fb6f-112">At the command prompt, type the following command, replacing the text in quotation marks with your values:</span></span>

    `SFTSequencer /UPGRADE:"pathtosourceSPRJ" /INSTALLPACKAGE:"pathtoUpgradeInstaller" /DECODEPATH:"pathtodecodefolder" /OUTPUTFILE:"pathtodestinationSPRJ"`

    **<span data-ttu-id="3fb6f-113">注</span><span class="sxs-lookup"><span data-stu-id="3fb6f-113">Note</span></span>**  
    <span data-ttu-id="3fb6f-114">追加のパラメーターを指定するには、アップグレードするアプリケーションの複雑さに応じてコマンドラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="3fb6f-114">You can specify additional parameters by using the command line, depending on the complexity of the application you are upgrading.</span></span> <span data-ttu-id="3fb6f-115">App-v の Sequencer で使用できるパラメーターの完全な一覧については、「[コマンドラインパラメーター](command-line-parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3fb6f-115">For a complete list of parameters that are available for use with the App-V Sequencer, see [Command-Line Parameters](command-line-parameters.md).</span></span>



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
<td align="left"><p><em>pathtosourceSPRJ</em></p></td>
<td align="left"><p>Specifies the directory location of the virtual application to be upgraded.</p></td>
</tr>
<tr class="even">
<td align="left"><p><em>pathtoUpgradeInstaller</em></p></td>
<td align="left"><p>Specifies the Windows Installer or a batch file that will be used to install an upgrade to the application.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>pathtodecodefolder</em></p></td>
<td align="left"><p>Specify the directory in which to unpack the SFT file.</p></td>
</tr>
<tr class="even">
<td align="left"><p><em>pathtodestinationSPRJ</em></p></td>
<td align="left"><p>Specifies the path and file name of the SPRJ file that will be created.</p></td>
</tr>
</tbody>
</table>
~~~



4. <span data-ttu-id="3fb6f-116">Enter**キーを押します**。</span><span class="sxs-lookup"><span data-stu-id="3fb6f-116">Press **Enter**.</span></span>

## <span data-ttu-id="3fb6f-117">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3fb6f-117">Related topics</span></span>


[<span data-ttu-id="3fb6f-118">コマンド ラインを使用して仮想アプリケーションを管理する方法</span><span class="sxs-lookup"><span data-stu-id="3fb6f-118">How to Manage Virtual Applications Using the Command Line</span></span>](how-to-manage-virtual-applications-using-the-command-line.md)









