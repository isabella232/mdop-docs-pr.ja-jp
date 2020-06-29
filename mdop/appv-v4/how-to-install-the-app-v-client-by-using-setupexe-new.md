---
title: setup.exe を使用して App-V Client をインストールする方法
description: setup.exe を使用して App-V Client をインストールする方法
author: dansimp
ms.assetid: 106a5d97-b5f6-4a16-bf52-a84f4d558c74
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 60f79a2d2f74848ab121ba13cdf8c215088d54db
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817337"
---
# <span data-ttu-id="e82b5-103">setup.exe を使用して App-V Client をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="e82b5-103">How to Install the App-V Client by Using Setup.exe</span></span>


<span data-ttu-id="e82b5-104">このトピックでは、setup.exe プログラムを使用して App-v クライアントをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e82b5-104">This topic describes how to install the App-V client by using the setup.exe program.</span></span> <span data-ttu-id="e82b5-105">setup.exe プログラムを使用して App-v クライアントをインストールすると、必要なソフトウェアがインストーラーによって決定され、クライアントをインストールする前に自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e82b5-105">When you install the App-V client using the setup.exe program, the installer determines which prerequisite software is needed and installs it automatically before it installs the client.</span></span>

**<span data-ttu-id="e82b5-106">Setup.exe を使用して Application Virtualization クライアントをインストールするには</span><span class="sxs-lookup"><span data-stu-id="e82b5-106">To install the Application Virtualization Client by Using Setup.exe</span></span>**

1.  <span data-ttu-id="e82b5-107">コンピューターの管理者権限を持つアカウントでログオンしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e82b5-107">Make sure you are logged on with an account that has administrator rights on the computer.</span></span>

2.  <span data-ttu-id="e82b5-108">コマンドプロンプトウィンドウを開き、ディレクトリをセットアップファイルが格納されているフォルダーに変更します。</span><span class="sxs-lookup"><span data-stu-id="e82b5-108">Open a Command Prompt window, and then change the directory to the folder that contains the setup files.</span></span> <span data-ttu-id="e82b5-109">バージョン4.6 以降バージョンの App-v クライアントをインストールする場合、コンピューターのオペレーティングシステム32ビットまたは64ビットに適切なインストーラーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e82b5-109">When installing version4.6 or a later version of the App-V client, you must use the correct installer for the computer’s operating system, 32-bit or 64-bit.</span></span> <span data-ttu-id="e82b5-110">インストールが失敗し、誤ったインストーラーを使用した場合にエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e82b5-110">The installation will fail and an error message will be displayed if you use the wrong installer.</span></span>

3.  <span data-ttu-id="e82b5-111">コマンドプロンプトで、install コマンド文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="e82b5-111">Enter the install command string at the command prompt.</span></span> <span data-ttu-id="e82b5-112">または、コマンドファイルを作成して、コマンドプロンプトから実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="e82b5-112">Alternatively, you can create a command file and run it from the command prompt.</span></span> <span data-ttu-id="e82b5-113">また、VBScript や Windows PowerShell などのスクリプト言語を使ってコマンドを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="e82b5-113">You can also use a scripting language such as VBScript or Windows PowerShell to run the command.</span></span>

