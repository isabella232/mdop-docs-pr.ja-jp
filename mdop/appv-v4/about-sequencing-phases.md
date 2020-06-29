---
title: シーケンス フェーズについて
description: シーケンス フェーズについて
author: dansimp
ms.assetid: c1cb7b6c-204c-48f2-848c-4bd5a3d5ecb6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4e3d1504f0af82f3d21806b38bb4640b6f7ebc45
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820004"
---
# <span data-ttu-id="f9dd9-103">シーケンス フェーズについて</span><span class="sxs-lookup"><span data-stu-id="f9dd9-103">About Sequencing Phases</span></span>


<span data-ttu-id="f9dd9-104">シーケンスは、Microsoft Application Virtualization (App-v) Sequencer を使ってシーケンス処理されたアプリケーションパッケージを作成するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="f9dd9-104">Sequencing is the process by which you create a sequenced application package by using the Microsoft Application Virtualization (App-V) Sequencer.</span></span> <span data-ttu-id="f9dd9-105">シーケンス中に、Sequencer はアプリケーションのすべてのインストールとセットアップのプロセスを監視して記録し、次のファイルを作成します。 ICO、OSD、SFT、SPRJ。</span><span class="sxs-lookup"><span data-stu-id="f9dd9-105">During sequencing, the Sequencer monitors and records all installation and setup processes for an application and creates the following files: ICO, OSD, SFT, and SPRJ.</span></span> <span data-ttu-id="f9dd9-106">これらのファイルには、アプリケーションに関する必要な情報がすべて含まれており、仮想環境でそのアプリケーションを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="f9dd9-106">These files contain all the necessary information about an application, and they allow that application to run in a virtual environment.</span></span>

<span data-ttu-id="f9dd9-107">アプリケーションの順序を設定し、仮想アプリケーションパッケージを作成するには、インストール、起動、カスタマイズ、保存の4つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="f9dd9-107">The four phases to sequencing an application and creating a virtual application package are installation, launch, customization, and save.</span></span> <span data-ttu-id="f9dd9-108">次のリストは、各フェーズに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="f9dd9-108">The following list provides information about each of the phases:</span></span>

1.  <span data-ttu-id="f9dd9-109">**インストールフェーズ**: インストールフェーズでは、パッケージ名と、パッケージに関連付けられるオプションの関連付けられたコメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="f9dd9-109">**Installation phase**—During the installation phase, you specify the package name and an optional associated comment that will be associated with the package.</span></span> <span data-ttu-id="f9dd9-110">このフェーズでは、詳細な監視オプションを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="f9dd9-110">You can also configure advanced monitoring options during this phase.</span></span> <span data-ttu-id="f9dd9-111">詳細な監視オプションには、ブロックサイズの指定や、監視中に自動更新をインストールするかどうかが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f9dd9-111">Advanced monitoring options include specifying the block size and whether you will install automatic updates during monitoring.</span></span> <span data-ttu-id="f9dd9-112">Sequencer は、仮想アプリケーションパッケージの作成に必要なすべての情報と構成を記録し、関連するファイルとレジストリの設定を行います。</span><span class="sxs-lookup"><span data-stu-id="f9dd9-112">The sequencer records all necessary information and configurations required to create a virtual application package and the associated file and registry settings.</span></span>

    <span data-ttu-id="f9dd9-113">**重要** [詳細設定] オプションを表示するには、[**パッケージ情報**] ページの [**高度な監視オプションの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f9dd9-113">**Important** To view the advanced options select **Show Advanced Monitoring Options** on the **Package Information** page.</span></span>

     

2.  <span data-ttu-id="f9dd9-114">**起動フェーズ**: 起動フェーズ中に、パッケージで構成する必要のあるファイルの関連付けとセキュリティ記述子を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f9dd9-114">**Launch phase**—During the launch phase, you can specify any required file associations and security descriptors that should be configured with the package.</span></span> <span data-ttu-id="f9dd9-115">アプリケーションの機能と安定性を確保するために、必要に応じて何度でもアプリケーションを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9dd9-115">You should open the application as many times as necessary to ensure application functionality and stability.</span></span>

3.  <span data-ttu-id="f9dd9-116">**カスタマイズフェーズ**: カスタマイズ段階で、関連付けられている .osd ファイルを使用してパッケージを構成できます。</span><span class="sxs-lookup"><span data-stu-id="f9dd9-116">**Customization phase**—During the customization phase, you can configure your package by using the associated .osd files.</span></span> <span data-ttu-id="f9dd9-117">関連付けられたスクリプトが仮想環境の内部または外部で実行されるかどうかを指定したり、実行する必要のある追加のアクションを指定したり、関連付けられたスクリプトの実行方法 (同期または非同期) を指定したり、ユーザーコンテキストで実行する必要のある追加スクリプトを指定したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="f9dd9-117">You can specify whether any associated scripts should run inside or outside of the virtual environment, specify additional actions that should be performed, specify how associated scripts run (synchronously or asynchronously), and specify any additional scripts that should be run under the user context.</span></span>

4.  <span data-ttu-id="f9dd9-118">**保存フェーズ**: 保存フェーズ中に、仮想アプリケーションパッケージに必要なすべてのファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f9dd9-118">**Save phase**—During the save phase, all required files for the virtual application package are created.</span></span> <span data-ttu-id="f9dd9-119">作成されたファイルは、sprj、sft、.osd、.ico、.xml マニフェスト、Windows installer (.msi) ファイルです。</span><span class="sxs-lookup"><span data-stu-id="f9dd9-119">The files created are .sprj, .sft, .osd, .ico, .xml manifest, and the Windows installer (.msi) file.</span></span>

## <span data-ttu-id="f9dd9-120">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f9dd9-120">Related topics</span></span>


[<span data-ttu-id="f9dd9-121">Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="f9dd9-121">Application Virtualization Sequencer</span></span>](application-virtualization-sequencer.md)

 

 





