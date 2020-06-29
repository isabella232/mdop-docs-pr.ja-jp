---
title: MBAM 2.0 グループ ポリシー オブジェクトの展開
description: MBAM 2.0 グループ ポリシー オブジェクトの展開
author: dansimp
ms.assetid: f17f3897-73ab-431b-a6ec-5a6cff9f279a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1ce2c2a37631d9d678d6de7c1d66b7fdafb2ade9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823494"
---
# <span data-ttu-id="6e539-103">MBAM 2.0 グループ ポリシー オブジェクトの展開</span><span class="sxs-lookup"><span data-stu-id="6e539-103">Deploying MBAM 2.0 Group Policy Objects</span></span>


<span data-ttu-id="6e539-104">Microsoft BitLocker の管理と監視 (MBAM) を正常に展開するには、まず Microsoft BitLocker の管理と監視の実装で使用するグループポリシーを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e539-104">To successfully deploy Microsoft BitLocker Administration and Monitoring (MBAM), you first have to determine the Group Policies that you will use in your implementation of Microsoft BitLocker Administration and Monitoring.</span></span> <span data-ttu-id="6e539-105">使用可能なさまざまなポリシーの詳細については、「 [MBAM 2.0 グループポリシーの要件](planning-for-mbam-20-group-policy-requirements-mbam-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e539-105">See [Planning for MBAM 2.0 Group Policy Requirements](planning-for-mbam-20-group-policy-requirements-mbam-2.md) for more information on the different policies that are available.</span></span> <span data-ttu-id="6e539-106">使用するポリシーを決定したら、MBAM 2.0 グループポリシーテンプレートを使用して、MBAM のポリシー設定を含む1つ以上のグループポリシーオブジェクト (GPO) を作成して展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e539-106">When you have determined the policies that you are going to use, you then must create and deploy one or more Group Policy Objects (GPO) that include the policy settings for MBAM by using the MBAM 2.0 Group Policy template.</span></span>

## <span data-ttu-id="6e539-107">MBAM 2.0 グループポリシーテンプレートをインストールする</span><span class="sxs-lookup"><span data-stu-id="6e539-107">Install the MBAM 2.0 Group Policy Template</span></span>


<span data-ttu-id="6e539-108">サーバーに関連する Microsoft BitLocker の管理機能と監視機能に加えて、server setup アプリケーションには MBAM グループポリシーテンプレートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6e539-108">In addition to the server-related Microsoft BitLocker Administration and Monitoring features, the server setup application includes a MBAM Group Policy template.</span></span> <span data-ttu-id="6e539-109">このテンプレートは、グループポリシー管理コンソール (GPMC) または高度なグループポリシー管理 (AGPM) を実行できる任意のコンピューターにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="6e539-109">This template can be installed on any computer able to run the Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM).</span></span>

[<span data-ttu-id="6e539-110">MBAM 2.0 グループ ポリシー テンプレートをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="6e539-110">How to Install the MBAM 2.0 Group Policy Template</span></span>](how-to-install-the-mbam-20-group-policy-template-mbam-2.md)

## <span data-ttu-id="6e539-111">MBAM 2.0 グループポリシー設定の展開</span><span class="sxs-lookup"><span data-stu-id="6e539-111">Deploy MBAM 2.0 Group Policy Settings</span></span>


<span data-ttu-id="6e539-112">必要な Gpo を作成したら、MBAM グループポリシー設定を組織のクライアントコンピューターに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e539-112">After you create the necessary GPOs, you must deploy the MBAM Group Policy settings to your organization’s client computers.</span></span>

[<span data-ttu-id="6e539-113">MBAM 2.0 GPO 設定を編集する方法</span><span class="sxs-lookup"><span data-stu-id="6e539-113">How to Edit MBAM 2.0 GPO Settings</span></span>](how-to-edit-mbam-20-gpo-settings-mbam-2.md)

## <span data-ttu-id="6e539-114">Windows で MBAM コントロールパネルを表示する</span><span class="sxs-lookup"><span data-stu-id="6e539-114">Display the MBAM Control Panel in Windows</span></span>


<span data-ttu-id="6e539-115">MBAM はカスタマイズされた MBAM コントロールパネルを提供して、既定の Windows BitLocker コントロールパネルを置き換えることができるため、グループポリシーを使用して、既定の BitLocker コントロールパネルをエンドユーザーに表示しないようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6e539-115">Because MBAM offers a customized MBAM control panel that can replace the default Windows BitLocker control panel, you can also choose to hide the default BitLocker Control Panel from end users by using Group Policy.</span></span>

[<span data-ttu-id="6e539-116">Windows コントロール パネルで既定の BitLocker 暗号化を非表示にする方法</span><span class="sxs-lookup"><span data-stu-id="6e539-116">How to Hide Default BitLocker Encryption in the Windows Control Panel</span></span>](how-to-hide-default-bitlocker-encryption-in-the-windows-control-panel-mbam-2.md)

## <span data-ttu-id="6e539-117">MBAM 2.0 グループポリシーオブジェクトの展開に関するその他のリソース</span><span class="sxs-lookup"><span data-stu-id="6e539-117">Other Resources for Deploying MBAM 2.0 Group Policy Objects</span></span>


[<span data-ttu-id="6e539-118">MBAM 2.0 の展開</span><span class="sxs-lookup"><span data-stu-id="6e539-118">Deploying MBAM 2.0</span></span>](deploying-mbam-20-mbam-2.md)

 

 