4.  <span data-ttu-id="e82b5-114">次のコマンドラインの例は、いくつかのオプションのパラメーターを使って setup.exe を使う方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e82b5-114">The following command-line example shows how setup.exe can be used with a number of optional parameters.</span></span> <span data-ttu-id="e82b5-115">これらのパラメーターの詳細については、「 [Application Virtualization クライアントインストーラーのコマンドラインパラメーター](application-virtualization-client-installer-command-line-parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e82b5-115">For more information about these parameters, see [Application Virtualization Client Installer Command-Line Parameters](application-virtualization-client-installer-command-line-parameters.md).</span></span>

    **<span data-ttu-id="e82b5-116">"setup.exe"/s/v "/qn SWICACHESIZE = \ \" 10240 \ "System\\" SWIPUBSVRTYPE = \ \ "= \ \" = \ \ "SWIPUBSVRHOST = \ \" PRODSYS\\ "SWIPUBSVRPORT = \ \" SWIPUBSVRDISPLAY "SWIPUBSVRPATH = \ \"/AppVirt/appsntype.xml \ \ "SWIPUBSVRREFRESH = \ \" = \ \ "D:\\AppVirt\\Global\\" SWIUSERDATA = \ \ ""%\\Windows\\Application "Client\\ = \ \" # \ \ "# \ \" @ "</span><span class="sxs-lookup"><span data-stu-id="e82b5-116">"setup.exe" /s /v"/qn SWICACHESIZE=\\"10240\\" SWIPUBSVRDISPLAY=\\"Production System\\" SWIPUBSVRTYPE=\\"HTTP /secure\\" SWIPUBSVRHOST=\\"PRODSYS\\" SWIPUBSVRPORT=\\"443\\" SWIPUBSVRPATH=\\"/AppVirt/appsntype.xml\\" SWIPUBSVRREFRESH=\\"on\\" SWIGLOBALDATA=\\"D:\\AppVirt\\Global\\" SWIUSERDATA=\\"^% LOCALAPPDATA ^%\\Windows\\Application Virtualization Client\\" SWIFSDRIVE=\\"Q\\""</span></span>**

    **<span data-ttu-id="e82b5-117">重要</span><span class="sxs-lookup"><span data-stu-id="e82b5-117">Important</span></span>**  
    -   <span data-ttu-id="e82b5-118">"**/V**" セクションに表示される引用符は、特殊文字として扱われ、前に "" が付いて入力されている必要があり **\\** ます。</span><span class="sxs-lookup"><span data-stu-id="e82b5-118">The quotation marks that appear in the "**/v**" section must be treated as special characters and entered with a preceding "**\\**".</span></span> <span data-ttu-id="e82b5-119">引用符は、値にスペースが含まれている場合にのみ必要です。ただし、一貫性を保つため、前の例のすべてのインスタンスは引用符で囲まれています。</span><span class="sxs-lookup"><span data-stu-id="e82b5-119">The quotation marks are required only when the value contains a space; however, for consistency, all the instances in the preceding example are shown as having quotation marks.</span></span>

    -   <span data-ttu-id="e82b5-120">" **%** **% HomeDrive%**" の "" 文字の前には "" エスケープ文字を指定する必要があり **^** ます。</span><span class="sxs-lookup"><span data-stu-id="e82b5-120">The "**%**" characters in "**%HomeDrive%**" must be preceded by the "**^**" escape character.</span></span> <span data-ttu-id="e82b5-121">そうしないと、Windows コマンドシェルによって、インストールを実行しているユーザーの値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="e82b5-121">Otherwise, the Windows command shell sets the value to that of the user who is performing the installation.</span></span>

    -   <span data-ttu-id="e82b5-122">この設定をサイレントインストールするには、 **InstallShield**スイッチ **/s**と **/qn**が必要です。</span><span class="sxs-lookup"><span data-stu-id="e82b5-122">The **InstallShield** switches **/s** and **/qn** are needed to make this a silent install.</span></span> <span data-ttu-id="e82b5-123">**/Qn**スイッチ**は、スペース**を入れずに引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="e82b5-123">The **/qn** switch must follow the **/v** switch, separated by only a quote character with no intervening spaces.</span></span>

    -   <span data-ttu-id="e82b5-124">**SWIGLOBALDATA**の値で指定したフォルダーは、既に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="e82b5-124">The folder specified in the **SWIGLOBALDATA** value must already exist.</span></span>

     

5.  <span data-ttu-id="e82b5-125">インストールが完了したら、Microsoft Update スキャンを実行して、最新の更新プログラムがインストールされていることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e82b5-125">When the installation is complete, we recommend that you run a Microsoft Update scan to ensure the latest updates are installed.</span></span>

## <span data-ttu-id="e82b5-126">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e82b5-126">Related topics</span></span>


[<span data-ttu-id="e82b5-127">コマンド ラインを使用してクライアントをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="e82b5-127">How to Install the Client by Using the Command Line</span></span>](how-to-install-the-client-by-using-the-command-line-new.md)

 

 





