---
title: Application Virtualization Sequencer のトラブルシューティング
description: Application Virtualization Sequencer のトラブルシューティング
author: dansimp
ms.assetid: 12ea8367-0b84-44e1-a885-e0539486556b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 60c47b853c74d90afc21e9ca172c0eec2a2c7a0d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815184"
---
# <span data-ttu-id="29eb8-103">Application Virtualization Sequencer のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="29eb8-103">Troubleshooting the Application Virtualization Sequencer</span></span>


<span data-ttu-id="29eb8-104">このトピックには、Application Virtualization (App-v) Sequencer の一般的な問題のトラブルシューティングに役立つ情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="29eb8-104">This topic includes information that you can use to help troubleshoot general issues on the Application Virtualization (App-V) Sequencer.</span></span>

## <span data-ttu-id="29eb8-105">App-v のアプリを使用して SFTD ファイルを作成すると、バージョン番号が予期せず大きくなる</span><span class="sxs-lookup"><span data-stu-id="29eb8-105">Creating an SFTD File by Using the App-V Sequencer Increases the Version Number Unexpectedly</span></span>


<span data-ttu-id="29eb8-106">SFTD ファイルに関連付けられているバージョン番号が、予期せず増加します。</span><span class="sxs-lookup"><span data-stu-id="29eb8-106">The version number associated with an SFTD file increases unexpectedly.</span></span>

**<span data-ttu-id="29eb8-107">解決策</span><span class="sxs-lookup"><span data-stu-id="29eb8-107">Solution</span></span>**

<span data-ttu-id="29eb8-108">コマンドラインを使用して、新しい sft ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="29eb8-108">Use the command line to generate a new .sft file.</span></span> <span data-ttu-id="29eb8-109">コマンドラインを使用して、sft ファイルを作成するには、コマンドプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="29eb8-109">To create the .sft file by using the command line, enter the following at a command prompt:</span></span>

**<span data-ttu-id="29eb8-110">mkdiffpkg.exe &lt; 基本の sft ファイル名 &gt; &lt; 差分 sft ファイル名&gt;</span><span class="sxs-lookup"><span data-stu-id="29eb8-110">mkdiffpkg.exe &lt;base SFT file name&gt; &lt;diff SFT file name&gt;</span></span>**

## <a href="" id="file-name-in-osd-file-is-not-correct-after-package-upgrade-"></a><span data-ttu-id="29eb8-111">パッケージのアップグレード後に、OSD ファイルのファイル名が正しくない</span><span class="sxs-lookup"><span data-stu-id="29eb8-111">File Name in OSD File Is Not Correct After Package Upgrade</span></span>


<span data-ttu-id="29eb8-112">既存のパッケージをアップグレードした後、ファイル名が間違っています。</span><span class="sxs-lookup"><span data-stu-id="29eb8-112">After you upgrade an existing package, the file name is not correct.</span></span>

**<span data-ttu-id="29eb8-113">解決策</span><span class="sxs-lookup"><span data-stu-id="29eb8-113">Solution</span></span>**

<span data-ttu-id="29eb8-114">アップグレード用のパッケージを開くときに、パッケージの出力場所としてルート Q:\\ ドライブを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29eb8-114">When you open a package for upgrade, you should specify the root Q:\\ drive as the output location for the package.</span></span> <span data-ttu-id="29eb8-115">出力場所に関連付けられたファイル名を指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="29eb8-115">Do not specify an associated file name with the output location.</span></span>

## <span data-ttu-id="29eb8-116">Microsoft Word2003 の既定のインストールでクライアントにストリーム配信するとエラーが発生する</span><span class="sxs-lookup"><span data-stu-id="29eb8-116">Microsoft Word2003 Default Install Results in an Error When Streamed to a Client</span></span>


<span data-ttu-id="29eb8-117">クライアントに Microsoft Word2003 をストリーミングすると、エラーが返されますが、Microsoft Word は引き続き実行されます。</span><span class="sxs-lookup"><span data-stu-id="29eb8-117">When you stream Microsoft Word2003 to a client, an error is returned but Microsoft Word continues to run.</span></span>

**<span data-ttu-id="29eb8-118">解決策</span><span class="sxs-lookup"><span data-stu-id="29eb8-118">Solution</span></span>**

<span data-ttu-id="29eb8-119">仮想アプリケーションパッケージを再シーケンスして、[**完全インストール**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="29eb8-119">Resequence the virtual application package, and select **Full Install**.</span></span>

## <span data-ttu-id="29eb8-120">依存パッケージを作成するときに、パッケージのアップグレードが機能しない</span><span class="sxs-lookup"><span data-stu-id="29eb8-120">Package Upgrade Does Not Work When You Create a Dependent Package</span></span>


<span data-ttu-id="29eb8-121">パッケージアップグレードを使って依存パッケージを作成し、新しいレジストリエントリを追加すると、正常に機能しているように見えますが、更新されたレジストリエントリは使用できません。</span><span class="sxs-lookup"><span data-stu-id="29eb8-121">When you create a dependent package by using package upgrade and add new registry entries, it appears to function correctly but the updated registry entries are not available.</span></span>

**<span data-ttu-id="29eb8-122">解決策</span><span class="sxs-lookup"><span data-stu-id="29eb8-122">Solution</span></span>**

<span data-ttu-id="29eb8-123">レジストリ設定は、常に元のバージョンのパッケージと共に保存されるため、パッケージの更新は、元のパッケージを修復しなければ利用できないように見えます。</span><span class="sxs-lookup"><span data-stu-id="29eb8-123">Registry settings are always stored with the original version of the package, so updates to the package will not appear to be available unless you repair the original package.</span></span>

## <span data-ttu-id="29eb8-124">シーケンス中にエラーが発生しました。NET 2.0</span><span class="sxs-lookup"><span data-stu-id="29eb8-124">Error When Trying to Sequence .NET2.0</span></span>


<span data-ttu-id="29eb8-125">必要なパッケージをシーケンスする場合。NET 2.0 というエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="29eb8-125">When you sequence a package that requires .NET2.0, you get an error.</span></span>

**<span data-ttu-id="29eb8-126">解決策</span><span class="sxs-lookup"><span data-stu-id="29eb8-126">Solution</span></span>**

<span data-ttu-id="29eb8-127">必要なシーケンスパッケージ。NET 2.0 はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="29eb8-127">Sequencing packages that require .NET2.0 is not supported.</span></span>

## <span data-ttu-id="29eb8-128">関連トピック</span><span class="sxs-lookup"><span data-stu-id="29eb8-128">Related topics</span></span>


[<span data-ttu-id="29eb8-129">Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="29eb8-129">Application Virtualization Sequencer</span></span>](application-virtualization-sequencer.md)

 

 





