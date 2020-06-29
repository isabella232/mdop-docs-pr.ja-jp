---
title: mof ファイルを作成または編集する方法
description: mof ファイルを作成または編集する方法
author: dansimp
ms.assetid: 4d19d707-b90f-4057-a6e9-e4221a607190
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5f59e9133dd25ecf45d16a5cb704d6ea00923d9e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825324"
---
# <span data-ttu-id="54f4b-103">mof ファイルを作成または編集する方法</span><span class="sxs-lookup"><span data-stu-id="54f4b-103">How to Create or Edit the mof Files</span></span>


<span data-ttu-id="54f4b-104">構成マネージャーを使用して Microsoft BitLocker 管理と監視 (MBAM) をインストールするには、構成の .mof ファイルを編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54f4b-104">Before you install Microsoft BitLocker Administration and Monitoring (MBAM) with Configuration Manager, you need to edit the Configuration.mof file.</span></span> <span data-ttu-id="54f4b-105">また、使用している Configuration Manager のバージョンに応じて、Sms \ _def ファイルを編集するか作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54f4b-105">You also need to either edit or create the Sms\_def.mof file, depending on which version of Configuration Manager you are using.</span></span>

## <span data-ttu-id="54f4b-106">Configuration.mof ファイルを編集する</span><span class="sxs-lookup"><span data-stu-id="54f4b-106">Edit the Configuration.mof File</span></span>


<span data-ttu-id="54f4b-107">MBAM Configuration Manager レポートでクライアントコンピューターが BitLocker のコンプライアンスの詳細を報告できるようにするには、Microsoft System Center Configuration Manager 2007 と SystemCenter2012 ConfigurationManager の構成の .mof ファイルを編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54f4b-107">To enable the client computers to report BitLocker compliance details through the MBAM Configuration Manager reports, you have to edit the Configuration.mof file for Microsoft System Center Configuration Manager 2007 and SystemCenter2012 ConfigurationManager.</span></span>

[<span data-ttu-id="54f4b-108">Configuration.mof ファイルを編集する</span><span class="sxs-lookup"><span data-stu-id="54f4b-108">Edit the Configuration.mof File</span></span>](edit-the-configurationmof-file.md)

## <a href="" id="create-or-edit-the-sms-def-mof-file"></a><span data-ttu-id="54f4b-109">Sms \ _def ファイルを作成または編集する</span><span class="sxs-lookup"><span data-stu-id="54f4b-109">Create or Edit the Sms\_def.mof File</span></span>


<span data-ttu-id="54f4b-110">MBAM Configuration Manager のレポートでクライアントコンピューターが BitLocker の準拠の詳細を報告できるようにするには、Sms \ _def .mof ファイルを作成または編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54f4b-110">To enable the client computers to report BitLocker compliance details in the MBAM Configuration Manager reports, you have to create or edit the Sms\_def.mof file.</span></span> <span data-ttu-id="54f4b-111">Configuration Manager 2007 では、ファイルが既に存在するため、既存のファイルを編集することはできますが、上書きする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="54f4b-111">In Configuration Manager 2007, the file already exists, so you need to edit, but not overwrite, the existing file.</span></span> <span data-ttu-id="54f4b-112">SystemCenter2012 ConfigurationManager を使用している場合は、ファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54f4b-112">If you are using SystemCenter2012 ConfigurationManager, you must create the file.</span></span>

[<span data-ttu-id="54f4b-113">Sms \ _def ファイルを作成または編集する</span><span class="sxs-lookup"><span data-stu-id="54f4b-113">Create or Edit the Sms\_def.mof File</span></span>](create-or-edit-the-sms-defmof-file.md)

## <span data-ttu-id="54f4b-114">関連トピック</span><span class="sxs-lookup"><span data-stu-id="54f4b-114">Related topics</span></span>


[<span data-ttu-id="54f4b-115">Configuration Manager による MBAM の展開</span><span class="sxs-lookup"><span data-stu-id="54f4b-115">Deploying MBAM with Configuration Manager</span></span>](deploying-mbam-with-configuration-manager-mbam2.md)

 

 





