---
title: MED-V インストール ファイルのコマンド ライン オプション
description: MED-V インストール ファイルのコマンド ライン オプション
author: dansimp
ms.assetid: 7b8cd3e4-1d09-44a0-b690-f85b0d0a6b02
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 39582a592a59a4d0e81ef406edc6a984497275c7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826467"
---
# <span data-ttu-id="216d8-103">MED-V インストール ファイルのコマンド ライン オプション</span><span class="sxs-lookup"><span data-stu-id="216d8-103">Command-Line Options for MED-V Installation Files</span></span>


<span data-ttu-id="216d8-104">Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 をインストールまたはアンインストールするときに、コマンドプロンプトでインストールファイルを実行するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="216d8-104">When you install or uninstall Microsoft Enterprise Desktop Virtualization (MED-V) 2.0, you have the option of running the installation files at the command prompt.</span></span> <span data-ttu-id="216d8-105">このセクションでは、コマンドプロンプトで MED-V をインストールまたはアンインストールするときに指定できるさまざまなオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="216d8-105">This section describes different options that you can specify when you install or uninstall MED-V at the command prompt.</span></span>

### <span data-ttu-id="216d8-106">コマンドライン引数</span><span class="sxs-lookup"><span data-stu-id="216d8-106">Command-Line Arguments</span></span>

