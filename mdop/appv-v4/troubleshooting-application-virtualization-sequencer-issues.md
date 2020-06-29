---
title: Application Virtualization Sequencer の問題のトラブルシューティング
description: Application Virtualization Sequencer の問題のトラブルシューティング
author: dansimp
ms.assetid: 2712094b-a0bc-4643-aced-5415535f3fec
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa8b84f37217f29ff2c08a2254d7f54ce74348d2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815244"
---
# <span data-ttu-id="5ff17-103">Application Virtualization Sequencer の問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="5ff17-103">Troubleshooting Application Virtualization Sequencer Issues</span></span>


<span data-ttu-id="5ff17-104">このトピックには、Application Virtualization (App-v) Sequencer の一般的な問題のトラブルシューティングに役立つ情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5ff17-104">This topic includes information that you can use to help troubleshoot general issues on the Application Virtualization (App-V) Sequencer.</span></span>

## <span data-ttu-id="5ff17-105">App-v のアプリを使用して SFTD ファイルを作成すると、バージョン番号が予期せず大きくなる</span><span class="sxs-lookup"><span data-stu-id="5ff17-105">Creating an SFTD File by Using the App-V Sequencer Increases the Version Number Unexpectedly</span></span>


<span data-ttu-id="5ff17-106">コマンドラインを使用して、新しい sft ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="5ff17-106">Use the command line to generate a new .sft file.</span></span> <span data-ttu-id="5ff17-107">コマンドラインを使用して、sft ファイルを作成するには、コマンドプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5ff17-107">To create the .sft file by using the command line, enter the following at a command prompt:</span></span>

**<span data-ttu-id="5ff17-108">mkdiffpkg.exe &lt; 基本の sft ファイル名 &gt; &lt; 差分 sft ファイル名&gt;</span><span class="sxs-lookup"><span data-stu-id="5ff17-108">mkdiffpkg.exe &lt;base SFT file name&gt; &lt;diff SFT file name&gt;</span></span>**

## <a href="" id="file-name-in-osd-file-is-not-correct-after-package-upgrade-"></a><span data-ttu-id="5ff17-109">パッケージのアップグレード後に、OSD ファイルのファイル名が正しくない</span><span class="sxs-lookup"><span data-stu-id="5ff17-109">File Name in OSD File Is Not Correct After Package Upgrade</span></span>


<span data-ttu-id="5ff17-110">アップグレード用のパッケージを開くときに、パッケージの出力場所としてルート Q:\\ ドライブを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ff17-110">When you open a package for upgrade, you should specify the root Q:\\ drive as the output location for the package.</span></span> <span data-ttu-id="5ff17-111">出力場所に関連付けられたファイル名を指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="5ff17-111">Do not specify an associated file name with the output location.</span></span>

## <span data-ttu-id="5ff17-112">Microsoft Word2003 の既定のインストールでクライアントにストリーム配信するとエラーが発生する</span><span class="sxs-lookup"><span data-stu-id="5ff17-112">Microsoft Word2003 Default Install Results in an Error When Streamed to a Client</span></span>


<span data-ttu-id="5ff17-113">クライアントに Microsoft Word2003 をストリーミングすると、エラーが返されますが、Microsoft Word は引き続き実行されます。</span><span class="sxs-lookup"><span data-stu-id="5ff17-113">When you stream Microsoft Word2003 to a client, an error is returned, but Microsoft Word continues to run.</span></span>

**<span data-ttu-id="5ff17-114">解決策</span><span class="sxs-lookup"><span data-stu-id="5ff17-114">Solution</span></span>**

