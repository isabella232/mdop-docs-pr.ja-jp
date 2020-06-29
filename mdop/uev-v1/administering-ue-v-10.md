---
title: UE-V 1.0 の管理
description: UE-V 1.0 の管理
author: dansimp
ms.assetid: c399ae8d-c839-4f84-9bfc-adacd8f89f34
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ce4dcafd1949dcedd195569dabb7540ce55a2f1a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822697"
---
# <span data-ttu-id="db256-103">UE-V 1.0 の管理</span><span class="sxs-lookup"><span data-stu-id="db256-103">Administering UE-V 1.0</span></span>


<span data-ttu-id="db256-104">Microsoft User Experience Virtualization (UE-V) を展開した後、さまざまな進行中の管理タスクを実行できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="db256-104">After you have deployed Microsoft User Experience Virtualization (UE-V), you must be able to perform various ongoing administrative tasks.</span></span> <span data-ttu-id="db256-105">これらのインストール後のタスクについては、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="db256-105">These post-installation tasks are described in the following sections.</span></span>

## <span data-ttu-id="db256-106">UE-V リソースの管理</span><span class="sxs-lookup"><span data-stu-id="db256-106">Managing UE-V resources</span></span>


<span data-ttu-id="db256-107">UE-V のライフサイクルでは、UE-V agent の構成を管理する必要があります。また、設定パッケージなどのリソースの保存場所を管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db256-107">In the course of the UE-V lifecycle, you will need to manage the configuration of the UE-V agent and also manage storage locations for resources such as settings packages.</span></span> <span data-ttu-id="db256-108">紛失した設定を回復するために、UE-V をインストールする前に、ユーザーの設定を元の状態に復元するなどのタスクを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="db256-108">You might need to perform other tasks such as to restore a user’s settings to their original state from before UE-V was installed in order to recover lost settings.</span></span> <span data-ttu-id="db256-109">次のトピックでは、UE-V リソースの管理に関するガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="db256-109">The following topics provide guidance for managing UE-V resources.</span></span>

### <span data-ttu-id="db256-110">UE-V のスケジュールされたタスクの頻度の変更</span><span class="sxs-lookup"><span data-stu-id="db256-110">Changing the Frequency of UE-V Scheduled Tasks</span></span>

<span data-ttu-id="db256-111">UE-V が [設定] テンプレートカタログの新しい、更新、または削除されたユーザー設定の場所テンプレートをチェックするときに管理するスケジュール済みタスクを構成できます。</span><span class="sxs-lookup"><span data-stu-id="db256-111">You can configure the scheduled tasks that manage when UE-V checks for new, updated, or removed custom settings location templates in the settings template catalog.</span></span>

[<span data-ttu-id="db256-112">UE-V のスケジュールされたタスクの頻度の変更</span><span class="sxs-lookup"><span data-stu-id="db256-112">Changing the Frequency of UE-V Scheduled Tasks</span></span>](changing-the-frequency-of-ue-v-scheduled-tasks.md)

### <a href="" id="sharing-settings-location-templates-with-the-ue-v-template-gallery-"></a><span data-ttu-id="db256-113">UE-V テンプレート ギャラリーを使用した設定場所テンプレートの共有</span><span class="sxs-lookup"><span data-stu-id="db256-113">Sharing Settings Location Templates with the UE-V Template Gallery</span></span>

<span data-ttu-id="db256-114">UE-V のテンプレートギャラリーでは、UE-V 設定の場所テンプレートの共有が容易になります。</span><span class="sxs-lookup"><span data-stu-id="db256-114">The UE-V template gallery facilitates the sharing of UE-V settings location templates.</span></span> <span data-ttu-id="db256-115">ギャラリーでは、他のユーザーと共有したり、他のユーザーが作成したテンプレートをダウンロードしたりするために、設定場所テンプレートをアップロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="db256-115">The gallery enables you to upload your settings location templates to share with other people and to download templates that other people have created.</span></span>

[<span data-ttu-id="db256-116">UE-V テンプレート ギャラリーを使用した設定場所テンプレートの共有</span><span class="sxs-lookup"><span data-stu-id="db256-116">Sharing Settings Location Templates with the UE-V Template Gallery</span></span>](sharing-settings-location-templates-with-the-ue-v-template-gallery.md)

