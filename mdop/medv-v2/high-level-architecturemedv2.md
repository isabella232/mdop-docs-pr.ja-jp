---
title: アーキテクチャの概要
description: アーキテクチャの概要
author: dansimp
ms.assetid: a00edb9f-207b-4f32-9e8f-522ea2739d2f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8a5db4a56b2abfb0df19b0d6d86f4bf88380c2bf
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827294"
---
# <span data-ttu-id="dadcb-103">アーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="dadcb-103">High-Level Architecture</span></span>


<span data-ttu-id="dadcb-104">このセクションでは、Microsoft Enterprise デスクトップ仮想化 (MED-V) 2.0 の上位レベルのシステムアーキテクチャとコンポーネント設計について説明します。</span><span class="sxs-lookup"><span data-stu-id="dadcb-104">This section describes the high-level system architecture and component design of Microsoft Enterprise Desktop Virtualization (MED-V) 2.0.</span></span>

## <span data-ttu-id="dadcb-105">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="dadcb-105">System Architecture</span></span>


<span data-ttu-id="dadcb-106">MED-V は、1つのデバイスで2つのオペレーティングシステムを実行する、仮想イメージの配信、グループポリシーベースのプロビジョニング、一元管理を実行するために、Windows 仮想 PC を拡張します。</span><span class="sxs-lookup"><span data-stu-id="dadcb-106">MED-V enhances Windows Virtual PC to run two operating systems on one device, adding virtual image delivery, Group Policy-based provisioning, and centralized management.</span></span> <span data-ttu-id="dadcb-107">MED-V を使用することで、windows 7 Professional、Enterprise、または Windows 7 Ultimate を実行している Windows ベースのデスクトップで、企業の Windows 仮想 PC のイメージの構成、展開、管理を簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="dadcb-107">By using MED-V, you can easily configure, deploy, and manage corporate Windows Virtual PC images on any Windows-based desktop running Windows 7 Professional, Enterprise, or Windows 7 Ultimate.</span></span> <span data-ttu-id="dadcb-108">MED-V ソリューションには、次のコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="dadcb-108">The MED-V solution includes the following components:</span></span>

<a href="" id="---------------med-v-host"></a> **<span data-ttu-id="dadcb-109">MED-V ホスト</span><span class="sxs-lookup"><span data-stu-id="dadcb-109">MED-V Host</span></span>**  
<span data-ttu-id="dadcb-110">MED-V Host Agent、電子ソフトウェア配布 (ESD) システム、レジストリ管理システム、および MED-V ゲストが含まれている Windows 7 環境。</span><span class="sxs-lookup"><span data-stu-id="dadcb-110">A Windows 7 environment that includes a MED-V Host Agent, an electronic software distribution (ESD) system, a registry management system, and a MED-V guest.</span></span> <span data-ttu-id="dadcb-111">MED-V ホストは、特定のセットアップ機能とシステム情報を処理できるように、MED-V ゲストと通信します。</span><span class="sxs-lookup"><span data-stu-id="dadcb-111">The MED-V host interacts with the MED-V guest so that certain setup functions and system information can be processed.</span></span>

<a href="" id="-------------------med-v-host-agent"></a> **<span data-ttu-id="dadcb-112">MED-V ホストエージェント</span><span class="sxs-lookup"><span data-stu-id="dadcb-112">MED-V Host Agent</span></span>**  
<span data-ttu-id="dadcb-113">チャネルを提供して、MED-V ゲストと通信する med-v ホストに含まれている med-v ソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="dadcb-113">The MED-V software contained in the MED-V host that provides a channel to communicate with the MED-V guest.</span></span> <span data-ttu-id="dadcb-114">また、初回のセットアップやアプリケーションの公開などの機能も提供されます。</span><span class="sxs-lookup"><span data-stu-id="dadcb-114">It also provides functionality such as first time setup and application publishing.</span></span>

<span data-ttu-id="dadcb-115">**注** MED-V とその必須コンポーネントがインストールされた後、med-v を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dadcb-115">**Note** After MED-V and its required components are installed MED-V must be configured.</span></span> <span data-ttu-id="dadcb-116">MED-V の構成は、初回のセットアップとして参照されます。</span><span class="sxs-lookup"><span data-stu-id="dadcb-116">The configuration of MED-V is referred to as first time setup.</span></span>

 

<a href="" id="esd-system"></a>**<span data-ttu-id="dadcb-117">ESD システム</span><span class="sxs-lookup"><span data-stu-id="dadcb-117">ESD System</span></span>**  
<span data-ttu-id="dadcb-118">MED-V で作成される MED-V ワークスペースパッケージファイルを展開してインストールできる既存のソフトウェア配布方法。</span><span class="sxs-lookup"><span data-stu-id="dadcb-118">Your existing software distribution method that lets you deploy and install the MED-V workspace package files that MED-V creates.</span></span>

