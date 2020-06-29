---
title: Differential SFT ファイルを使用する方法
description: Differential SFT ファイルを使用する方法
author: dansimp
ms.assetid: 607e30fd-2f0e-4e2f-b669-0b3f010aebb0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 85cc45f9665569d77fcf275db6dbc080eb919229
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816387"
---
# <span data-ttu-id="ff8b5-103">Differential SFT ファイルを使用する方法</span><span class="sxs-lookup"><span data-stu-id="ff8b5-103">How to Use the Differential SFT File</span></span>


<span data-ttu-id="ff8b5-104">Microsoft Application Virtualization (App-v) Sequencer は、アプリケーションをシーケンスするときに、すべての仮想アプリケーションのファイルのコンテンツと構成情報を格納するために SFT ファイル (sft) を作成します。</span><span class="sxs-lookup"><span data-stu-id="ff8b5-104">When sequencing an application, the Microsoft Application Virtualization (App-V) Sequencer creates SFT files (.sft) to store all of the virtual application’s files content and configuration information.</span></span> <span data-ttu-id="ff8b5-105">App-v のバージョン4.5 では、差分の SFT (dsft) ファイルが導入されています。</span><span class="sxs-lookup"><span data-stu-id="ff8b5-105">In version4.5 of App-V, the Differential SFT (.dsft) file has been introduced.</span></span> <span data-ttu-id="ff8b5-106">Sequencer を使って既存のパッケージのアップグレードを作成した後で、このファイルを生成し、元のシーケンスされたアプリケーションパッケージと新しいバージョンの違いのみを格納することができます。</span><span class="sxs-lookup"><span data-stu-id="ff8b5-106">After using the Sequencer to create an upgrade for an existing package, you can choose to generate this file to store only the differences between the original sequenced application package and the new version.</span></span> <span data-ttu-id="ff8b5-107">このため、新しいバージョンのアプリケーションでは、完全な SFT ファイルよりもずっと小さく、低帯域幅のネットワーク接続を経由してパッケージの更新を送信することによる影響を減らします。</span><span class="sxs-lookup"><span data-stu-id="ff8b5-107">It is therefore much smaller than the full SFT file would be for the new version of the application and reduces the impact of sending package updates over low-bandwidth network connections.</span></span> <span data-ttu-id="ff8b5-108">ただし、この使用は特定の制限された状況でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ff8b5-108">However, its use is supported only in certain restricted situations.</span></span> <span data-ttu-id="ff8b5-109">この機能は、特に電子ソフトウェア配布 (ESD) システムを使用して、ローカルファイルサーバーで低帯域幅接続を使用しているユーザーのグループを管理するために使用されるようにすることを目的としています。また、App-v ストリーミングサーバーを使用していません。</span><span class="sxs-lookup"><span data-stu-id="ff8b5-109">This feature was intended to be used specifically where you are using an electronic software distribution (ESD) system to manage a group of users with a local file server over a low-bandwidth connection and you are not using App-V streaming servers.</span></span>

<span data-ttu-id="ff8b5-110">Configuration Manager は、既に組み込まれている低帯域幅の展開をサポートしているため、構成 Manager2007 を使用してユーザーを管理している場合は、差分の SFT ファイルを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ff8b5-110">You do not need to use the Differential SFT file if you are using Configuration Manager2007 to manage the users, because Configuration Manager has support for low-bandwidth deployments already built in.</span></span> <span data-ttu-id="ff8b5-111">また、Application Virtualization (App-v) 管理またはストリーミングサーバーをアクティブなアップグレードで使用している場合、クライアントは古いパッケージバージョンと新しいパッケージバージョンの違いのみを取得するため、この操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="ff8b5-111">It is also not required if you are using Application Virtualization (App-V) Management or Streaming Servers with Active Upgrade because the client will retrieve only the differences between the old and new package versions.</span></span>

<span data-ttu-id="ff8b5-112">次の手順では、Sequencer のインストールに含まれている mkdiffpkg.exe を使用して、仮想アプリケーションパッケージのアップグレードを完了した後に、差分の SFT ファイルを作成して、差分の SFT ファイルを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ff8b5-112">The following procedure shows how to use the mkdiffpkg.exe that is included in the Sequencer installation to create the Differential SFT file, after completing the upgrade of the virtual application package, and to deploy the Differential SFT file.</span></span> <span data-ttu-id="ff8b5-113">この手順を完了すると、パッケージがクライアントコンピューターから何らかの方法でアンロードされた場合に、ユーザーが次にアプリケーションを実行しようとしたときに、クライアントは、ローカルファイル共有から完全なパッケージ V2 をストリーム処理するように設定された上書き URL に戻ります。</span><span class="sxs-lookup"><span data-stu-id="ff8b5-113">Completing this procedure helps ensure that if the package is somehow unloaded from the client computer, the next time the user tries to run the application, the client will fall back to the override URL, which is set to stream the full package V2.sft from the local file share.</span></span> <span data-ttu-id="ff8b5-114">これにより、アプリケーションの起動時にユーザーがエラーにならないようになります。</span><span class="sxs-lookup"><span data-stu-id="ff8b5-114">This will avoid any failure for the user when starting the application.</span></span> <span data-ttu-id="ff8b5-115">クライアント全体が破損したり、アンインストールされたりした場合は、アップグレードされたパッケージ (V2) の完全バージョンをクライアントに展開するように ESD システムを構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ff8b5-115">If the entire client becomes corrupted or is uninstalled, it is recommended that the ESD system be configured to deploy the full version of the upgraded package, V2.sft, to the client.</span></span>

