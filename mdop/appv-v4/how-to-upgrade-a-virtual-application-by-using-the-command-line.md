---
title: コマンド ラインを使用して仮想アプリケーションをアップグレードする方法
description: コマンド ラインを使用して仮想アプリケーションをアップグレードする方法
author: dansimp
ms.assetid: 83c97767-6ea1-42aa-b411-ccc9fa61cf81
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8612deb31a1692dd85cfee88ca4b18cbc5ac2ab2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816464"
---
# <span data-ttu-id="9ab43-103">コマンド ラインを使用して仮想アプリケーションをアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="9ab43-103">How to Upgrade a Virtual Application by Using the Command Line</span></span>


<span data-ttu-id="9ab43-104">コマンドラインを使用して仮想アプリケーションをアップグレードするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="9ab43-104">Use the following procedure to upgrade a virtual application by using a command line.</span></span>

**<span data-ttu-id="9ab43-105">仮想アプリケーションをアップグレードするには</span><span class="sxs-lookup"><span data-stu-id="9ab43-105">To upgrade a virtual application</span></span>**

1.  <span data-ttu-id="9ab43-106">Application Virtualization (App-v) Sequencer を実行しているコンピューターでコマンドプロンプトを開くには、[**スタート**]、[**実行**]、[ **cmd**] の各オプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="9ab43-106">On the computer that is running the Application Virtualization (App-V) Sequencer, to open the command prompt, select **Start**, **Run**, and type **cmd**.</span></span> <span data-ttu-id="9ab43-107">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ab43-107">Click **OK**.</span></span>

2.  <span data-ttu-id="9ab43-108">コマンドプロンプトで、App-v Sequencer がインストールされている場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="9ab43-108">At the command prompt, specify the location where the App-V Sequencer is installed.</span></span> <span data-ttu-id="9ab43-109">たとえば、コマンドプロンプトでは、次のように入力します。 **cd c: cd c/l Microsoft Application Virtualization Sequencer**</span><span class="sxs-lookup"><span data-stu-id="9ab43-109">For example, at the command prompt, you could type the following: **cd C:\\Program Files\\Microsoft Application Virtualization Sequencer**.</span></span>

3.  <span data-ttu-id="9ab43-110">コマンドプロンプトで、次のコマンドを入力します。引用符で囲まれたテキストを値で置き換えます。</span><span class="sxs-lookup"><span data-stu-id="9ab43-110">At the command prompt, type the following command, replacing the text in quotation marks with your values:</span></span>

    `SFTSequencer /UPGRADE:"pathtosourceSPRJ" /INSTALLPACKAGE:"pathtoUpgradeInstaller" /DECODEPATH:"pathtodecodefolder" /OUTPUTFILE:"pathtodestinationSPRJ"`

    **<span data-ttu-id="9ab43-111">注</span><span class="sxs-lookup"><span data-stu-id="9ab43-111">Note</span></span>**  
    <span data-ttu-id="9ab43-112">追加のパラメーターを指定するには、アップグレードするアプリケーションの複雑さに応じてコマンドラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="9ab43-112">You can specify additional parameters by using the command line, depending on the complexity of the application you are upgrading.</span></span> <span data-ttu-id="9ab43-113">App-v の Sequencer で使用できるパラメーターの完全な一覧については、「 [Sequencer コマンドラインパラメーター](sequencer-command-line-parameters.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9ab43-113">For a complete list of parameters that are available for use with the App-V Sequencer, see [Sequencer Command-Line Parameters](sequencer-command-line-parameters.md).</span></span>



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



4. <span data-ttu-id="9ab43-114">Enter**キーを押します**。</span><span class="sxs-lookup"><span data-stu-id="9ab43-114">Press **Enter**.</span></span>

## <span data-ttu-id="9ab43-115">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9ab43-115">Related topics</span></span>


[<span data-ttu-id="9ab43-116">App-v Sequencer を使用して仮想アプリケーションを作成またはアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="9ab43-116">How to Create or Upgrade Virtual Applications Using the App-V Sequencer</span></span>](how-to-create-or-upgrade-virtual-applications-using--the-app-v-sequencer.md)

[<span data-ttu-id="9ab43-117">Sequencer コマンド ライン エラー コード</span><span class="sxs-lookup"><span data-stu-id="9ab43-117">Sequencer Command-Line Error Codes</span></span>](sequencer-command-line-error-codes.md)

[<span data-ttu-id="9ab43-118">Sequencer コマンド ライン パラメーター</span><span class="sxs-lookup"><span data-stu-id="9ab43-118">Sequencer Command-Line Parameters</span></span>](sequencer-command-line-parameters.md)