<a href="" id="registry-management-system"></a>**<span data-ttu-id="dadcb-119">レジストリ管理システム</span><span class="sxs-lookup"><span data-stu-id="dadcb-119">Registry Management System</span></span>**  
<span data-ttu-id="dadcb-120">既存のグループポリシー設定と基本設定の管理方法。</span><span class="sxs-lookup"><span data-stu-id="dadcb-120">Your existing method of managing Group Policy settings and preferences.</span></span>

<a href="" id="windows-virtual-pc-image"></a>**<span data-ttu-id="dadcb-121">Windows 仮想 PC のイメージ</span><span class="sxs-lookup"><span data-stu-id="dadcb-121">Windows Virtual PC Image</span></span>**  
<span data-ttu-id="dadcb-122">次のコンポーネントが含まれている管理者が定義した仮想マシン。</span><span class="sxs-lookup"><span data-stu-id="dadcb-122">An administrator-defined virtual machine that contains the following components:</span></span>

<a href="" id="corporate-operating-system"></a>**<span data-ttu-id="dadcb-123">企業のオペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="dadcb-123">Corporate Operating System</span></span>**  
<span data-ttu-id="dadcb-124">標準の企業オペレーティングシステム。</span><span class="sxs-lookup"><span data-stu-id="dadcb-124">Your standard corporate operating system.</span></span>

<a href="" id="management-and-security-tools"></a>**<span data-ttu-id="dadcb-125">管理とセキュリティツール</span><span class="sxs-lookup"><span data-stu-id="dadcb-125">Management and Security Tools</span></span>**  
<span data-ttu-id="dadcb-126">ウイルス対策など、標準の管理およびセキュリティツール。</span><span class="sxs-lookup"><span data-stu-id="dadcb-126">Your standard management and security tools, such as virus protection.</span></span>

<a href="" id="-----------------------med-v-guest"></a> **<span data-ttu-id="dadcb-127">MED ゲスト</span><span class="sxs-lookup"><span data-stu-id="dadcb-127">MED-V Guest</span></span>**  
<span data-ttu-id="dadcb-128">Windows XP SP3 環境。 windows 7 上で実行されている windows 仮想 PC の一部として、次のコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="dadcb-128">A Windows XP SP3 environment, as part of a Windows Virtual PC running on Windows 7 that contains the following components:</span></span>

<a href="" id="---------------------------med-v-guest-agent"></a> **<span data-ttu-id="dadcb-129">MED-Hyper-v ゲストエージェント</span><span class="sxs-lookup"><span data-stu-id="dadcb-129">MED-V Guest Agent</span></span>**  
<span data-ttu-id="dadcb-130">Med-v ホストと通信するためのチャネルを提供する、MED-V ゲストに含まれている MED-V ソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="dadcb-130">The MED-V software contained in the MED-V guest that provides a channel to communicate with the MED-V host.</span></span> <span data-ttu-id="dadcb-131">また、初回のセットアップの実行などの機能を備えた MED-V Host Agent もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="dadcb-131">It also supports the MED-V Host Agent with functions like performing first time setup.</span></span>

<span data-ttu-id="dadcb-132">**注** MED-V ゲストエージェントは、初回セットアップ時に自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="dadcb-132">**Note** The MED-V Guest Agent is installed automatically during first time setup.</span></span>

 

<a href="" id="esd-client"></a>**<span data-ttu-id="dadcb-133">ESD クライアント</span><span class="sxs-lookup"><span data-stu-id="dadcb-133">ESD Client</span></span>**  
<span data-ttu-id="dadcb-134">Esd システムの省略可能な部分で、ソフトウェアパッケージをインストールし、ステータスを ESD システムに報告します。</span><span class="sxs-lookup"><span data-stu-id="dadcb-134">An optional part of your ESD system that installs software packages and reports status to the ESD system.</span></span>

## <span data-ttu-id="dadcb-135">関連トピック</span><span class="sxs-lookup"><span data-stu-id="dadcb-135">Related topics</span></span>


[<span data-ttu-id="dadcb-136">アプリケーションのオペレーティング システムの互換性の計画</span><span class="sxs-lookup"><span data-stu-id="dadcb-136">Planning for Application Operating System Compatibility</span></span>](planning-for-application-operating-system-compatibility.md)

[<span data-ttu-id="dadcb-137">MED-V の展開環境を準備する</span><span class="sxs-lookup"><span data-stu-id="dadcb-137">Prepare the Deployment Environment for MED-V</span></span>](prepare-the-deployment-environment-for-med-v.md)

 

 





