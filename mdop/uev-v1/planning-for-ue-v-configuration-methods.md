---
title: UE-V の構成方法の計画
description: UE-V の構成方法の計画
author: dansimp
ms.assetid: 57bce7ab-1be5-434b-9ee5-c96026bbe010
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4894644d72392ae984d0de290bf634e137d5b85e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827094"
---
# <span data-ttu-id="5cb9f-103">UE-V の構成方法の計画</span><span class="sxs-lookup"><span data-stu-id="5cb9f-103">Planning for UE-V Configuration Methods</span></span>


<span data-ttu-id="5cb9f-104">Microsoft User Experience Virtualization (UE-V) の構成によって、設定が企業全体でどのように同期されるかが決まります。</span><span class="sxs-lookup"><span data-stu-id="5cb9f-104">Microsoft User Experience Virtualization (UE-V) configurations determine how settings are synchronized throughout the enterprise.</span></span> <span data-ttu-id="5cb9f-105">このトピックでは、お客様のビジネス要件に最も適した構成計画を策定するための UE-V 構成の作成方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5cb9f-105">This topic describes how UE-V configurations are created to help you formulate a configuration plan that best meets your business requirements.</span></span>

## <span data-ttu-id="5cb9f-106">UE-V の構成方法</span><span class="sxs-lookup"><span data-stu-id="5cb9f-106">Configuration methods for UE-V</span></span>


<span data-ttu-id="5cb9f-107">使用している構成方法によっては、エージェントのインストールの前、最中、またはインストール後に UE-V を構成できます。</span><span class="sxs-lookup"><span data-stu-id="5cb9f-107">You can configure UE-V before, during, or after agent installation, depending on the configuration method that you use.</span></span>

<span data-ttu-id="5cb9f-108">**グループポリシー:** 既存のグループポリシーインフラストラクチャを使用して、ue-v エージェントの展開前または後の ue-v の構成を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5cb9f-108">**Group Policy:** existing Group Policy infrastructure can be used to configure UE-V before or after UE-V Agent deployment.</span></span> <span data-ttu-id="5cb9f-109">UE-V は、ue-v Agent の一般的な構成オプションの一元管理を有効にし、ue-v の同期を構成するための設定も含まれています。</span><span class="sxs-lookup"><span data-stu-id="5cb9f-109">The UE-V ADMX template enables the central management of common UE-V Agent configuration options, and it includes settings to configure UE-V synchronization.</span></span> <span data-ttu-id="5cb9f-110">グループポリシーを使用するネットワーク環境では、エージェントの展開を見越して UE-V を事前に構成することができます。</span><span class="sxs-lookup"><span data-stu-id="5cb9f-110">Network environments that use Group Policy can preconfigure UE-V in anticipation of agent deployment.</span></span>

[<span data-ttu-id="5cb9f-111">グループ ポリシー オブジェクトを使用した UE-V の構成</span><span class="sxs-lookup"><span data-stu-id="5cb9f-111">Configuring UE-V with Group Policy Objects</span></span>](configuring-ue-v-with-group-policy-objects.md)

[<span data-ttu-id="5cb9f-112">UE-V グループ ポリシー ADMX テンプレートのインストール</span><span class="sxs-lookup"><span data-stu-id="5cb9f-112">Installing the UE-V Group Policy ADMX Templates</span></span>](installing-the-ue-v-group-policy-admx-templates.md)