<span data-ttu-id="5ff17-115">仮想アプリケーションパッケージを再シーケンスして、[**完全インストール**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5ff17-115">Resequence the virtual application package and select **Full Install**.</span></span>

## <span data-ttu-id="5ff17-116">依存パッケージを作成すると、アクティブなアップグレードが機能しない</span><span class="sxs-lookup"><span data-stu-id="5ff17-116">Active Upgrade Does Not Work When You Create a Dependent Package</span></span>


<span data-ttu-id="5ff17-117">アクティブなアップグレードを使用して、新しいレジストリエントリを追加して、依存パッケージを作成すると、正常に機能しているように見えますが、更新されたレジストリエントリは使用できません。</span><span class="sxs-lookup"><span data-stu-id="5ff17-117">When you create a dependent package by using active upgrade and add new registry entries, it appears to function correctly, but the updated registry entries are not available.</span></span>

**<span data-ttu-id="5ff17-118">解決策</span><span class="sxs-lookup"><span data-stu-id="5ff17-118">Solution</span></span>**

<span data-ttu-id="5ff17-119">レジストリ設定は、常に元のバージョンのパッケージと共に保存されるため、パッケージの更新は、元のパッケージを修復しなければ利用できないように見えます。</span><span class="sxs-lookup"><span data-stu-id="5ff17-119">Registry settings are always stored with the original version of the package, so updates to the package will not appear to be available unless you repair the original package.</span></span>

## <span data-ttu-id="5ff17-120">[プロパティ] ページを使用して、Microsoft Office2007 ドキュメントの詳細情報が表示されない</span><span class="sxs-lookup"><span data-stu-id="5ff17-120">Detailed information is not visible for Microsoft Office2007 documents by using the properties page</span></span>


<span data-ttu-id="5ff17-121">[プロパティ] ページを使用して、Microsoft Office2007 ドキュメントに関連付けられている詳細情報を表示しようとすると、詳細情報は表示されません。</span><span class="sxs-lookup"><span data-stu-id="5ff17-121">When you try to view detailed information associated with a Microsoft Office2007 document by using the properties page, the detailed information is not visible.</span></span>

**<span data-ttu-id="5ff17-122">解決策</span><span class="sxs-lookup"><span data-stu-id="5ff17-122">Solution</span></span>**

<span data-ttu-id="5ff17-123">これらのプロパティページに必要なシェルの拡張子は、app-v でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5ff17-123">App-V does not support the required shell extensions for these property pages.</span></span>

## <span data-ttu-id="5ff17-124">16ビットアプリケーションをシーケンスするときに一部のレジストリキーがキャプチャされない</span><span class="sxs-lookup"><span data-stu-id="5ff17-124">Some registry keys are not captured when you sequence 16-bit applications</span></span>


<span data-ttu-id="5ff17-125">App-v 4.5 では、レジストリフックはカーネルモードからユーザーモードに移動されました。</span><span class="sxs-lookup"><span data-stu-id="5ff17-125">In App-V 4.5, registry hooking has been moved from kernel mode to user mode.</span></span> <span data-ttu-id="5ff17-126">16ビットアプリケーションまたは16ビットインストーラーを使用するアプリケーションをシーケンスする場合は、まず、Windows NT 仮想 DOS コンピューター (NTVDM) でプロセスを実行するように sequencer コンピューターを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ff17-126">If you want to sequence a 16-bit application or an application that uses a 16-bit installer, you must first configure the sequencer computer so that the process runs in its own copy of the Windows NT Virtual DOS Machine (NTVDM).</span></span>

**<span data-ttu-id="5ff17-127">解決策</span><span class="sxs-lookup"><span data-stu-id="5ff17-127">Solution</span></span>**

<span data-ttu-id="5ff17-128">優先順位のコンピューターでは、アプリケーションをシーケンスする前に、次のグローバル REGSZ レジストリキー値を [はい] に設定します。</span><span class="sxs-lookup"><span data-stu-id="5ff17-128">Before you sequence the application, set the following global REGSZ registry key value to "yes" on the sequencing computer:</span></span>

<span data-ttu-id="5ff17-129">HKLM\\SYSTEM\\CurrentControlSet\\Control\\WOW\\DefaultSeparateVDM</span><span class="sxs-lookup"><span data-stu-id="5ff17-129">HKLM\\SYSTEM\\CurrentControlSet\\Control\\WOW\\DefaultSeparateVDM</span></span>

<span data-ttu-id="5ff17-130">この機能を有効にするには、コンピューターを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ff17-130">You must restart the computer before this takes effect.</span></span>

## <span data-ttu-id="5ff17-131">関連トピック</span><span class="sxs-lookup"><span data-stu-id="5ff17-131">Related topics</span></span>


[<span data-ttu-id="5ff17-132">Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="5ff17-132">Application Virtualization Sequencer</span></span>](application-virtualization-sequencer.md)

 

 





