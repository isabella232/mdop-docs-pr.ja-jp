---
title: App-V 4.6 SP2 リリース ノート
description: App-V 4.6 SP2 リリース ノート
author: dansimp
ms.assetid: abb536f0-e187-4c5b-952a-f837abd10ad2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: cf36a6361e6f49c2b868c6752e1b2eb379cc9a31
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822344"
---
# <span data-ttu-id="f1b9d-103">App-V 4.6 SP2 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="f1b9d-103">App-V 4.6 SP2 Release Notes</span></span>


**<span data-ttu-id="f1b9d-104">これらのリリースノートを検索するには、CTRL キーを押しながら F キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f1b9d-104">To search these release notes, press CTRL+F.</span></span>**

<span data-ttu-id="f1b9d-105">Microsoft Application Virtualization (App-v) 4.6 SP2 をインストールする前に、これらのリリースノートをよくお読みください。</span><span class="sxs-lookup"><span data-stu-id="f1b9d-105">Read these release notes thoroughly before you install Microsoft Application Virtualization (App-V)4.6 SP2.</span></span>

<span data-ttu-id="f1b9d-106">これらのリリースノートには、Application Virtualization 4.6 SP2 を正常にインストールするために必要な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f1b9d-106">These release notes contain information that is required to successfully install Application Virtualization 4.6 SP2.</span></span> <span data-ttu-id="f1b9d-107">リリースノートには、製品ドキュメントに記載されていない情報も含まれています。</span><span class="sxs-lookup"><span data-stu-id="f1b9d-107">The release notes also contain information that is not available in the product documentation.</span></span> <span data-ttu-id="f1b9d-108">これらのリリースノートと他の App-v 4.6 SP2 ドキュメントの間に違いがある場合は、最新の変更を、権威を持つものとして扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1b9d-108">If there is a difference between these release notes and other App-V4.6SP2 documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="f1b9d-109">これらのリリースノートは、この製品に含まれているコンテンツに代わるものです。</span><span class="sxs-lookup"><span data-stu-id="f1b9d-109">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="f1b9d-110">製品ドキュメントについて</span><span class="sxs-lookup"><span data-stu-id="f1b9d-110">About the Product Documentation</span></span>