<span data-ttu-id="216d8-107">次のコマンドライン引数を、それぞれの MED-V インストールファイルと共に使うことができます。</span><span class="sxs-lookup"><span data-stu-id="216d8-107">You can use the following command-line arguments together with their respective MED-V installation files.</span></span>

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="216d8-108">インストールファイル</span><span class="sxs-lookup"><span data-stu-id="216d8-108">Installation File</span></span></th>
<th align="left"><span data-ttu-id="216d8-109">引数</span><span class="sxs-lookup"><span data-stu-id="216d8-109">Argument</span></span></th>
<th align="left"><span data-ttu-id="216d8-110">受け入れられる値</span><span class="sxs-lookup"><span data-stu-id="216d8-110">Accepted Values</span></span></th>
<th align="left"><span data-ttu-id="216d8-111">型</span><span class="sxs-lookup"><span data-stu-id="216d8-111">Type</span></span></th>
<th align="left"><span data-ttu-id="216d8-112">説明</span><span class="sxs-lookup"><span data-stu-id="216d8-112">Description</span></span></th>
<th align="left"><span data-ttu-id="216d8-113">既定値</span><span class="sxs-lookup"><span data-stu-id="216d8-113">Default</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="216d8-114">Host Agent</span><span class="sxs-lookup"><span data-stu-id="216d8-114">Host Agent</span></span></p></td>
<td align="left"><p><span data-ttu-id="216d8-115">MEDVDIR</span><span class="sxs-lookup"><span data-stu-id="216d8-115">MEDVDIR</span></span></p></td>
<td align="left"><p><span data-ttu-id="216d8-116">&lt;インストールパス&gt;</span><span class="sxs-lookup"><span data-stu-id="216d8-116">&lt;install path&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="216d8-117">インストール</span><span class="sxs-lookup"><span data-stu-id="216d8-117">Installation</span></span></p></td>
<td align="left"><p><span data-ttu-id="216d8-118">インストールされているディレクトリを変更する</span><span class="sxs-lookup"><span data-stu-id="216d8-118">Change installed directory</span></span></p></td>
<td align="left"><p><span data-ttu-id="216d8-119">インストールは、プログラムのエンタープライズデスクトップ仮想化に進みます。</span><span class="sxs-lookup"><span data-stu-id="216d8-119">Installation goes to Program Files\Microsoft Enterprise Desktop Virtualization.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="216d8-120">MED-V ワークスペースパッケージャー</span><span class="sxs-lookup"><span data-stu-id="216d8-120">MED-V Workspace Packager</span></span></p></td>
<td align="left"><p><span data-ttu-id="216d8-121">MEDVDIR</span><span class="sxs-lookup"><span data-stu-id="216d8-121">MEDVDIR</span></span></p></td>
<td align="left"><p><span data-ttu-id="216d8-122">&lt;インストールパス&gt;</span><span class="sxs-lookup"><span data-stu-id="216d8-122">&lt;install path&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="216d8-123">インストール</span><span class="sxs-lookup"><span data-stu-id="216d8-123">Installation</span></span></p></td>
<td align="left"><p><span data-ttu-id="216d8-124">インストールされているディレクトリを変更する</span><span class="sxs-lookup"><span data-stu-id="216d8-124">Change installed directory</span></span></p></td>
<td align="left"><p><span data-ttu-id="216d8-125">インストールは、プログラムのエンタープライズデスクトップ仮想化に進みます。</span><span class="sxs-lookup"><span data-stu-id="216d8-125">Installation goes to Program Files\Microsoft Enterprise Desktop Virtualization.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="216d8-126">MED-V ワークスペース</span><span class="sxs-lookup"><span data-stu-id="216d8-126">MED-V workspace</span></span></p></td>
<td align="left"><p><span data-ttu-id="216d8-127">INSTALLDIR</span><span class="sxs-lookup"><span data-stu-id="216d8-127">INSTALLDIR</span></span></p></td>
<td align="left"><p><span data-ttu-id="216d8-128">&lt;インストールパス&gt;</span><span class="sxs-lookup"><span data-stu-id="216d8-128">&lt;install path&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="216d8-129">インストール</span><span class="sxs-lookup"><span data-stu-id="216d8-129">Installation</span></span></p></td>
<td align="left"><p><span data-ttu-id="216d8-130">インストールされているディレクトリを変更する</span><span class="sxs-lookup"><span data-stu-id="216d8-130">Change installed directory</span></span></p></td>
<td align="left"><p><span data-ttu-id="216d8-131">インストールは ProgramData\Microsoft\Medv\Workspace. に進みます。</span><span class="sxs-lookup"><span data-stu-id="216d8-131">Installation goes to ProgramData\Microsoft\Medv\Workspace.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="216d8-132">MED-V ワークスペース</span><span class="sxs-lookup"><span data-stu-id="216d8-132">MED-V workspace</span></span></p></td>
<td align="left"><p><span data-ttu-id="216d8-133">VHD の上書き</span><span class="sxs-lookup"><span data-stu-id="216d8-133">OVERWRITE VHD</span></span></p></td>
<td align="left"><p><span data-ttu-id="216d8-134">0 または 1</span><span class="sxs-lookup"><span data-stu-id="216d8-134">0 or 1</span></span></p></td>
<td align="left"><p><span data-ttu-id="216d8-135">インストール</span><span class="sxs-lookup"><span data-stu-id="216d8-135">Installation</span></span></p></td>
<td align="left"><p><span data-ttu-id="216d8-136">VHD が存在する場合 (0) または既存の VHD (1) を上書きすると、インストールが失敗します。</span><span class="sxs-lookup"><span data-stu-id="216d8-136">Fail installation if VHD exists(0) or overwrite existing VHD(1).</span></span></p></td>
<td align="left"><p><span data-ttu-id="216d8-137">仮想ハードディスク (VHD) が既に存在する場合、上書きは行われず、インストールが失敗します。</span><span class="sxs-lookup"><span data-stu-id="216d8-137">Overwrite does not occur and installation fails if a virtual hard disk (VHD) already exists.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="216d8-138">MED-V ワークスペース</span><span class="sxs-lookup"><span data-stu-id="216d8-138">MED-V workspace</span></span></p></td>
<td align="left"><p><span data-ttu-id="216d8-139">SUPPRESSMEDVLAUNCH</span><span class="sxs-lookup"><span data-stu-id="216d8-139">SUPPRESSMEDVLAUNCH</span></span></p></td>
<td align="left"><p><span data-ttu-id="216d8-140">0 または 1</span><span class="sxs-lookup"><span data-stu-id="216d8-140">0 or 1</span></span></p></td>
<td align="left"><p><span data-ttu-id="216d8-141">インストール</span><span class="sxs-lookup"><span data-stu-id="216d8-141">Installation</span></span></p></td>
<td align="left"><p><span data-ttu-id="216d8-142">MED-V ワークスペースをインストールした後、開始 (0) または start (1) MED-V を実行します。</span><span class="sxs-lookup"><span data-stu-id="216d8-142">Start(0) or do not start(1) MED-V after MED-V workspace is installed.</span></span></p></td>
<td align="left"><p><span data-ttu-id="216d8-143">ユーザーインターフェイス (UI) を使って MED-V ワークスペースをインストールした場合、[完了] ページのチェックボックスで、 <strong> </strong> med-v を開始するかどうかが制御されます。</span><span class="sxs-lookup"><span data-stu-id="216d8-143">If the MED-V workspace was installed with the user interface (UI), a check box on the <strong>Finish</strong> page controls whether to start MED-V.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="216d8-144">MED-V ワークスペース</span><span class="sxs-lookup"><span data-stu-id="216d8-144">MED-V workspace</span></span></p></td>
<td align="left"><p><span data-ttu-id="216d8-145">DELETEDISKS ディスク</span><span class="sxs-lookup"><span data-stu-id="216d8-145">DELETEDIFFDISKS</span></span></p></td>
<td align="left"><p><span data-ttu-id="216d8-146">0 または 1</span><span class="sxs-lookup"><span data-stu-id="216d8-146">0 or 1</span></span></p></td>
<td align="left"><p><span data-ttu-id="216d8-147">アンインストール</span><span class="sxs-lookup"><span data-stu-id="216d8-147">Uninstallation</span></span></p></td>
<td align="left"><p><span data-ttu-id="216d8-148">Keep (0) または delete (1) の場合は、MED-V で作成された Vhd</span><span class="sxs-lookup"><span data-stu-id="216d8-148">Keep(0) or delete(1) VHDs created by MED-V</span></span></p></td>
<td align="left"><p><span data-ttu-id="216d8-149">Vhd は削除されません。</span><span class="sxs-lookup"><span data-stu-id="216d8-149">No VHDs are deleted.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="216d8-150">コマンドライン引数の例</span><span class="sxs-lookup"><span data-stu-id="216d8-150">Examples of Command-Line Arguments</span></span>

