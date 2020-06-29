---
title: User Experience Virtualization 1.0 について
description: User Experience Virtualization 1.0 について
author: dansimp
ms.assetid: 3758b100-35a8-4e10-ac08-f583fb8ddbd9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6010f9c4ebc260eec0324fb880dc2c92fd675130
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822714"
---
# <span data-ttu-id="5d631-103">User Experience Virtualization 1.0 について</span><span class="sxs-lookup"><span data-stu-id="5d631-103">About User Experience Virtualization 1.0</span></span>


<span data-ttu-id="5d631-104">Microsoft User Experience Virtualization (UE-V) は、ユーザーによって行われた変更をアプリケーションの設定と Windows オペレーティングシステムの設定に対して監視します。</span><span class="sxs-lookup"><span data-stu-id="5d631-104">Microsoft User Experience Virtualization (UE-V) monitors the changes that are made by users to application settings and Windows operating system settings.</span></span> <span data-ttu-id="5d631-105">ユーザー設定は、設定の保存場所にキャプチャされ、中央に配置されます。</span><span class="sxs-lookup"><span data-stu-id="5d631-105">The user settings are captured and centralized to a settings storage location.</span></span> <span data-ttu-id="5d631-106">これらの設定は、デスクトップコンピューター、ノート pc、仮想デスクトップインフラストラクチャ (VDI) セッションなど、ユーザーによってアクセスされるさまざまなコンピューターに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="5d631-106">These settings can then be applied to the different computers that are accessed by the user, including desktop computers, laptop computers, and virtual desktop infrastructure (VDI) sessions.</span></span>

<span data-ttu-id="5d631-107">ユーザーエクスペリエンスの仮想化では、設定場所テンプレートを使用して、ユーザーコンピューター上のどのアプリケーションと Windows 設定を監視および一元管理するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5d631-107">User Experience Virtualization uses settings location templates to specify what applications and Windows settings on the user computers are monitored and centralized.</span></span> <span data-ttu-id="5d631-108">設定場所テンプレートは、各アプリケーションまたはオペレーティングシステムの設定に関連付けられているファイルとレジストリの場所を指定する XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="5d631-108">The settings location template is an XML file that specifies which file and registry locations are associated with each application or operating system setting.</span></span> <span data-ttu-id="5d631-109">このテンプレートには、設定の値は含まれていません。これには、監視される設定の場所のみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5d631-109">The template does not contain values for the settings; it contains only the locations of the settings that are to be monitored.</span></span>

<span data-ttu-id="5d631-110">ユーザーがコンピューターを操作している場合は、アプリケーションの設定と Windows 設定が UE-V によって監視されます。</span><span class="sxs-lookup"><span data-stu-id="5d631-110">The application settings and Windows settings are monitored by UE-V when users are working on their computers.</span></span> <span data-ttu-id="5d631-111">アプリケーション設定の値は、ユーザーがアプリケーションを閉じたときに、設定ストレージサーバーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="5d631-111">The values for the application settings are stored on the settings storage server when the user closes the application.</span></span> <span data-ttu-id="5d631-112">Windows 設定の値は、ユーザーがログオフするとき、コンピューターがロックされているとき、またはコンピューターからリモートで接続を解除したときに保存されます。</span><span class="sxs-lookup"><span data-stu-id="5d631-112">The values for the Windows settings are stored when the user logs off, when the computer is locked, or when they disconnect remotely from a computer.</span></span>

<span data-ttu-id="5d631-113">管理者は、UE-V 設定の場所テンプレートを作成して、どのエンタープライズアプリケーション設定をローミングするかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="5d631-113">An administrator can create a UE-V settings location template to specify which enterprise application settings will roam.</span></span> <span data-ttu-id="5d631-114">UE-V には、一部の Microsoft アプリケーションや Windows 設定用の設定場所テンプレートのセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5d631-114">UE-V includes a set of settings location templates for some Microsoft applications and Windows settings.</span></span> <span data-ttu-id="5d631-115">UE-V の既定のアプリケーションと設定の一覧については、「 [ue-v 1.0 を使用して同期するアプリケーションを計画](planning-which-applications-to-synchronize-with-ue-v-10.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d631-115">For a list of default applications and settings in UE-V, see [Planning Which Applications to Synchronize with UE-V 1.0](planning-which-applications-to-synchronize-with-ue-v-10.md).</span></span>

## <span data-ttu-id="5d631-116">UEV 1.0 リリースノート</span><span class="sxs-lookup"><span data-stu-id="5d631-116">UEV 1.0 Release Notes</span></span>


<span data-ttu-id="5d631-117">詳細と、ドキュメントに組み込まれていない最新ニュースについては、「 [Microsoft User Experience Virtualization (ue-v) 1.0 のリリースノート](microsoft-user-experience-virtualization--ue-v--10-release-notes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d631-117">For more information, and for late-breaking news that did not make it into the documentation, see [Microsoft User Experience Virtualization (UE-V) 1.0 Release Notes](microsoft-user-experience-virtualization--ue-v--10-release-notes.md).</span></span>

## <span data-ttu-id="5d631-118">関連トピック</span><span class="sxs-lookup"><span data-stu-id="5d631-118">Related topics</span></span>


[<span data-ttu-id="5d631-119">User Experience Virtualization 1.0 の概要</span><span class="sxs-lookup"><span data-stu-id="5d631-119">Getting Started With User Experience Virtualization 1.0</span></span>](getting-started-with-user-experience-virtualization-10.md)

[<span data-ttu-id="5d631-120">Microsoft User Experience Virtualization (UE-V) 1.0</span><span class="sxs-lookup"><span data-stu-id="5d631-120">Microsoft User Experience Virtualization (UE-V) 1.0</span></span>](index.md)

[<span data-ttu-id="5d631-121">UE-V 1.0 のアーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="5d631-121">High-Level Architecture for UE-V 1.0</span></span>](high-level-architecture-for-ue-v-10.md)

 

 





