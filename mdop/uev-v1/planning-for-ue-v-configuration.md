---
title: UE-V の構成計画
description: UE-V の構成計画
author: dansimp
ms.assetid: db78dad4-78e0-45d6-a235-8b7345cb79f8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ce21afc7b7e8ee183b4fb86de7dea6eeaa58953e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826824"
---
# <span data-ttu-id="213a6-103">UE-V の構成計画</span><span class="sxs-lookup"><span data-stu-id="213a6-103">Planning for UE-V Configuration</span></span>


<span data-ttu-id="213a6-104">どのアプリケーションを展開し、どの構成で UE-V の動作を定義するかを定義することで、企業の特定のニーズに合わせて Microsoft User Experience Virtualization (UE-V) を構成できます。</span><span class="sxs-lookup"><span data-stu-id="213a6-104">You can configure Microsoft User Experience Virtualization (UE-V) to meet the specific needs of your enterprise by defining which applications are deployed and which configurations define the UE-V behavior.</span></span>

## <span data-ttu-id="213a6-105">どのアプリケーションを UE-V と同期するかを計画する</span><span class="sxs-lookup"><span data-stu-id="213a6-105">Plan which applications to synchronize with UE-V</span></span>


<span data-ttu-id="213a6-106">UE-V には、定義済みの設定場所テンプレートのセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="213a6-106">UE-V includes a set of predefined settings location templates.</span></span> <span data-ttu-id="213a6-107">UE-V を使用すると、管理者は、エンタープライズで使用されているサードパーティまたは基幹業務アプリケーションなど、他のアプリケーションのカスタム設定の場所テンプレートを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="213a6-107">UE-V also allows administrators to create custom settings location templates for other applications, including third-party or line-of-business applications that are used in the enterprise.</span></span> <span data-ttu-id="213a6-108">このトピックでは、UE-V クライアントに含まれているアプリケーションの一覧と、カスタム設定の場所テンプレートを含める方法に関するガイダンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="213a6-108">This topic includes a list of applications that are included with the UE-V client and guidance on how to include custom settings location templates.</span></span>

[<span data-ttu-id="213a6-109">UE-V 1.0 を使用して同期するアプリケーションの計画</span><span class="sxs-lookup"><span data-stu-id="213a6-109">Planning Which Applications to Synchronize with UE-V 1.0</span></span>](planning-which-applications-to-synchronize-with-ue-v-10.md)

## <span data-ttu-id="213a6-110">UE-V の基幹業務アプリケーションを評価するためのチェックリスト</span><span class="sxs-lookup"><span data-stu-id="213a6-110">Checklist for Evaluating Line-of-Business Applications for UE-V</span></span>


<span data-ttu-id="213a6-111">基幹業務アプリケーションを同期する必要があるかどうかについてのガイダンス。</span><span class="sxs-lookup"><span data-stu-id="213a6-111">Guidance on whether a line-of-business application should be synchronized.</span></span>

[<span data-ttu-id="213a6-112">UE-V 1.0 の基幹業務アプリケーションを評価するためのチェックリスト</span><span class="sxs-lookup"><span data-stu-id="213a6-112">Checklist for Evaluating Line-of-Business Applications for UE-V 1.0</span></span>](checklist-for-evaluating-line-of-business-applications-for-ue-v-10.md)

## <span data-ttu-id="213a6-113">カスタムテンプレートの展開を計画する</span><span class="sxs-lookup"><span data-stu-id="213a6-113">Plan custom template deployment</span></span>


<span data-ttu-id="213a6-114">サードパーティアプリケーションなどの他のアプリケーションをサポートするには、UE-V Generator を使用してカスタム設定の場所テンプレートを作成し、それらを設定テンプレートカタログに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="213a6-114">In order to support other applications, including third-party applications, you must create custom settings location templates by using the UE-V Generator, and deploy them to a settings template catalog.</span></span>

[<span data-ttu-id="213a6-115">UE-V 1.0 のカスタム テンプレートの展開計画</span><span class="sxs-lookup"><span data-stu-id="213a6-115">Planning for Custom Template Deployment for UE-V 1.0</span></span>](planning-for-custom-template-deployment-for-ue-v-10.md)

## <span data-ttu-id="213a6-116">UE-V 構成の計画</span><span class="sxs-lookup"><span data-stu-id="213a6-116">Plan for UE-V configuration</span></span>


<span data-ttu-id="213a6-117">UE-V 構成は、設定が企業全体でどのように同期されるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="213a6-117">UE-V configurations determine how settings are synchronized throughout the enterprise.</span></span> <span data-ttu-id="213a6-118">これらの構成は、UE-V エージェントの展開前、最中、または実行後に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="213a6-118">These configurations can be made before, during, or after the UE-V Agent is deployed.</span></span> <span data-ttu-id="213a6-119">UE-V には、さまざまな構成方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="213a6-119">UE-V provides a variety of configuration methods</span></span>

[<span data-ttu-id="213a6-120">UE-V の構成方法の計画</span><span class="sxs-lookup"><span data-stu-id="213a6-120">Planning for UE-V Configuration Methods</span></span>](planning-for-ue-v-configuration-methods.md)

## <span data-ttu-id="213a6-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="213a6-121">Related topics</span></span>


[<span data-ttu-id="213a6-122">UE-V 1.0 の計画</span><span class="sxs-lookup"><span data-stu-id="213a6-122">Planning for UE-V 1.0</span></span>](planning-for-ue-v-10.md)

 

 