<span data-ttu-id="216d8-151">次の例では、MED-V workspace パッケージャーによって作成された MED-V ワークスペースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="216d8-151">The following example installs the MED-V workspace created by the MED-V workspace Packager.</span></span> <span data-ttu-id="216d8-152">インストールファイルは Temp ディレクトリにログファイルを作成し、quiet モードでインストールファイルを実行しますが、完了時に MED-V ホストエージェントを起動しません。</span><span class="sxs-lookup"><span data-stu-id="216d8-152">The installation file creates a log file in the Temp directory and runs the installation file in quiet mode, but does not start the MED-V Host Agent on completion.</span></span> <span data-ttu-id="216d8-153">インストールファイルでは、以前のインストールで残っていた VHD が、同じ名前で上書きされます。</span><span class="sxs-lookup"><span data-stu-id="216d8-153">The installation file overwrites any VHD left behind by a previous installation that has the same name.</span></span>

``` syntax
setup.exe /l* %temp%\medv-workspace-install.log /qn SUPPRESSMEDVLAUNCH=1 OVERWRITEVHD=1
```

<span data-ttu-id="216d8-154">次の例では、以前にインストールされた MED-V ワークスペースをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="216d8-154">The following example uninstalls the MED-V workspace that was previously installed.</span></span> <span data-ttu-id="216d8-155">インストールファイルは Temp ディレクトリにログファイルを作成し、quiet モードでインストールファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="216d8-155">The installation file creates a log file in the Temp directory and runs the installation file in quiet mode.</span></span> <span data-ttu-id="216d8-156">インストールファイルは、残っている仮想ハードディスクのファイルをファイルシステムから削除します。</span><span class="sxs-lookup"><span data-stu-id="216d8-156">The installation file deletes any remaining virtual hard disk files from the file system.</span></span>

``` syntax
%ProgramData%\Microsoft\Medv\Workspace\uninstall.exe /l* %temp%\medv-workspace-uninstall.log /qn DELETEDIFFDISKS=1
```

## <span data-ttu-id="216d8-157">関連トピック</span><span class="sxs-lookup"><span data-stu-id="216d8-157">Related topics</span></span>


[<span data-ttu-id="216d8-158">MED-V コンポーネントを展開する</span><span class="sxs-lookup"><span data-stu-id="216d8-158">Deploy the MED-V Components</span></span>](deploy-the-med-v-components.md)

[<span data-ttu-id="216d8-159">MED-V テクニカル リファレンス</span><span class="sxs-lookup"><span data-stu-id="216d8-159">Technical Reference for MED-V</span></span>](technical-reference-for-med-v.md)

 

 





