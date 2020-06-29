---
title: インストールの前提条件を構成する
description: インストールの前提条件を構成する
author: dansimp
ms.assetid: ff9cf28a-3eac-4b6c-8ce9-bfc202f57947
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 6cd9379804c45a2025064a6eecf363c010980369
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819307"
---
# <span data-ttu-id="e65f6-103">インストールの前提条件を構成する</span><span class="sxs-lookup"><span data-stu-id="e65f6-103">Configure Installation Prerequisites</span></span>


<span data-ttu-id="e65f6-104">次の手順は、Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 をインストールして使用するための前提条件です。</span><span class="sxs-lookup"><span data-stu-id="e65f6-104">The following instructions are prerequisites for installing and using Microsoft Enterprise Desktop Virtualization (MED-V) 2.0:</span></span>

[<span data-ttu-id="e65f6-105">Windows 仮想 PC</span><span class="sxs-lookup"><span data-stu-id="e65f6-105">Windows Virtual PC</span></span>](#bkmk-howtoinstallandconfiguremicrosoftvirtualpc7)

[<span data-ttu-id="e65f6-106">Windows 仮想 PC の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="e65f6-106">Windows Virtual PC Update</span></span>](#bkmk-howtoinstallandconfiguremicrosoftvirtualpc7update)

[<span data-ttu-id="e65f6-107">ウイルス対策/バックアップソフトウェアの構成</span><span class="sxs-lookup"><span data-stu-id="e65f6-107">Antivirus/Backup Software Configuration</span></span>](#bkmk-antivirusbackupsoftwareconfiguration)

## <a href="" id="bkmk-howtoinstallandconfiguremicrosoftvirtualpc7"></a><span data-ttu-id="e65f6-108">Windows 仮想 PC をインストールして構成する方法</span><span class="sxs-lookup"><span data-stu-id="e65f6-108">How to Install and Configure Windows Virtual PC</span></span>


<span data-ttu-id="e65f6-109">**重要** Windows 版の Virtual PC がホストコンピューターに既に存在する場合は、Windows Virtual PC をインストールする前にアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e65f6-109">**Important** If a version of Virtual PC for Windows already exists on the host computer, you must uninstall it before you install Windows Virtual PC.</span></span>

 

**<span data-ttu-id="e65f6-110">Windows 仮想 PC をインストールするには</span><span class="sxs-lookup"><span data-stu-id="e65f6-110">To install Windows Virtual PC</span></span>**

1.  <span data-ttu-id="e65f6-111">Microsoft ダウンロードセンター () から[Windows VIRTUAL PC](https://go.microsoft.com/fwlink/?LinkId=195918)をダウンロードし https://go.microsoft.com/fwlink/?LinkId=195918) ます。</span><span class="sxs-lookup"><span data-stu-id="e65f6-111">Download [Windows Virtual PC](https://go.microsoft.com/fwlink/?LinkId=195918) from the Microsoft Download Center (https://go.microsoft.com/fwlink/?LinkId=195918).</span></span>

2.  <span data-ttu-id="e65f6-112">ホストコンピューターでインストールファイルを実行して、ウィザードの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e65f6-112">Run the installation file on the host computer, and follow the steps in the wizard.</span></span>

<span data-ttu-id="e65f6-113">**重要** Windows 仮想 PC には、仮想環境と物理コンピューターの間の操作を改善する機能を提供する統合コンポーネントパッケージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e65f6-113">**Important** Windows Virtual PC includes the Integration Components package, which provides features that improve the interaction between the virtual environment and the physical computer.</span></span> <span data-ttu-id="e65f6-114">たとえば、ホストとゲストコンピューターの間でマウスを移動できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e65f6-114">For example, it lets your mouse move between the host and the guest computers.</span></span> <span data-ttu-id="e65f6-115">MED では、統合コンポーネントパッケージをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e65f6-115">MED-V requires the installation of the Integration Components package.</span></span>

 

## <a href="" id="bkmk-howtoinstallandconfiguremicrosoftvirtualpc7update"></a><span data-ttu-id="e65f6-116">Windows 仮想 PC の更新プログラムをインストールして構成する方法</span><span class="sxs-lookup"><span data-stu-id="e65f6-116">How to Install and Configure the Windows Virtual PC Update</span></span>


<span data-ttu-id="e65f6-117">KB977206 に関連付けられている Microsoft update により、ハードウェア支援による仮想化 (HAV) テクノロジを備えていないコンピューターで Windows XP モードが有効になります。</span><span class="sxs-lookup"><span data-stu-id="e65f6-117">The Microsoft update associated with article KB977206 enables Windows XP Mode for computers without hardware-assisted virtualization (HAV) technology.</span></span> <span data-ttu-id="e65f6-118">ゲストオペレーティングシステムの統合コンポーネントパッケージが、ホストコンピューターにインストールされている Windows 仮想 PC のバージョンと一致しない場合、一部の統合機能が正しく動作しない可能性があるため、この更新プログラムをインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e65f6-118">We recommended that you install this update because some integration features might not work correctly if the Integration Components package in the guest operating system do not match the version of Windows Virtual PC that is installed on the host computer.</span></span>

<span data-ttu-id="e65f6-119">**重要** Windows 7 と Service Pack 1 を実行しているホストコンピューターに MED-V をインストールする場合は、この更新プログラムをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e65f6-119">**Important** You do not have to install this update when you are installing MED-V on host computers that are running Windows 7 with Service Pack 1.</span></span>

 

<span data-ttu-id="e65f6-120">**ヒント** ここに記載されている更新に加えて、使用可能なすべての Windows 仮想 PC 更新プログラムを確認して、環境に適した、または必要な更新プログラムを適用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e65f6-120">**Tip** In addition to the update listed here, we recommend that you review all available Windows Virtual PC updates and apply those updates that are appropriate or necessary for your environment.</span></span>

 

**<span data-ttu-id="e65f6-121">Windows 仮想 PC の更新プログラムをインストールするには</span><span class="sxs-lookup"><span data-stu-id="e65f6-121">To install the Windows Virtual PC Update</span></span>**

1.  <span data-ttu-id="e65f6-122">Microsoft ダウンロードセンターから、必要な Windows 仮想 PC の更新プログラムをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e65f6-122">Download the required Windows Virtual PC update from the Microsoft Download Center.</span></span>

    <span data-ttu-id="e65f6-123">[32 ビット更新プログラム](https://go.microsoft.com/fwlink/?LinkId=195919)( https://go.microsoft.com/fwlink/?LinkId=195919) .</span><span class="sxs-lookup"><span data-stu-id="e65f6-123">[32-bit Update](https://go.microsoft.com/fwlink/?LinkId=195919) (https://go.microsoft.com/fwlink/?LinkId=195919).</span></span>

    <span data-ttu-id="e65f6-124">[64 ビット更新プログラム](https://go.microsoft.com/fwlink/?LinkId=195920)( https://go.microsoft.com/fwlink/?LinkId=195920) .</span><span class="sxs-lookup"><span data-stu-id="e65f6-124">[64-bit Update](https://go.microsoft.com/fwlink/?LinkId=195920) (https://go.microsoft.com/fwlink/?LinkId=195920).</span></span>

2.  <span data-ttu-id="e65f6-125">ホストコンピューターで管理者モードでインストールファイルを実行し、ウィザードの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e65f6-125">Run the installation file on the host computer in elevated mode, and follow the steps in the wizard.</span></span>

    <span data-ttu-id="e65f6-126">Windows 仮想 PC の修正プログラムパッケージの詳細については、[記事 977206](https://go.microsoft.com/fwlink/?LinkId=195921) () を参照してください https://go.microsoft.com/fwlink/?LinkId=195921) 。</span><span class="sxs-lookup"><span data-stu-id="e65f6-126">For more information about the hotfix package for Windows Virtual PC, see [article 977206](https://go.microsoft.com/fwlink/?LinkId=195921) (https://go.microsoft.com/fwlink/?LinkId=195921).</span></span>

## <a href="" id="bkmk-antivirusbackupsoftwareconfiguration"></a><span data-ttu-id="e65f6-127">ウイルス対策/バックアップソフトウェアを構成する方法</span><span class="sxs-lookup"><span data-stu-id="e65f6-127">How to Configure Antivirus/Backup Software</span></span>


<span data-ttu-id="e65f6-128">ウイルス対策によって仮想デスクトップのパフォーマンスが影響を受けないようにするには、ホストコンピューター上で実行されている任意のウイルス対策またはバックアッププロセスから、次の仮想マシンのファイルの種類を除外することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e65f6-128">To prevent antivirus activity from affecting the performance of the virtual desktop, we recommend, where you can, to exclude the following virtual machine file types from any antivirus or backup process that is running on the host computer:</span></span>

-   <span data-ttu-id="e65f6-129">\*..VMC</span><span class="sxs-lookup"><span data-stu-id="e65f6-129">\*.VMC</span></span>

-   <span data-ttu-id="e65f6-130">\*.VUD</span><span class="sxs-lookup"><span data-stu-id="e65f6-130">\*.VUD</span></span>

-   <span data-ttu-id="e65f6-131">\*.VSV</span><span class="sxs-lookup"><span data-stu-id="e65f6-131">\*.VSV</span></span>

-   <span data-ttu-id="e65f6-132">\*.VHD</span><span class="sxs-lookup"><span data-stu-id="e65f6-132">\*.VHD</span></span>

## <span data-ttu-id="e65f6-133">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e65f6-133">Related topics</span></span>


[<span data-ttu-id="e65f6-134">環境の前提条件を構成する</span><span class="sxs-lookup"><span data-stu-id="e65f6-134">Configure Environment Prerequisites</span></span>](configure-environment-prerequisites.md)

[<span data-ttu-id="e65f6-135">アーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="e65f6-135">High-Level Architecture</span></span>](high-level-architecturemedv2.md)

[<span data-ttu-id="e65f6-136">MED-V 2.0 でサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="e65f6-136">MED-V 2.0 Supported Configurations</span></span>](med-v-20-supported-configurations.md)

 

 





