---
title: MBAM 1.0 グループ ポリシー オブジェクトの展開
description: MBAM 1.0 グループ ポリシー オブジェクトの展開
author: dansimp
ms.assetid: 2129291e-d2b2-41ed-b643-1e311c49fee7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8d14123f1d5b197146e425cba063e8ce4c180641
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821217"
---
# <span data-ttu-id="f4b9d-103">MBAM 1.0 グループ ポリシー オブジェクトの展開</span><span class="sxs-lookup"><span data-stu-id="f4b9d-103">Deploying MBAM 1.0 Group Policy Objects</span></span>


<span data-ttu-id="f4b9d-104">Microsoft BitLocker の管理と監視 (MBAM) を正常に展開するには、MBAM の実装で使用するグループポリシーを最初に確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4b9d-104">To successfully deploy Microsoft BitLocker Administration and Monitoring (MBAM), you must first determine the Group Policies that you will use in your implementation of MBAM.</span></span> <span data-ttu-id="f4b9d-105">利用可能なさまざまなポリシーの詳細については、「 [MBAM 1.0 グループポリシーの要件の計画](planning-for-mbam-10-group-policy-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4b9d-105">For more information about the various available policies, see [Planning for MBAM 1.0 Group Policy Requirements](planning-for-mbam-10-group-policy-requirements.md).</span></span> <span data-ttu-id="f4b9d-106">使用するポリシーを決定したら、MBAM 1.0 グループポリシーテンプレートを使用して、MBAM ポリシー設定を含む1つ以上のグループポリシーオブジェクト (GPO) を作成して展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4b9d-106">When you have determined the policies that you are going to use, you must use the MBAM 1.0 Group Policy template to create and deploy one or more Group Policy objects (GPO) that include the MBAM policy settings.</span></span>

## <span data-ttu-id="f4b9d-107">MBAM 1.0 グループポリシーテンプレートをインストールする</span><span class="sxs-lookup"><span data-stu-id="f4b9d-107">Install the MBAM 1.0 Group Policy template</span></span>


<span data-ttu-id="f4b9d-108">MBAM のサーバー関連機能を提供するだけでなく、server setup アプリケーションには MBAM グループポリシーテンプレートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f4b9d-108">In addition to providing server-related features of MBAM, the server setup application includes an MBAM Group Policy template.</span></span> <span data-ttu-id="f4b9d-109">このテンプレートは、グループポリシー管理コンソール (GPMC) または高度なグループポリシー管理 (AGPM) を実行できる任意のコンピューターにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="f4b9d-109">You can install this template on any computer that is able to run the Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM).</span></span>

[<span data-ttu-id="f4b9d-110">MBAM 1.0 グループ ポリシー テンプレートをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="f4b9d-110">How to Install the MBAM 1.0 Group Policy Template</span></span>](how-to-install-the-mbam-10-group-policy-template.md)

## <span data-ttu-id="f4b9d-111">MBAM 1.0 グループポリシー設定の展開</span><span class="sxs-lookup"><span data-stu-id="f4b9d-111">Deploy MBAM 1.0 Group Policy settings</span></span>


<span data-ttu-id="f4b9d-112">必要な Gpo を作成したら、MBAM グループポリシー設定を組織のクライアントコンピューターに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4b9d-112">After you create the necessary GPOs, you must deploy the MBAM Group Policy settings to your organization’s client computers.</span></span>

[<span data-ttu-id="f4b9d-113">MBAM 1.0 GPO 設定を編集する方法</span><span class="sxs-lookup"><span data-stu-id="f4b9d-113">How to Edit MBAM 1.0 GPO Settings</span></span>](how-to-edit-mbam-10-gpo-settings.md)

## <span data-ttu-id="f4b9d-114">Windows で MBAM コントロールパネルを表示する</span><span class="sxs-lookup"><span data-stu-id="f4b9d-114">Display the MBAM Control Panel in Windows</span></span>


<span data-ttu-id="f4b9d-115">MBAM はカスタマイズされた MBAM コントロールパネルを提供して、既定の Windows BitLocker コントロールパネルを置き換えることができるため、グループポリシーを使用して、既定の BitLocker コントロールパネルをエンドユーザーに表示しないようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f4b9d-115">Because MBAM offers a customized MBAM control panel that can replace the default Windows BitLocker control panel, you can also choose to hide the default BitLocker Control Panel from end users by using Group Policy.</span></span>

[<span data-ttu-id="f4b9d-116">Windows コントロール パネルで既定の BitLocker 暗号化を非表示にする方法</span><span class="sxs-lookup"><span data-stu-id="f4b9d-116">How to Hide Default BitLocker Encryption in The Windows Control Panel</span></span>](how-to-hide-default-bitlocker-encryption-in-the-windows-control-panel.md)

## <span data-ttu-id="f4b9d-117">MBAM 1.0 グループポリシーオブジェクトの展開に関するその他のリソース</span><span class="sxs-lookup"><span data-stu-id="f4b9d-117">Other resources for deploying MBAM 1.0 Group Policy Objects</span></span>


[<span data-ttu-id="f4b9d-118">MBAM 1.0 の展開</span><span class="sxs-lookup"><span data-stu-id="f4b9d-118">Deploying MBAM 1.0</span></span>](deploying-mbam-10.md)

 

 





