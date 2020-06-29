---
title: コマンド ラインを使用してクライアントをインストールする方法
description: コマンド ラインを使用してクライアントをインストールする方法
author: dansimp
ms.assetid: ed372403-64ff-48ff-a3cd-a46cad04a4d5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: eca594e1399b4ca4f680f68efffcd011fdc5f042
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817324"
---
# <span data-ttu-id="0ffb0-103">コマンド ラインを使用してクライアントをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="0ffb0-103">How to Install the Client by Using the Command Line</span></span>


<span data-ttu-id="0ffb0-104">このセクションのトピックでは、setup.exe または setup.msi を使用して、Application Virtualization (App-v) デスクトップクライアントまたはリモートデスクトップサービス (旧ターミナルサービス) の App-v クライアントのいずれかをインストールする手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="0ffb0-104">The topics in this section include procedures to install either the Application Virtualization (App-V) Desktop Client or the App-V Client for Remote Desktop Services (formerly Terminal Services) by using either setup.exe or setup.msi.</span></span> <span data-ttu-id="0ffb0-105">セットアッププログラムを実行するには、管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="0ffb0-105">Administrative rights are required to run either setup program.</span></span>

<span data-ttu-id="0ffb0-106">オプションのコマンドラインパラメーターを使用して、インストール時に特定の構成設定を App-v クライアントに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="0ffb0-106">You can use optional command-line parameters to apply specific configuration settings to the App-V client during the installation.</span></span> <span data-ttu-id="0ffb0-107">パラメーターの使用の詳細については、「 [Application Virtualization クライアントインストーラーのコマンドラインパラメーター](application-virtualization-client-installer-command-line-parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ffb0-107">For more information about using parameters, see [Application Virtualization Client Installer Command-Line Parameters](application-virtualization-client-installer-command-line-parameters.md).</span></span> <span data-ttu-id="0ffb0-108">クライアントを展開する前に (たとえば、グループポリシーを使用して)、レジストリ設定をコンピューターに適用した場合、これらの設定は保持され、その他のコマンドラインパラメーターが適用されます。</span><span class="sxs-lookup"><span data-stu-id="0ffb0-108">If you have applied registry settings to a computer before deploying a client—for example, by using Group Policy—these settings are retained and any additional command line parameters are applied.</span></span> <span data-ttu-id="0ffb0-109">コマンドラインパラメーターの値によって、同じ設定の既存の値が置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="0ffb0-109">Command line parameter values will replace any existing value for the same setting.</span></span>

<span data-ttu-id="0ffb0-110">**注** VDI server の実装などの読み取り専用キャッシュで使用するように App-v クライアントをインストールする場合、キャッシュが読み取り専用のときにクライアントがアプリケーションを更新しないように、 *Autoloadtarget*パラメーターを NONE に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ffb0-110">**Note** When you install the App-V client to use with a read-only cache, for example with a VDI server implementation, you must set the *AUTOLOADTARGET* parameter to NONE to prevent the client from trying to update applications when the cache is read-only.</span></span>

 

<span data-ttu-id="0ffb0-111">これらのパラメーターをインストール後に設定する方法について詳しくは、コマンドライン (Application Virtualization (App-v) 運用ガイド) を[使って、App-v クライアントのレジストリ設定を構成する方法](https://go.microsoft.com/fwlink/?LinkId=169355)をご覧ください https://go.microsoft.com/fwlink/?LinkId=169355) 。</span><span class="sxs-lookup"><span data-stu-id="0ffb0-111">For more information about setting these parameter values after installation, see [How to Configure the App-V Client Registry Settings by Using the Command Line](https://go.microsoft.com/fwlink/?LinkId=169355) (https://go.microsoft.com/fwlink/?LinkId=169355) in the Application Virtualization (App-V) Operations Guide.</span></span>

<span data-ttu-id="0ffb0-112">**注** ユーザーのコンピューターの構成設定がクライアントのインストールパスに依存する場合は、Application Virtualization (App-v) 4.5 クライアントで、以前のバージョンとは異なるフォルダーにインストールファイルがコピーされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0ffb0-112">**Note** If a configuration setting on the user’s computer depends on the client installation path, note that the Application Virtualization (App-V)4.5 client copies its installation files to a different folder than previous versions did.</span></span> <span data-ttu-id="0ffb0-113">既定では、App-v 4.5 クライアントの新規インストールによって、そのインストールファイルが¥¥ Program files ¥ Microsoft Application Virtualization Client フォルダーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="0ffb0-113">By default, a new installation of the App-V4.5 client will copy its installation files to the \\Program Files\\Microsoft Application Virtualization Client folder.</span></span> <span data-ttu-id="0ffb0-114">以前のバージョンのクライアントが既にインストールされている場合は、App-v 4.5 クライアントインストーラーを実行すると、既存のインストールフォルダーを使って既存のクライアントのアップグレードが実行されます。</span><span class="sxs-lookup"><span data-stu-id="0ffb0-114">If an earlier version of the client is already installed, running the App-V 4.5 client installer will perform an upgrade of the existing client using the existing installation folder.</span></span>

 

<span data-ttu-id="0ffb0-115">\ [テンプレートトークンの値 \]</span><span class="sxs-lookup"><span data-stu-id="0ffb0-115">\[Template Token Value\]</span></span>

<span data-ttu-id="0ffb0-116">**注** App-v バージョン4.6 以降の場合、App-v クライアントをインストールすると、SFTLDR.DLL が Windows\\system32 ディレクトリにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="0ffb0-116">**Note** For App-V version4.6 and later, when the App-V client is installed, SFTLDR.DLL is copied to the Windows\\system32 directory.</span></span> <span data-ttu-id="0ffb0-117">App-v クライアントが64ビットシステムにインストールされている場合、SFTLDR\_WOW64.DLL は Windows\\SysWOW64 ディレクトリにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="0ffb0-117">If the App-V client is installed on a 64-bit system, SFTLDR\_WOW64.DLL is copied to the Windows\\SysWOW64 directory.</span></span>

 

<span data-ttu-id="0ffb0-118">\ [テンプレートトークンの値 \]</span><span class="sxs-lookup"><span data-stu-id="0ffb0-118">\[Template Token Value\]</span></span>

## <span data-ttu-id="0ffb0-119">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0ffb0-119">In This Section</span></span>


<span data-ttu-id="0ffb0-120">次のトピックでは、setup.exe または setup.msi を使って、Application Virtualization (App-v) デスクトップクライアントまたはリモートデスクトップサービス (旧ターミナルサービス) の App-v クライアントのいずれかをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0ffb0-120">The following topics describe how to install either the Application Virtualization (App-V) Desktop Client or the App-V Client for Remote Desktop Services (formerly Terminal Services) by using either setup.exe or setup.msi.</span></span>

<a href="" id="how-to-install-the-app-v-client-by-using-setup-exe"></a>[<span data-ttu-id="0ffb0-121">setup.exe を使用して App-V Client をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="0ffb0-121">How to Install the App-V Client by Using Setup.exe</span></span>](how-to-install-the-app-v-client-by-using-setupexe-new.md)  
<span data-ttu-id="0ffb0-122">setup.exe プログラムを使用して、App-v クライアントをインストールするための詳しい手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="0ffb0-122">Provides a step-by-step procedure for installing the App-V client by using the setup.exe program.</span></span>

<a href="" id="how-to-install-the-app-v-client-by-using-setup-msi"></a>[<span data-ttu-id="0ffb0-123">setup.msi を使用して App-V Client をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="0ffb0-123">How to Install the App-V Client by Using Setup.msi</span></span>](how-to-install-the-app-v-client-by-using-setupmsi-new.md)  
<span data-ttu-id="0ffb0-124">setup.msi プログラムを使用して、必要なソフトウェアと App-v クライアントをインストールするための詳しい手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="0ffb0-124">Provides step-by-step procedures for installing any prerequisite software and also the App-V client by using the setup.msi program.</span></span>

## <span data-ttu-id="0ffb0-125">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0ffb0-125">Related topics</span></span>


[<span data-ttu-id="0ffb0-126">Application Virtualization Client インストーラーのコマンド ライン パラメーター</span><span class="sxs-lookup"><span data-stu-id="0ffb0-126">Application Virtualization Client Installer Command-Line Parameters</span></span>](application-virtualization-client-installer-command-line-parameters.md)

[<span data-ttu-id="0ffb0-127">Application Virtualization Client を手動でインストールする方法</span><span class="sxs-lookup"><span data-stu-id="0ffb0-127">How to Manually Install the Application Virtualization Client</span></span>](how-to-manually-install-the-application-virtualization-client.md)

[<span data-ttu-id="0ffb0-128">クライアントで仮想アプリケーションを公開する方法</span><span class="sxs-lookup"><span data-stu-id="0ffb0-128">How to Publish a Virtual Application on the Client</span></span>](how-to-publish-a-virtual-application-on-the-client.md)

[<span data-ttu-id="0ffb0-129">App-V Client をアンインストールする方法</span><span class="sxs-lookup"><span data-stu-id="0ffb0-129">How to Uninstall the App-V Client</span></span>](how-to-uninstall-the-app-v-client.md)

 

 