<span data-ttu-id="f1b9d-111">App-v のドキュメントの詳細については、Microsoft TechNet の[Application Virtualization](https://go.microsoft.com/fwlink/?LinkID=232982)ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1b9d-111">For more information about documentation for App-V, see the [Application Virtualization](https://go.microsoft.com/fwlink/?LinkID=232982) page on Microsoft TechNet.</span></span>

## <span data-ttu-id="f1b9d-112">フィードバックの提供</span><span class="sxs-lookup"><span data-stu-id="f1b9d-112">Providing feedback</span></span>


<span data-ttu-id="f1b9d-113">弊社では、App-v 4.6 SP2 についてご意見をお寄せしています。</span><span class="sxs-lookup"><span data-stu-id="f1b9d-113">We are interested in your feedback on App-V4.6SP2.</span></span> <span data-ttu-id="f1b9d-114">にフィードバックを送信でき <mdopdocs@microsoft.com> ます。</span><span class="sxs-lookup"><span data-stu-id="f1b9d-114">You can send your feedback to <mdopdocs@microsoft.com>.</span></span>

<span data-ttu-id="f1b9d-115">**注** このメールアドレスはサポートチャネルではありませんが、お客様からのフィードバックは、弊社のドキュメントと製品リリースの将来の変更を計画するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f1b9d-115">**Note** This email address is not a support channel, but your feedback will help us to plan future changes for our documentation and product releases.</span></span>

 

<span data-ttu-id="f1b9d-116">MDOP と追加のラーニングリソースに関する最新情報については、「 [mdop の情報エクスペリエンス](https://go.microsoft.com/fwlink/p/?LinkId=236032)」ページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f1b9d-116">For the latest information about MDOP and additional learning resources, see the [MDOP Information Experience](https://go.microsoft.com/fwlink/p/?LinkId=236032) page.</span></span>

<span data-ttu-id="f1b9d-117">新しい更新プログラムまたはフィードバックを提供する方法について詳しくは、 [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)または[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f1b9d-117">For more information about new updates or to provide feedback, follow us on [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445) or [Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447).</span></span>

## <a href="" id="known-issues-with-app-v-4-6-sp2-"></a><span data-ttu-id="f1b9d-118">App-v 4.6 SP2 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="f1b9d-118">Known Issues with App-V4.6SP2</span></span>


### <span data-ttu-id="f1b9d-119">シーケンスの際に、システム以外の物理ドライブの短いファイル名のサポートは無効になります</span><span class="sxs-lookup"><span data-stu-id="f1b9d-119">Short file name support is disabled for non-system physical drives when you sequence</span></span>

<span data-ttu-id="f1b9d-120">Windows 8 または Windows Server 2012 でシーケンスを行うと、システム以外の物理ドライブの場合、短いファイル名 (8.3) のサポートは既定で無効になります。</span><span class="sxs-lookup"><span data-stu-id="f1b9d-120">When you sequence on Windows 8 or Windows Server 2012, support for short file names (8.3) is disabled by default for non-system physical drives.</span></span>

<span data-ttu-id="f1b9d-121">シーケンスステーションのプライマリ仮想アプリケーションディレクトリ (たとえば、"Q:\\appname") に関連付けられた基になる物理ドライブは、仮想アプリケーションパッケージを作成するときに短いファイル名を生成するために、短いファイル名 (8.3) のサポートを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1b9d-121">The underlying physical drive associated with the primary virtual application directory (for example, “Q:\\appname”) on the sequencing station must provide short file name (8.3) support in order for the App-V4.6SP2 Sequencer to generate short file names when creating virtual application packages.</span></span> <span data-ttu-id="f1b9d-122">短いファイル名 (8.3) Windows 8 または Windows Server 2012 のシステム以外の物理ドライブでは、既定でサポートが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="f1b9d-122">Short file name (8.3) support is disabled by default for non-system physical drives on Windows 8 or Windows Server 2012.</span></span>

<span data-ttu-id="f1b9d-123">**回避策:** システム以外の物理ドライブで短いファイル名 (8.3) のサポートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f1b9d-123">**Workaround:** Enable short file name (8.3) support on non-system physical drives.</span></span> <span data-ttu-id="f1b9d-124">Windows 8 または Windows Server 2012 で短いファイル名のサポートを有効にするには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f1b9d-124">You can use the following command to enable short file name support on Windows 8 or Windows Server 2012.</span></span>

``` syntax
fsutil 8dot3name set <virtual drive letter>:
```

<span data-ttu-id="f1b9d-125">たとえば、ドライブ文字が "Q:" の場合は、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f1b9d-125">For example, use the following command if the drive letter is “Q:”:</span></span>

``` syntax
fsutil 8dot3name set Q: 0
```

<span data-ttu-id="f1b9d-126">**注** App-v ファイルシステムでは、Windows 8 または Windows Server 2012 上の短いパスが適切に処理されるため、App-v クライアントでこの設定を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f1b9d-126">**Note** You do not need to change this setting on the App-V client because the App-V file system properly handles short paths on Windows 8 or Windows Server 2012.</span></span>

 

### <a href="" id="-------------app-v-does-not-override-the-default-handler-for-file-type-or-protocol-associations-on-windows-8"></a> <span data-ttu-id="f1b9d-127">Windows 8 でのファイルの種類またはプロトコルの関連付けの既定のハンドラーを、app-v が上書きしない</span><span class="sxs-lookup"><span data-stu-id="f1b9d-127">App-V does not override the default handler for file type or protocol associations on Windows 8</span></span>

<span data-ttu-id="f1b9d-128">Windows 8 の**コントロールパネル**の [**既定のプログラム**] を使って既定のアプリケーションを選択した場合、そのアプリケーションに関連付けられているファイルの種類の関連付けは、app-v によって上書きされません。</span><span class="sxs-lookup"><span data-stu-id="f1b9d-128">If you select a default application by using **Default Programs** in **Control Panel** on Windows 8, App-V will not override the associated file type associations for that application.</span></span>

<span data-ttu-id="f1b9d-129">**回避策:**-.</span><span class="sxs-lookup"><span data-stu-id="f1b9d-129">**Workaround:** None.</span></span>

### <span data-ttu-id="f1b9d-130">仮想化された Outlook 2010 は、Windows 8 の mailto クリックリンクのオプションとして提供されていません。</span><span class="sxs-lookup"><span data-stu-id="f1b9d-130">Virtualized Outlook 2010 is not offered as an option for mailto clickable links on Windows 8</span></span>

<span data-ttu-id="f1b9d-131">Mailto シェル拡張機能では、Windows 8 で仮想化された Outlook 2010 は提供されません。</span><span class="sxs-lookup"><span data-stu-id="f1b9d-131">The mailto shell extension does not offer virtualized Outlook 2010 on Windows 8.</span></span> <span data-ttu-id="f1b9d-132">たとえば、Windows 8 で実行されている仮想化された Outlook 2010 から mailto: リンクをクリックした場合、新しいメールウィンドウは作成されません。</span><span class="sxs-lookup"><span data-stu-id="f1b9d-132">For example, if you click a mailto: link from virtualized Outlook 2010 that is running on Windows 8, a new email window is not created.</span></span> <span data-ttu-id="f1b9d-133">このオプションは、windows 7 およびそれ以前のバージョンの Windows オペレーティングシステムで正しく動作します。</span><span class="sxs-lookup"><span data-stu-id="f1b9d-133">This option works correctly on Windows 7 and earlier versions of the Windows operating system.</span></span>

<span data-ttu-id="f1b9d-134">**回避策:**-.</span><span class="sxs-lookup"><span data-stu-id="f1b9d-134">**Workaround:** None.</span></span>

### <a href="" id="-------------application-virtualization-4-6-sp2-update-is-not-offered-on-all-locales-that-use-microsoft-update"></a> <span data-ttu-id="f1b9d-135">Microsoft Update を使用するすべてのロケールで Application Virtualization 4.6 SP2 更新プログラムが提供されない</span><span class="sxs-lookup"><span data-stu-id="f1b9d-135">Application Virtualization 4.6 SP2 update is not offered on all locales that use Microsoft Update</span></span>

<span data-ttu-id="f1b9d-136">Microsoft Update を使用している場合、以下の言語ロケールでは、App-v 4.6 SP2 の更新プログラムは使用できません。</span><span class="sxs-lookup"><span data-stu-id="f1b9d-136">When you use Microsoft Update, the update for App-V4.6SP2 is not available for the following language locales:</span></span>

-   <span data-ttu-id="f1b9d-137">カザフ語</span><span class="sxs-lookup"><span data-stu-id="f1b9d-137">Kazakh</span></span>

-   <span data-ttu-id="f1b9d-138">ヒンディー語</span><span class="sxs-lookup"><span data-stu-id="f1b9d-138">Hindi</span></span>

-   <span data-ttu-id="f1b9d-139">セルビア語-キリル</span><span class="sxs-lookup"><span data-stu-id="f1b9d-139">Serbian-Cyrillic</span></span>

<span data-ttu-id="f1b9d-140">**回避策:** Microsoft Windows Server Update Services (WSUS) を使用している場合は、英語版の更新プログラムを使用するか、Microsoft Update カタログから更新プログラムをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="f1b9d-140">**Workaround:** If you are using Microsoft Windows Server Update Services (WSUS), use the English version of the update or download the update from the Microsoft Update Catalog.</span></span>

## <span data-ttu-id="f1b9d-141">リリースノートの著作権情報</span><span class="sxs-lookup"><span data-stu-id="f1b9d-141">Release Notes Copyright Information</span></span>


<span data-ttu-id="f1b9d-142">Microsoft、Active Directory、ActiveX、Bing、Excel、Silverlight、SQLServer、Windows、microsoft Intune、WindowsPowerShell は、Microsoft の会社グループの商標です。</span><span class="sxs-lookup"><span data-stu-id="f1b9d-142">Microsoft, Active Directory, ActiveX, Bing, Excel, Silverlight, SQLServer, Windows, MicrosoftIntune, and WindowsPowerShell are trademarks of the Microsoft group of companies.</span></span> <span data-ttu-id="f1b9d-143">その他のすべての商標は、該当する所有者に帰属します。</span><span class="sxs-lookup"><span data-stu-id="f1b9d-143">All other trademarks are property of their respective owners.</span></span>



## <span data-ttu-id="f1b9d-144">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f1b9d-144">Related topics</span></span>


[<span data-ttu-id="f1b9d-145">Microsoft Application Virtualization 4.6 SP2 について</span><span class="sxs-lookup"><span data-stu-id="f1b9d-145">About Microsoft Application Virtualization 4.6 SP2</span></span>](about-microsoft-application-virtualization-46-sp2.md)

 

 





