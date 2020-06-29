---
title: Microsoft Application Virtualization 4.6 SP2 について
description: Microsoft Application Virtualization 4.6 SP2 について
author: dansimp
ms.assetid: 1429e314-9c38-472b-8687-3bed6cf0015c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 16303380782a086cfd750c7a8b2f99bf4f4c8b5d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820017"
---
# <span data-ttu-id="99701-103">Microsoft Application Virtualization 4.6 SP2 について</span><span class="sxs-lookup"><span data-stu-id="99701-103">About Microsoft Application Virtualization 4.6 SP2</span></span>


<span data-ttu-id="99701-104">Microsoft Application Virtualization (App-v) 4.6 SP2 には、このトピックで説明するいくつかの拡張機能と新機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="99701-104">Microsoft Application Virtualization (App-V)4.6 SP2 provides several enhancements and new features, which are described in this topic.</span></span>

<span data-ttu-id="99701-105">**注意** このトピックでは、レジストリエディターを使用して Windows レジストリを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="99701-105">**Caution** This topic describes how to change the Windows registry by using Registry Editor.</span></span> <span data-ttu-id="99701-106">Windows レジストリを誤って変更した場合、Windows の再インストールが必要になる可能性のある重大な問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="99701-106">If you change the Windows registry incorrectly, you can cause serious problems that might require you to reinstall Windows.</span></span> <span data-ttu-id="99701-107">レジストリを変更する前に、レジストリファイル (system.dat とユーザー) のバックアップコピーを作成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="99701-107">You should make a backup copy of the registry files (System.dat and User.dat) before you change the registry.</span></span> <span data-ttu-id="99701-108">Microsoft は、レジストリを変更したときに発生する可能性のある問題を解決できないことを保証できません。</span><span class="sxs-lookup"><span data-stu-id="99701-108">Microsoft cannot guarantee that the problems that might occur when you change the registry can be resolved.</span></span> <span data-ttu-id="99701-109">レジストリは、自分の責任において変更してください。</span><span class="sxs-lookup"><span data-stu-id="99701-109">Change the registry at your own risk.</span></span>

 

**<span data-ttu-id="99701-110">Windows 8 および Windows Server 2012 のサポート</span><span class="sxs-lookup"><span data-stu-id="99701-110">Support for Windows 8 and Windows Server 2012</span></span>**

<span data-ttu-id="99701-111">App-v 4.6 SP2 では、Windows 8 と Windows Server 2012 のリモートデスクトップサービスのサポートが追加されています。</span><span class="sxs-lookup"><span data-stu-id="99701-111">App-V4.6SP2 adds support for Windows 8 and Windows Server 2012 Remote Desktop Services.</span></span>

**<span data-ttu-id="99701-112">App-v 5.0 クライアントとの共存のサポート</span><span class="sxs-lookup"><span data-stu-id="99701-112">Support for coexistence with App-V 5.0 client</span></span>**