<span data-ttu-id="5cb9f-113">**コマンドラインまたはバッチスクリプトのインストール:** ue-v Agent の展開で使用されるパラメーターによって、多数の ue-v 設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="5cb9f-113">**Command-line or Batch Script Installation:** parameters that are used with the deployment of the UE-V Agent allow the configuration of many UE-V settings.</span></span> <span data-ttu-id="5cb9f-114">System Center Configuration Manager などの電子ソフトウェア配布システムでは、UE-V Agent ソフトウェアの展開とインストール時にこれらのパラメーターを使ってクライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="5cb9f-114">Electronic software distribution systems, such as System Center Configuration Manager, use these parameters to configure their clients when deploying and installing the UE-V Agent software.</span></span> <span data-ttu-id="5cb9f-115">インストールパラメーターの一覧とインストールスクリプトの例については、「 [Ue-v agent の展開](deploying-the-ue-v-agent.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5cb9f-115">For a list of installation parameters and sample installation scripts, see [Deploying the UE-V Agent](deploying-the-ue-v-agent.md).</span></span>

<span data-ttu-id="5cb9f-116">**Powershell と wmi:** ue-v エージェントがインストールされた後に、powershell または wmi を使用してスクリプトコマンドを使用して構成を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="5cb9f-116">**PowerShell and WMI:** scripted commands using PowerShell or WMI can be used to modify configurations after the UE-V Agent has been installed.</span></span> <span data-ttu-id="5cb9f-117">PowerShell コマンドと WMI コマンドの一覧については、「 [ue-v 1.0 エージェントと powershell と wmi を使ったパッケージの管理](managing-the-ue-v-10-agent-and-packages-with-powershell-and-wmi.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cb9f-117">For a list of PowerShell and WMI commands, see [Managing the UE-V 1.0 Agent and Packages with PowerShell and WMI](managing-the-ue-v-10-agent-and-packages-with-powershell-and-wmi.md).</span></span>

<span data-ttu-id="5cb9f-118">**レジストリ設定を編集します。** UE-V の設定はレジストリに格納され、レジストリ設定を変更できる任意のツール (RegEdit など) を使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="5cb9f-118">**Edit Registry Settings:** UE-V settings are stored in the registry and can be modified by using any tool that can modify registry settings, such as RegEdit.</span></span>

<span data-ttu-id="5cb9f-119">**注** レジストリを変更すると、データが失われるか、コンピューターが応答しなくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="5cb9f-119">**Note** Registry modification can result in data loss or the computer becoming unresponsive.</span></span> <span data-ttu-id="5cb9f-120">他の構成方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5cb9f-120">We recommend that you use other configuration methods.</span></span>

 

### <span data-ttu-id="5cb9f-121">UE-V 構成の設定</span><span class="sxs-lookup"><span data-stu-id="5cb9f-121">UE-V configuration settings</span></span>

<span data-ttu-id="5cb9f-122">UE-V の構成設定の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5cb9f-122">The following are examples of UE-V configuration settings:</span></span>

-   <span data-ttu-id="5cb9f-123">[**記憶域のパスの設定]:** ue-v の設定を保存するファイル共有の場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="5cb9f-123">**Setting Storage Path:** specifies the location of the file share that stores the UE-V settings.</span></span>

-   <span data-ttu-id="5cb9f-124">**設定テンプレートカタログのパス:** 新しい設定場所テンプレートがチェックされた場所を定義する汎用名前付け規則 (UNC) パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="5cb9f-124">**Settings Template Catalog Path:** specifies the Universal Naming Convention (UNC) path that defines the location that was checked for new settings location templates.</span></span>

-   <span data-ttu-id="5cb9f-125">**Microsoft テンプレートの登録:** インストール時に既定の Microsoft テンプレートを登録するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5cb9f-125">**Register Microsoft Templates:** specifies whether the default Microsoft templates should be registered during installation.</span></span>

-   <span data-ttu-id="5cb9f-126">**同期方法:** Windows オフラインファイル機能がオフラインサポートに使用されるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5cb9f-126">**Synchronization Method:** specifies whether the Windows Offline Files feature is used for offline support.</span></span>

-   <span data-ttu-id="5cb9f-127">**同期タイムアウト:** 設定の保存場所からユーザー設定を取得するときにコンピューターがタイムアウトするまでの時間 (ミリ秒単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="5cb9f-127">**Synchronization Timeout:** specifies the number of milliseconds that the computer waits before timeout when retrieving the user settings from the settings storage location.</span></span>

-   <span data-ttu-id="5cb9f-128">**同期有効:** ue-v 設定の同期を有効にするか無効にするかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5cb9f-128">**Synchronization Enable:** specifies whether the UE-V settings synchronization is enabled or disabled.</span></span>

-   <span data-ttu-id="5cb9f-129">[**パッケージの最大サイズ]:** ue-v agent が警告を報告する設定パッケージファイルのしきい値のサイズ (バイト単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="5cb9f-129">**Maximum Package Size:** specifies a settings package file threshold size in bytes at which the UE-V Agent reports a warning.</span></span>

## <span data-ttu-id="5cb9f-130">関連トピック</span><span class="sxs-lookup"><span data-stu-id="5cb9f-130">Related topics</span></span>


[<span data-ttu-id="5cb9f-131">UE-V 1.0 の計画</span><span class="sxs-lookup"><span data-stu-id="5cb9f-131">Planning for UE-V 1.0</span></span>](planning-for-ue-v-10.md)

[<span data-ttu-id="5cb9f-132">UE-V の構成計画</span><span class="sxs-lookup"><span data-stu-id="5cb9f-132">Planning for UE-V Configuration</span></span>](planning-for-ue-v-configuration.md)

 

 





