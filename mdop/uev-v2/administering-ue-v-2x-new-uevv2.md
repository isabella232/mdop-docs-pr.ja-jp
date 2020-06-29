---
title: UE-V 2. x の管理
description: UE-V 2. x の管理
author: dansimp
ms.assetid: 996e4797-8383-4627-b714-24a84c907798
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2674f6ace80672c1e89bb4f9c765b56f260c3bc0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825674"
---
# <span data-ttu-id="1c57e-103">UE-V 2. x の管理</span><span class="sxs-lookup"><span data-stu-id="1c57e-103">Administering UE-V 2.x</span></span>


<span data-ttu-id="1c57e-104">Microsoft User Experience Virtualization (UE-V) 2.0、2.1、または 2.1 SP1 を展開した後、UE-V Agent の構成の管理や消失した設定の回復など、さまざまな管理タスクを実行できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c57e-104">After you have deployed Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, or 2.1 SP1, you must be able to perform various ongoing administrative tasks, such as managing the configuration of the UE-V Agent and recovering lost settings.</span></span> <span data-ttu-id="1c57e-105">これらのインストール後のタスクについては、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="1c57e-105">These post-installation tasks are described in the following sections.</span></span>

## <span data-ttu-id="1c57e-106">UE-V 2 .x 構成の管理</span><span class="sxs-lookup"><span data-stu-id="1c57e-106">Managing UE-V 2.x configurations</span></span>


<span data-ttu-id="1c57e-107">UE-V のライフサイクルでは、UE-V Agent の構成を管理する必要があります。また、設定パッケージファイルなどのリソースの保存場所を管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c57e-107">In the course of the UE-V lifecycle, you have to manage the configuration of the UE-V Agent and also manage storage locations for resources such as settings package files.</span></span>

[<span data-ttu-id="1c57e-108">UE-V 2.x の構成を管理する</span><span class="sxs-lookup"><span data-stu-id="1c57e-108">Manage Configurations for UE-V 2.x</span></span>](manage-configurations-for-ue-v-2x-new-uevv2.md)

## <span data-ttu-id="1c57e-109">カスタム UE-V テンプレートと UE-V Generator を使って作業する</span><span class="sxs-lookup"><span data-stu-id="1c57e-109">Working with custom UE-V templates and the UE-V 2.x Generator</span></span>


<span data-ttu-id="1c57e-110">このトピックでは、UE-V Generator を使用してカスタム設定の場所テンプレートを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1c57e-110">This topic provides instructions for how to use the UE-V Generator and manage custom settings location templates.</span></span>

[<span data-ttu-id="1c57e-111">カスタム ue-v (ue-v) テンプレートと UE-V Generator を使って作業する</span><span class="sxs-lookup"><span data-stu-id="1c57e-111">Working with Custom UE-V 2.x Templates and the UE-V 2.x Generator</span></span>](working-with-custom-ue-v-2x-templates-and-the-ue-v-2x-generator-new-uevv2.md)

## <span data-ttu-id="1c57e-112">UE-V 2. x と同期されたアプリケーションと Windows の設定のバックアップと復元を行います。</span><span class="sxs-lookup"><span data-stu-id="1c57e-112">Backup and restore application and Windows settings that are synchronized with UE-V 2.x</span></span>


<span data-ttu-id="1c57e-113">UE-V の windows Management Instrumentation (WMI) 機能と Windows PowerShell 機能により、設定パッケージを復元することができます。</span><span class="sxs-lookup"><span data-stu-id="1c57e-113">Windows Management Instrumentation (WMI) and Windows PowerShell features of UE-V provide the ability to restore settings packages.</span></span> <span data-ttu-id="1c57e-114">WMI コマンドと Windows PowerShell コマンドを使用すると、アプリケーションと Windows の設定を元の状態に復元し、ユーザーが新しいデバイスを採用したときに追加の設定を復元することができます。</span><span class="sxs-lookup"><span data-stu-id="1c57e-114">By using WMI and Windows PowerShell commands, you can restore application and Windows settings to their original state and restore additional settings when a user adopts a new device.</span></span>

[<span data-ttu-id="1c57e-115">UE-V 2. x で管理バックアップと復元を管理する</span><span class="sxs-lookup"><span data-stu-id="1c57e-115">Manage Administrative Backup and Restore in UE-V 2.x</span></span>](manage-administrative-backup-and-restore-in-ue-v-2x-new-topic-for-21.md)