<span data-ttu-id="99701-113">App-v 4.6 SP2 は、Microsoft Application Virtualization 5.0 クライアントとの共存をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="99701-113">App-V4.6SP2 provides support for coexistence with the Microsoft Application Virtualization 5.0 client.</span></span> <span data-ttu-id="99701-114">App-v 4.6 SP2 クライアントとの共存のために App-v 5.0 クライアントを構成する方法については、「App-v 5.0 ドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99701-114">Review the App-V 5.0 documentation for instructions on how to configure the App-V 5.0 client for coexistence with the App-V4.6SP2 client.</span></span> <span data-ttu-id="99701-115">App-v 5.0 の詳細については、TechNet の「 [Application Virtualization 5](https://go.microsoft.com/fwlink/?LinkId=267599) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99701-115">For more information about App-V 5.0, see [Application Virtualization 5](https://go.microsoft.com/fwlink/?LinkId=267599) on TechNet.</span></span>

**<span data-ttu-id="99701-116">保護モードで Adobe Reader X を仮想化する機能</span><span class="sxs-lookup"><span data-stu-id="99701-116">Ability to virtualize Adobe Reader X with Protected Mode</span></span>**

<span data-ttu-id="99701-117">次の手順に従って、その保護モード機能を有効にして Adobe Reader X を仮想化することができます。</span><span class="sxs-lookup"><span data-stu-id="99701-117">You can virtualize Adobe Reader X with its Protected Mode feature turned on by using the following procedures.</span></span> <span data-ttu-id="99701-118">以前は、Adobe Reader X を仮想化するために、保護モードを無効にする必要がありました。</span><span class="sxs-lookup"><span data-stu-id="99701-118">Previously you had to disable Protected Mode in order to virtualize Adobe Reader X.</span></span>

<span data-ttu-id="99701-119">App-v の Sequencer を起動する前に、[HKEY] の下に次のレジストリ値を作成します \ _LOCAL \ _MACHINE \\ フトウェア \\ 4 \ ソフトの上書き:</span><span class="sxs-lookup"><span data-stu-id="99701-119">Before launching the App-V Sequencer, create the following registry value under HKEY\_LOCAL\_MACHINE\\SOFTWARE \\Microsoft\\SoftGrid\\4.5\\SystemGuard\\Overrides:</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="99701-120">名前</span><span class="sxs-lookup"><span data-stu-id="99701-120">Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="99701-121">種類</span><span class="sxs-lookup"><span data-stu-id="99701-121">Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="99701-122">データ</span><span class="sxs-lookup"><span data-stu-id="99701-122">Data</span></span></p></td>
<td align="left"><p><span data-ttu-id="99701-123">説明</span><span class="sxs-lookup"><span data-stu-id="99701-123">Description</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="99701-124">EnableVFSPassthrough</span><span class="sxs-lookup"><span data-stu-id="99701-124">EnableVFSPassthrough</span></span></p></td>
<td align="left"><p><span data-ttu-id="99701-125">DWORD</span><span class="sxs-lookup"><span data-stu-id="99701-125">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="99701-126">件</span><span class="sxs-lookup"><span data-stu-id="99701-126">1</span></span></p></td>
<td align="left"><p><span data-ttu-id="99701-127"><strong> </strong> 起動フェーズ中に Adobe Reader X を保護モードで起動するには、この値を1に設定します。</span><span class="sxs-lookup"><span data-stu-id="99701-127">Set this value to <strong>1</strong> in order to start Adobe Reader X in Protected Mode during the launch phase.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="99701-128">**注** 64ビットオペレーティングシステムを実行しているコンピューターの場合は、_MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard\\Overrides. で [_LOCAL HKEY] にレジストリ値を作成します。</span><span class="sxs-lookup"><span data-stu-id="99701-128">**Note** On a computer running a 64-bit operating system, create the registry value under HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard\\Overrides.</span></span>

 

<span data-ttu-id="99701-129">Adobe Reader X パッケージの各 OSD ファイルで、POLICIES 要素の下に次の項目を追加し &lt; &gt; ます。</span><span class="sxs-lookup"><span data-stu-id="99701-129">For each OSD-file in your Adobe Reader X package, add the following items under the &lt;POLICIES&gt; element:</span></span>

`<VIRTUAL_FILE_SYSTEM_PASS_THROUGH>TRUE</VIRTUAL_FILE_SYSTEM_PASS_THROUGH>`

`<VIRTUAL_REGISTRY_PASS_THROUGH>TRUE</VIRTUAL_REGISTRY_PASS_THROUGH>`

`<ENFORCE_ACLS_ON_VREG_MODIFY>TRUE</ENFORCE_ACLS_ON_VREG_MODIFY>`

**<span data-ttu-id="99701-130">新しい Sequencer コマンドラインパラメーター</span><span class="sxs-lookup"><span data-stu-id="99701-130">New Sequencer command-line parameter</span></span>**

<span data-ttu-id="99701-131">Sequencer の GUI を使用してパッケージアクセラレータ (PA) を作成する場合は、パッケージアクセラレータを適用する管理者に対してパッケージ化と展開のガイダンスを提供する RTF または TXT ファイルを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="99701-131">When you create a Package Accelerator (PA) through the Sequencer GUI, you can select an RTF or TXT file that provides packaging and deployment guidance to the administrators who will apply the Package Accelerator.</span></span> <span data-ttu-id="99701-132">この機能は、Sequencer CLI を使って利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="99701-132">This functionality is now available using the Sequencer CLI.</span></span>

`/ACCELERATORDESCRIPTIONFILE:PathToDescriptionFile`

<span data-ttu-id="99701-133">パッケージアクセラレーターの作成時にパッケージ化と展開のガイダンスを提供する RTF または TXT ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="99701-133">Specify a path to an RTF or TXT file that provides packaging and deployment guidance when creating a Package Accelerator.</span></span>

**<span data-ttu-id="99701-134">Microsoft アプリケーションのエラーレポートをインストールする必要がなくなりました</span><span class="sxs-lookup"><span data-stu-id="99701-134">Microsoft Application Error Reporting no longer needs to be installed</span></span>**

<span data-ttu-id="99701-135">setup.msi を使用して App-v 4.6 SP2 クライアントをインストールしているときに、Microsoft アプリケーションエラー報告 (dw20shared.msi) をインストールする必要がなくなりました。</span><span class="sxs-lookup"><span data-stu-id="99701-135">When you are installing the App-V4.6SP2 client by using setup.msi, you no longer need to install Microsoft Application Error Reporting (dw20shared.msi).</span></span> <span data-ttu-id="99701-136">App-V 4.6 SP2 では、Microsoft エラー報告機能が使用されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="99701-136">App-V4.6SP2 now uses Microsoft Error Reporting.</span></span> <span data-ttu-id="99701-137">詳細については、「 [Setup.msiを使用して App-v クライアントをインストールする方法](https://go.microsoft.com/fwlink/?LinkId=267237)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99701-137">For more information, see [How to Install the App-V Client by Using Setup.msi](https://go.microsoft.com/fwlink/?LinkId=267237).</span></span>

**<span data-ttu-id="99701-138">顧客のフィードバックと修正プログラムのロールアップ</span><span class="sxs-lookup"><span data-stu-id="99701-138">Customer feedback and hotfix rollup</span></span>**

<span data-ttu-id="99701-139">App-v 4.6 SP2 には、アプリ-V 4.6 SP1 のリリース以降に発生した問題に対処するための修正プログラムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="99701-139">App-V4.6SP2 includes a rollup of fixes to address issues found since the App-V 4.6 SP1 release.</span></span> <span data-ttu-id="99701-140">App-v 4.6 SP2 には、Microsoft Application Virtualization 4.6 SP1 修正プログラム6を含む最新の修正プログラムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="99701-140">App-V4.6SP2 contains the latest fixes up to and including Microsoft Application Virtualization 4.6 SP1 Hotfix 6.</span></span>

## <span data-ttu-id="99701-141">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="99701-141">In This Section</span></span>


<a href="" id="app-v-4-6-sp2-release-notes"></a>[<span data-ttu-id="99701-142">App-V 4.6 SP2 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="99701-142">App-V 4.6 SP2 Release Notes</span></span>](https://go.microsoft.com/fwlink/?LinkId=267600)  
<span data-ttu-id="99701-143">App-v 4.6 SP2 の既知の問題に関する最新情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="99701-143">Provides the most up-to-date information about known issues with App-V4.6SP2.</span></span>

 

 