<span data-ttu-id="ff8b5-116">パッケージのアップグレードの詳細については、「App-v 4.5 の運用ガイド」の「既存の仮想アプリケーションをアップグレードする方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff8b5-116">For more information about upgrading a package, see “How to Upgrade an Existing Virtual Application” in the App-V4.5 Operations Guide at</span></span> <https://go.microsoft.com/fwlink/?LinkId=133129>

<span data-ttu-id="ff8b5-117">**注** 必須条件として、ESD の対象となるすべてのユーザーコンピューターは、ローカルキャッシュに V1 の sft ファイルを完全にロードしている必要があります。また、すべてのコンピューターでファイルストリーミングが有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff8b5-117">**Note** As a prerequisite, all user computers being targeted by the ESD must have the V1.sft file fully loaded into their local cache, and file streaming must be enabled on all computers.</span></span>

 

**<span data-ttu-id="ff8b5-118">同一の SFT ファイルを使用するには</span><span class="sxs-lookup"><span data-stu-id="ff8b5-118">To use the Differential SFT file</span></span>**

1.  <span data-ttu-id="ff8b5-119">管理者権限を持つアカウントを使用して、Sequencer コンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ff8b5-119">Log on to the Sequencer computer by using an account with administrator rights.</span></span> <span data-ttu-id="ff8b5-120">Sequencer でアップグレードの元のパッケージ (V1) を開き、パッケージを新しいバージョン (V2) にアップグレードして、新しいバージョンの sft として保存します。</span><span class="sxs-lookup"><span data-stu-id="ff8b5-120">Open the original package (V1) for upgrade in the Sequencer, and then upgrade the package to the new version (V2) and save it as a new V2.sft.</span></span>

2.  <span data-ttu-id="ff8b5-121">App V 4.5 Sequencer インストールフォルダーでコマンドウィンドウを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ff8b5-121">Open a command window in the App-V4.5 Sequencer installation folder, and run the following command:</span></span>

    `“mkdiffpkg.exe V2.sft V2.dsft”`

3.  <span data-ttu-id="ff8b5-122">ESD システムまたはその他のファイルのコピープロセスを使用して、完全な V2 パッケージコンテンツファイル (V2) を、適切な接続のネットワーク接続のユーザーコンピューターからアクセスできるローカルファイル共有にコピーします。</span><span class="sxs-lookup"><span data-stu-id="ff8b5-122">Using the ESD system or other file copy process, copy the full V2 package content file, V2.sft, to a local file share that is accessible to the user computers on a well-connected network connection.</span></span>

4.  <span data-ttu-id="ff8b5-123">ESD システムを使用して、各ユーザーのコンピューターに、2つの差分の SFT ファイル (V2) のコピーを配置します。</span><span class="sxs-lookup"><span data-stu-id="ff8b5-123">Using the ESD system, place a copy of the Differential SFT file, V2.dsft, on each user computer.</span></span>

5.  <span data-ttu-id="ff8b5-124">V2. dsft ファイルをインポートするには、各ユーザーのコンピューター上で次の SFTMIME コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ff8b5-124">To import the V2.dsft file, run the following SFTMIME command on each user computer:</span></span>

    `“SFTMIME load package:<package name> /SFTPATH <path to V2.dsft>”`

6.  <span data-ttu-id="ff8b5-125">次の SFTMIME コマンドを各ユーザーのコンピューターで実行して、"上書き URL" を設定して、V2 のファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="ff8b5-125">Run the following SFTMIME command on each user computer to set the override URL to point to the V2.sft file:</span></span>

    `“SFTMIME configure package:<package name> /OverrideURL FILE://<network path to V2.sft>”`

**<span data-ttu-id="ff8b5-126">注</span><span class="sxs-lookup"><span data-stu-id="ff8b5-126">Note</span></span>**  
-   <span data-ttu-id="ff8b5-127">差分の SFT ファイルは、正しい順序でクライアントに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff8b5-127">Differential SFT files must be applied to clients in the correct order.</span></span> <span data-ttu-id="ff8b5-128">たとえば、V2 は、V3 の前に V1 アプリケーションに適用する必要があります。 dsft が適用されます。</span><span class="sxs-lookup"><span data-stu-id="ff8b5-128">For example, V2.dsft must be applied to a V1 application before V3.dsft is applied.</span></span>

-   <span data-ttu-id="ff8b5-129">Sequencer での**Microsoft Windows Installer (MSI) パッケージ**機能の生成は、差分の SFT ファイルでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="ff8b5-129">The **Generate Microsoft Windows Installer (MSI) Package** capability in the Sequencer cannot be used with the Differential SFT file.</span></span>

 

## <span data-ttu-id="ff8b5-130">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ff8b5-130">Related topics</span></span>


[<span data-ttu-id="ff8b5-131">App-v Sequencer を使用して仮想アプリケーションを作成またはアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="ff8b5-131">How to Create or Upgrade Virtual Applications Using the App-V Sequencer</span></span>](how-to-create-or-upgrade-virtual-applications-using--the-app-v-sequencer.md)

 

 





