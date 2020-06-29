---
title: テンプレートの作成と既定のテンプレートの設定
description: テンプレートの作成と既定のテンプレートの設定
author: dansimp
ms.assetid: ffa72c2a-64eb-4492-8072-c3a66179b546
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0c415ab2fba994eff14caf9ec557e2ba8ccacfa5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821044"
---
# <span data-ttu-id="7e0fb-103">テンプレートの作成と既定のテンプレートの設定</span><span class="sxs-lookup"><span data-stu-id="7e0fb-103">Creating a Template and Setting a Default Template</span></span>


<span data-ttu-id="7e0fb-104">テンプレートを作成すると、特定のバージョンのグループポリシーオブジェクト (GPO) のすべての設定を保存して、新しい Gpo の作成の開始点として使用することができます。</span><span class="sxs-lookup"><span data-stu-id="7e0fb-104">Creating a template enables you to save all the settings of a particular version of a Group Policy Object (GPO) to use as a starting point for creating new GPOs.</span></span> <span data-ttu-id="7e0fb-105">エディターとして、新しい Gpo を作成するすべてのグループポリシー管理者が既定のテンプレートとして使用できるテンプレートを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="7e0fb-105">As an Editor, you can also specify which of the available templates will be the default template for all Group Policy administrators creating new GPOs.</span></span>

<span data-ttu-id="7e0fb-106">テンプレートには、次のような可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7e0fb-106">Some potential uses for a template include the following:</span></span>

-   <span data-ttu-id="7e0fb-107">組織がドメイン全体で再利用できるセキュリティベースラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="7e0fb-107">Create a security baseline that your organization can reuse across domains.</span></span>

-   <span data-ttu-id="7e0fb-108">組織が部署ごとにカスタマイズできるフォルダーリダイレクションとオフラインファイルを管理するためのテンプレートを作成します。</span><span class="sxs-lookup"><span data-stu-id="7e0fb-108">Create a template to manage folder redirection and offline files that your organization can customize for each department.</span></span>

-   <span data-ttu-id="7e0fb-109">組織がさまざまな地理的領域のワイヤレスネットワーク接続を構成するために使用できるワイヤレスネットワークテンプレートを作成します。</span><span class="sxs-lookup"><span data-stu-id="7e0fb-109">Create a wireless networking template that your organization can use to configure wireless network connections for different geographical areas.</span></span>

-   <span data-ttu-id="7e0fb-110">ローカルネットワーク管理者の法令遵守テンプレートを作成します。</span><span class="sxs-lookup"><span data-stu-id="7e0fb-110">Create regulatory compliance templates for local network administrators.</span></span>

-   <span data-ttu-id="7e0fb-111">既存の GPO の読み取り専用スナップショットを作成します。</span><span class="sxs-lookup"><span data-stu-id="7e0fb-111">Create a read-only snapshot of an existing GPO.</span></span>

<span data-ttu-id="7e0fb-112">**注** テンプレートは、編集できない GPO の静的なバージョンであり、新しい編集可能な Gpo を作成するための開始点として使用することができます。</span><span class="sxs-lookup"><span data-stu-id="7e0fb-112">**Note** A template is a static version of a GPO that cannot be edited, yet can be used as a starting point for creating new, editable GPOs.</span></span> <span data-ttu-id="7e0fb-113">テンプレートの名前の変更や削除は、そのテンプレートから作成された Gpo には影響しません。</span><span class="sxs-lookup"><span data-stu-id="7e0fb-113">Renaming or deleting a template does not affect GPOs created from that template.</span></span>

 

-   [<span data-ttu-id="7e0fb-114">テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="7e0fb-114">Create a Template</span></span>](create-a-template-agpm40.md)

-   [<span data-ttu-id="7e0fb-115">既定のテンプレートを設定する</span><span class="sxs-lookup"><span data-stu-id="7e0fb-115">Set a Default Template</span></span>](set-a-default-template-agpm40.md)

 

 