## <span data-ttu-id="1c57e-116">UE-V 2. x のスケジュールされたタスクの頻度の変更</span><span class="sxs-lookup"><span data-stu-id="1c57e-116">Changing the frequency of UE-V 2.x scheduled tasks</span></span>


<span data-ttu-id="1c57e-117">UE-V が新規または更新された設定をチェックするとき、または設定テンプレートカタログで更新されたカスタム設定の場所テンプレートを管理するスケジュールされたタスクを構成できます。</span><span class="sxs-lookup"><span data-stu-id="1c57e-117">You can configure the scheduled tasks that manage when UE-V checks for new or updated settings or for updated custom settings location templates in the settings template catalog.</span></span>

[<span data-ttu-id="1c57e-118">UE-V 2. x のスケジュールされたタスクの頻度の変更</span><span class="sxs-lookup"><span data-stu-id="1c57e-118">Changing the Frequency of UE-V 2.x Scheduled Tasks</span></span>](changing-the-frequency-of-ue-v-2x-scheduled-tasks-both-uevv2.md)

## <span data-ttu-id="1c57e-119">UE-V の設定パッケージを移行する</span><span class="sxs-lookup"><span data-stu-id="1c57e-119">Migrating UE-V 2.x settings packages</span></span>


<span data-ttu-id="1c57e-120">ユーザー設定パッケージは、新しいサーバーに移行するか、バックアップ目的で再配置することができます。</span><span class="sxs-lookup"><span data-stu-id="1c57e-120">You can relocate the user settings packages either when they migrate to a new server or for backup purposes.</span></span>

[<span data-ttu-id="1c57e-121">UE-V の設定パッケージを移行する</span><span class="sxs-lookup"><span data-stu-id="1c57e-121">Migrating UE-V 2.x Settings Packages</span></span>](migrating-ue-v-2x-settings-packages-both-uevv2.md)

## <span data-ttu-id="1c57e-122">アプリケーションの仮想化アプリケーションで UE-V を使用する</span><span class="sxs-lookup"><span data-stu-id="1c57e-122">Using UE-V 2.x with Application Virtualization applications</span></span>


<span data-ttu-id="1c57e-123">Microsoft Application Virtualization (App-v) と UE-V を使用して、複数のコンピューター間で仮想アプリケーションとインストールされているアプリケーションの間で設定を共有することができます。</span><span class="sxs-lookup"><span data-stu-id="1c57e-123">You can use UE-V with Microsoft Application Virtualization (App-V) to share settings between virtual applications and installed applications across multiple computers.</span></span>

[<span data-ttu-id="1c57e-124">アプリケーションの仮想化アプリケーションで UE-V を使用する</span><span class="sxs-lookup"><span data-stu-id="1c57e-124">Using UE-V 2.x with Application Virtualization Applications</span></span>](using-ue-v-2x-with-application-virtualization-applications-both-uevv2.md)

## <span data-ttu-id="1c57e-125">この製品のその他のリソース</span><span class="sxs-lookup"><span data-stu-id="1c57e-125">Other resources for this product</span></span>


-   [<span data-ttu-id="1c57e-126">Microsoft User Experience Virtualization (UE-V) 2. x</span><span class="sxs-lookup"><span data-stu-id="1c57e-126">Microsoft User Experience Virtualization (UE-V) 2.x</span></span>](index.md)

-   [<span data-ttu-id="1c57e-127">UE-V 2.x の概要</span><span class="sxs-lookup"><span data-stu-id="1c57e-127">Get Started with UE-V 2.x</span></span>](get-started-with-ue-v-2x-new-uevv2.md)

-   [<span data-ttu-id="1c57e-128">UE-V の展開を準備する</span><span class="sxs-lookup"><span data-stu-id="1c57e-128">Prepare a UE-V 2.x Deployment</span></span>](prepare-a-ue-v-2x-deployment-new-uevv2.md)

-   [<span data-ttu-id="1c57e-129">UE-V 2. x のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="1c57e-129">Troubleshooting UE-V 2.x</span></span>](troubleshooting-ue-v-2x-both-uevv2.md)

-   [<span data-ttu-id="1c57e-130">UE-V 2.x のテクニカル リファレンス</span><span class="sxs-lookup"><span data-stu-id="1c57e-130">Technical Reference for UE-V 2.x</span></span>](technical-reference-for-ue-v-2x-both-uevv2.md)






 

 





