---
title: コマンド ラインを使用して MBAM クライアントを展開する方法
description: コマンド ラインを使用して MBAM クライアントを展開する方法
author: dansimp
ms.assetid: ac1d4ffe-c26d-41c9-9737-a4f2b37fde24
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 416d76ad876c5114e3a8764111b6a15c879b13b5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824487"
---
# <span data-ttu-id="34915-103">コマンド ラインを使用して MBAM クライアントを展開する方法</span><span class="sxs-lookup"><span data-stu-id="34915-103">How to Deploy the MBAM Client by Using a Command Line</span></span>


<span data-ttu-id="34915-104">コマンドラインを使用して、Microsoft BitLocker 管理および監視 (MBAM) クライアントソフトウェアを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="34915-104">You can use a command line to deploy the Microsoft BitLocker Administration and Monitoring (MBAM) Client software.</span></span>

## <span data-ttu-id="34915-105">MBAM クライアントソフトウェアを展開するためのコマンドライン</span><span class="sxs-lookup"><span data-stu-id="34915-105">Command Line to deploy the MBAM Client software</span></span>


<span data-ttu-id="34915-106">MBAM クライアントソフトウェアを展開するときに、コマンドプロンプトで次のコマンドを入力して、エンドユーザーライセンス契約に自動的に同意します。</span><span class="sxs-lookup"><span data-stu-id="34915-106">Type the following command at the command prompt to automatically accept the end user license agreement when deploying the MBAM Client software.</span></span>

**<span data-ttu-id="34915-107">MBAMClientSetup.exe/acceptEula = Yes</span><span class="sxs-lookup"><span data-stu-id="34915-107">MBAMClientSetup.exe /acceptEula=Yes</span></span>**

<span data-ttu-id="34915-108">**注** **/Ju**と **/jm**のコマンドラインオプションはサポートされていないため、mbam クライアントソフトウェアのインストールに使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="34915-108">**Note** The **/ju** and **/jm** command-line options are not supported and cannot be used to install the MBAM Client software.</span></span>

 

<span data-ttu-id="34915-109">コマンドプロンプトで次のコマンドを入力して、MSP を抽出してインストールします。</span><span class="sxs-lookup"><span data-stu-id="34915-109">Type the following command at the command prompt to extract and install the MSP:</span></span>

**<span data-ttu-id="34915-110">MBAMClientSetup.exe &lt; の MSI を抽出するための/extract path &gt; = Yes</span><span class="sxs-lookup"><span data-stu-id="34915-110">MBAMClientSetup.exe /extract &lt;path to extract MSI&gt; /acceptEula=Yes</span></span>**

<span data-ttu-id="34915-111">次のコマンドを実行して、サイレントモードで MSI をインストールします。</span><span class="sxs-lookup"><span data-stu-id="34915-111">Then, install the MSI silently by running the following command:</span></span>

**<span data-ttu-id="34915-112">&lt;は、展開された MSI/QB ALLUSERS への msiexec/i パス &gt; = 1 REBOOT = ReallySuppress</span><span class="sxs-lookup"><span data-stu-id="34915-112">msiexec /i &lt;path to extracted MSI&gt; /qb ALLUSERS=1 REBOOT=ReallySuppress</span></span>**

<span data-ttu-id="34915-113">**注** MBAM 2.5 SP1 以降、MBAM 製品には別の MSI が含まれなくなりました。</span><span class="sxs-lookup"><span data-stu-id="34915-113">**Note** Beginning in MBAM 2.5 SP1, a separate MSI is no longer included with the MBAM product.</span></span> <span data-ttu-id="34915-114">ただし、EULA に同意した後は、製品に含まれている実行可能ファイル (.exe) から MSI を抽出することができます。</span><span class="sxs-lookup"><span data-stu-id="34915-114">However, you can extract the MSI from the executable file (.exe) that is included with the product, after accepting the EULA.</span></span>

 

## <a href="" id="optin-for-microsoft-updates-1-command-line-option"></a><span data-ttu-id="34915-115">OPTIN \ _FOR \ _MICROSOFT \ _UPDATES = 1 コマンドラインオプション</span><span class="sxs-lookup"><span data-stu-id="34915-115">OPTIN\_FOR\_MICROSOFT\_UPDATES=1 command-line option</span></span>


<span data-ttu-id="34915-116">必要に応じて、クライアントソフトウェアのインストール中にコマンドラインオプションを指定して、 `OPTIN_FOR_MICROSOFT_UPDATES=1` クライアントコンピューターに Microsoft 更新プログラムを自動的にインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="34915-116">You can optionally specify the command-line option `OPTIN_FOR_MICROSOFT_UPDATES=1` during the Client software installation to automatically install Microsoft Updates on client computers.</span></span> <span data-ttu-id="34915-117">このオプションを指定すると、Microsoft Update が自動的に起動し、クライアントソフトウェアのインストールが完了した後にインストールできる更新プログラムが検索されます。</span><span class="sxs-lookup"><span data-stu-id="34915-117">Specifying this option makes Microsoft Update automatically start and search for available updates to install after the Client software installation finishes.</span></span>

<span data-ttu-id="34915-118">このコマンドラインオプションは、次のいずれかのインストール方法で使うことができます。</span><span class="sxs-lookup"><span data-stu-id="34915-118">You can use this command-line option with either of the following installation methods.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="34915-119">を使用して MBAM クライアントソフトウェアをインストールする</span><span class="sxs-lookup"><span data-stu-id="34915-119">Install the MBAM Client software by using</span></span></th>
<th align="left"><span data-ttu-id="34915-120">例</span><span class="sxs-lookup"><span data-stu-id="34915-120">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="34915-121">MBAMClientSetup.exe</span><span class="sxs-lookup"><span data-stu-id="34915-121">MBAMClientSetup.exe</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="34915-122">MbamClientSetup.exe OPTIN_FOR_MICROSOFT_UPDATES = 1</span><span class="sxs-lookup"><span data-stu-id="34915-122">MbamClientSetup.exe OPTIN_FOR_MICROSOFT_UPDATES=1</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="34915-123">msiexec/i MBAMClient.msi</span><span class="sxs-lookup"><span data-stu-id="34915-123">msiexec /i MBAMClient.msi</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="34915-124">msiexec/i MBAMClient.msi OPTIN_FOR_MICROSOFT_UPDATES = 1</span><span class="sxs-lookup"><span data-stu-id="34915-124">msiexec /i MBAMClient.msi OPTIN_FOR_MICROSOFT_UPDATES=1</span></span></strong></p></td>
</tr>
</tbody>
</table>

 


## <span data-ttu-id="34915-125">関連トピック</span><span class="sxs-lookup"><span data-stu-id="34915-125">Related topics</span></span>


[<span data-ttu-id="34915-126">MBAM 2.5 クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="34915-126">Deploying the MBAM 2.5 Client</span></span>](deploying-the-mbam-25-client.md)

 

 
## <span data-ttu-id="34915-127">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="34915-127">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="34915-128">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="34915-128">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="34915-129">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="34915-129">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




