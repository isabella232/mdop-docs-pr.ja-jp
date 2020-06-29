---
title: クライアントで仮想アプリケーションを公開する方法
description: クライアントで仮想アプリケーションを公開する方法
author: dansimp
ms.assetid: 90af843e-b5b3-4a71-a3a1-fa5f4c087f28
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b5585f82150db69929ccedbee3aecab969c5e7dc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816874"
---
# <span data-ttu-id="021ff-103">クライアントで仮想アプリケーションを公開する方法</span><span class="sxs-lookup"><span data-stu-id="021ff-103">How to Publish a Virtual Application on the Client</span></span>


<span data-ttu-id="021ff-104">電子ソフトウェア配布システムを使用してアプリケーションの仮想化を展開する場合は、次のいずれかの手順を使用して、アプリケーションパッケージをユーザーに公開することができます。</span><span class="sxs-lookup"><span data-stu-id="021ff-104">When you deploy Application Virtualization by using an electronic software distribution system, you can use one of the following procedures to publish an application package to your users.</span></span>

**<span data-ttu-id="021ff-105">スタンドアロンの Windows インストーラーファイルを使用してパッケージを発行するには</span><span class="sxs-lookup"><span data-stu-id="021ff-105">To publish a package using a stand-alone Windows Installer file</span></span>**

1.  <span data-ttu-id="021ff-106">*Requireauthorizationifcached*パラメーターを 0 (ゼロ) に設定してクライアントをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="021ff-106">The client should be installed with the *REQUIREAUTHORIZATIONIFCACHED* parameter set to 0 (zero).</span></span> <span data-ttu-id="021ff-107">このパラメーターの設定の詳細については、「 [Application Virtualization クライアントインストーラーのコマンドラインパラメーター](application-virtualization-client-installer-command-line-parameters.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="021ff-107">For more information about setting this parameter, see [Application Virtualization Client Installer Command-Line Parameters](application-virtualization-client-installer-command-line-parameters.md)</span></span>

2.  <span data-ttu-id="021ff-108">Windows Installer ファイルと SFT ファイルをターゲットコンピューター上の同じフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="021ff-108">Copy the Windows Installer file and the SFT file to same folder on the target computer.</span></span>

3.  <span data-ttu-id="021ff-109">コンピューターで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="021ff-109">Run the following command on the computer:</span></span>

    `Msiexec.exe /I "packagename.msi" /q`

**<span data-ttu-id="021ff-110">Windows インストーラーとパッケージマニフェストを使ってパッケージを発行するには</span><span class="sxs-lookup"><span data-stu-id="021ff-110">To publish a package using Windows Installer and the package manifest</span></span>**

1.  <span data-ttu-id="021ff-111">ターゲットコンピューターと SFT ファイルを、ストリーミングサーバー上のコンテンツ共有にコピーします。</span><span class="sxs-lookup"><span data-stu-id="021ff-111">Copy the Windows Installer file to the target computer and the SFT file to the CONTENT share on the streaming server.</span></span>

2.  <span data-ttu-id="021ff-112">各ユーザーのコンピューターで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="021ff-112">Run the following command on each user’s computer:</span></span>

    `Msiexec.exe /I "\\pathtomsi\packagename.msi" MODE=STREAMING  OVERRIDEURL="\\\\server\\share\\package.sft" LOAD=TRUE /q`

    <span data-ttu-id="021ff-113">**重要** OVERRIDEURL の場合、バックスラッシュ文字の前にバックスラッシュを使用してエスケープするか、上書き URL パスが正しく解析されないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="021ff-113">**Important** For OVERRIDEURL all backslash characters must be escaped using a preceding backslash, or the OVERRIDEURL path will not be parsed correctly.</span></span> <span data-ttu-id="021ff-114">また、値がファイルへのパスである場合を除き、プロパティと値は大文字で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="021ff-114">Also, properties and values must be entered as uppercase except where the value is a path to a file.</span></span>

     

**<span data-ttu-id="021ff-115">SFTMIME を使用してパッケージを発行するには</span><span class="sxs-lookup"><span data-stu-id="021ff-115">To publish a package using SFTMIME</span></span>**

-   <span data-ttu-id="021ff-116">コンピューター上のすべてのユーザーに対してアプリケーションを公開する方法の例については、ユーザーのコンピューターで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="021ff-116">For an example of how to publish an application for all users on a computer, run the following command on the user’s computer:</span></span>

    `SFTMIME ADD PACKAGE:package-name /MANIFEST manifest-path                                 [/GLOBAL] [/LOG log-pathname | /CONSOLE | /GUI]`

    <span data-ttu-id="021ff-117">このようなその他の SFTMIME コマンドの詳細については、「 [Sftmime コマンドのリファレンス](sftmime--command-reference.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="021ff-117">For additional details about these and other SFTMIME commands, see [SFTMIME Command Reference](sftmime--command-reference.md).</span></span>

## <span data-ttu-id="021ff-118">関連トピック</span><span class="sxs-lookup"><span data-stu-id="021ff-118">Related topics</span></span>


[<span data-ttu-id="021ff-119">公開方法の選択</span><span class="sxs-lookup"><span data-stu-id="021ff-119">Determine Your Publishing Method</span></span>](determine-your-publishing-method.md)

[<span data-ttu-id="021ff-120">電子ソフトウェア配布ベースのシナリオ</span><span class="sxs-lookup"><span data-stu-id="021ff-120">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="021ff-121">SFTMIME コマンドリファレンス</span><span class="sxs-lookup"><span data-stu-id="021ff-121">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

[<span data-ttu-id="021ff-122">Application Virtualization Client のスタンドアロン配信シナリオ</span><span class="sxs-lookup"><span data-stu-id="021ff-122">Stand-Alone Delivery Scenario for Application Virtualization Clients</span></span>](stand-alone-delivery-scenario-for-application-virtualization-clients.md)

 

 