### <span data-ttu-id="db256-117">アプリケーションと Windows の設定を UE-V 1.0 と同期させる</span><span class="sxs-lookup"><span data-stu-id="db256-117">Restoring application and Windows settings synchronized with UE-V 1.0</span></span>

<span data-ttu-id="db256-118">UE-V の WMI 機能と PowerShell 機能により、設定パッケージを復元することができます。</span><span class="sxs-lookup"><span data-stu-id="db256-118">WMI and PowerShell features of UE-V provide the ability to restore settings packages.</span></span> <span data-ttu-id="db256-119">WMI コマンドと PowerShell コマンドを使用すると、アプリケーションの設定と Windows の設定を、UE-V agent を起動した後に初めてアプリケーションを起動したときにコンピューター上にあった設定値に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="db256-119">WMI and PowerShell commands allow you to restore application settings and Windows settings to the settings values that were on the computer the first time the application was started after the UE-V agent was launched.</span></span>

[<span data-ttu-id="db256-120">UE-V 1.0 を使用して同期されたアプリケーションと Windows の設定の復元</span><span class="sxs-lookup"><span data-stu-id="db256-120">Restoring Application and Windows Settings Synchronized with UE-V 1.0</span></span>](restoring-application-and-windows-settings-synchronized-with-ue-v-10.md)

### <span data-ttu-id="db256-121">グループ ポリシー オブジェクトを使用した UE-V の構成</span><span class="sxs-lookup"><span data-stu-id="db256-121">Configuring UE-V with Group Policy Objects</span></span>

<span data-ttu-id="db256-122">グループポリシーを使って、UE-V によるコンピューター上の設定の同期方法を定義した設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="db256-122">You can use Group Policy to modify the settings that define how UE-V synchronizes settings on computers.</span></span>

[<span data-ttu-id="db256-123">グループ ポリシー オブジェクトを使用した UE-V の構成</span><span class="sxs-lookup"><span data-stu-id="db256-123">Configuring UE-V with Group Policy Objects</span></span>](configuring-ue-v-with-group-policy-objects.md)

### <span data-ttu-id="db256-124">PowerShell と WMI を使用した UE-V の管理</span><span class="sxs-lookup"><span data-stu-id="db256-124">Administering UE-V with PowerShell and WMI</span></span>

<span data-ttu-id="db256-125">PowerShell と WMI を使って、UE-V によるコンピューター上の設定の同期方法を定義する設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="db256-125">You can use PowerShell and WMI to modify the settings that define how UE-V synchronizes settings on computers.</span></span>

[<span data-ttu-id="db256-126">PowerShell と WMI を使用した UE-V 1.0 エージェントの管理</span><span class="sxs-lookup"><span data-stu-id="db256-126">Managing the UE-V 1.0 Agent and Packages with PowerShell and WMI</span></span>](managing-the-ue-v-10-agent-and-packages-with-powershell-and-wmi.md)

### <span data-ttu-id="db256-127">UE-V 設定パッケージの移行</span><span class="sxs-lookup"><span data-stu-id="db256-127">Migrating UE-V Settings Packages</span></span>

<span data-ttu-id="db256-128">新しいサーバーまたはバックアップ目的で、ユーザー設定パッケージを再配置できます。</span><span class="sxs-lookup"><span data-stu-id="db256-128">You can relocate the user settings packages either when migrating to a new server or for backup purposes.</span></span>

[<span data-ttu-id="db256-129">UE-V 設定パッケージの移行</span><span class="sxs-lookup"><span data-stu-id="db256-129">Migrating UE-V Settings Packages</span></span>](migrating-ue-v-settings-packages.md)

## <span data-ttu-id="db256-130">この製品のその他のリソース</span><span class="sxs-lookup"><span data-stu-id="db256-130">Other resources for this product</span></span>


[<span data-ttu-id="db256-131">UE-V 1.0 の操作</span><span class="sxs-lookup"><span data-stu-id="db256-131">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)

 

 





