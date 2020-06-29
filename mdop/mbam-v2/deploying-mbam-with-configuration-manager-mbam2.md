---
title: Configuration Manager による MBAM の展開
description: Configuration Manager による MBAM の展開
author: dansimp
ms.assetid: 89d03e29-457a-471d-b893-e0b74a83ec50
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c6cffc1cf51a26aeaa94fcb265199c19f0f34abe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823454"
---
# <span data-ttu-id="f41b5-103">Configuration Manager による MBAM の展開</span><span class="sxs-lookup"><span data-stu-id="f41b5-103">Deploying MBAM with Configuration Manager</span></span>


<span data-ttu-id="f41b5-104">次の手順では、「はじめに」「[構成マネージャーでの MBAM の使用](getting-started---using-mbam-with-configuration-manager.md)」で説明されている推奨構成を使用して、Microsoft System Center Configuration manager 2007 または MicrosoftSystemCenter2012 ConfigurationManager を使用して Microsoft BitLocker 管理と監視 (mbam) を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f41b5-104">The following procedures describe how to deploy Microsoft BitLocker Administration and Monitoring (MBAM) with Microsoft System Center Configuration Manager 2007 or MicrosoftSystemCenter2012 ConfigurationManager by usingthe recommended configuration, which is described in [Getting Started - Using MBAM with Configuration Manager](getting-started---using-mbam-with-configuration-manager.md).</span></span> <span data-ttu-id="f41b5-105">推奨される構成は、1つ以上の Microsoft BitLocker 管理および監視サーバーに管理機能と監視機能をインストールし、Microsoft System Center Configuration Manager 2007 または MicrosoftSystemCenter2012 ConfigurationManager を別のサーバーにインストールすることです。</span><span class="sxs-lookup"><span data-stu-id="f41b5-105">The recommended configuration is to install the Administration and Monitoring features on one or more Microsoft BitLocker Administration and Monitoring servers, and install Microsoft System Center Configuration Manager 2007 or MicrosoftSystemCenter2012 ConfigurationManager on a separate server.</span></span>

<span data-ttu-id="f41b5-106">インストールを始める前に、「 [Configuration manager を使用して MBAM を展開する](planning-to-deploy-mbam-with-configuration-manager-2.md)ための計画を確認する」を参照して、mbam を configuration manager にインストールするための前提条件とハードウェアおよびソフトウェア要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f41b5-106">Before you start the installation, ensure that you have met the prerequisites and hardware and software requirements for installing MBAM with Configuration Manager by reviewing [Planning to Deploy MBAM with Configuration Manager](planning-to-deploy-mbam-with-configuration-manager-2.md).</span></span>

<span data-ttu-id="f41b5-107">Configuration Manager のトポロジで MBAM を再インストールする必要がある場合は、最初に特定の Configuration Manager オブジェクトを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f41b5-107">If you ever have to reinstall MBAM with the Configuration Manager topology, you will need to remove certain Configuration Manager objects first.</span></span> <span data-ttu-id="f41b5-108">詳細については、[サポート技術](https://go.microsoft.com/fwlink/?LinkId=286306)情報の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f41b5-108">Read the [Knowledge Base article](https://go.microsoft.com/fwlink/?LinkId=286306) for more information.</span></span>

<span data-ttu-id="f41b5-109">MBAM を Configuration Manager にインストールする手順は、次のカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="f41b5-109">The steps to install MBAM with Configuration Manager are grouped into the following categories.</span></span> <span data-ttu-id="f41b5-110">各カテゴリの手順を実行して、インストールを完了します。</span><span class="sxs-lookup"><span data-stu-id="f41b5-110">Complete the steps for each category to complete the installation.</span></span>

## <span data-ttu-id="f41b5-111">mof ファイルを作成または編集する方法</span><span class="sxs-lookup"><span data-stu-id="f41b5-111">How to Create or Edit the mof Files</span></span>


<span data-ttu-id="f41b5-112">MBAM Configuration Manager レポートでクライアントコンピューターが BitLocker のコンプライアンスの詳細を報告できるようにするには、**構成**マネージャーのバージョンに応じて、Sms \ _def ファイルを編集または作成する必要があります ()。</span><span class="sxs-lookup"><span data-stu-id="f41b5-112">To enable the client computers to report BitLocker compliance details through the MBAM Configuration Manager reports, you have to edit the **Configuration.mof** file, and either edit or create the Sms\_def.mof file, depending on which version of Configuration Manager you are using.</span></span>

[<span data-ttu-id="f41b5-113">mof ファイルを作成または編集する方法</span><span class="sxs-lookup"><span data-stu-id="f41b5-113">How to Create or Edit the mof Files</span></span>](how-to-create-or-edit-the-mof-files.md)

## <span data-ttu-id="f41b5-114">Configuration Manager と共に MBAM をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="f41b5-114">How to Install MBAM with Configuration Manager</span></span>


<span data-ttu-id="f41b5-115">このセクションでは、次のものをインストールするための手順について説明します。 MBAM Configuration Manager サーバーデータベースサーバー上の回復データベースと監査データベース管理/監視サーバーのサーバー機能の管理と監視を行います。</span><span class="sxs-lookup"><span data-stu-id="f41b5-115">This section provides steps about how to install the following: MBAM on the Configuration Manager Server; the Recovery and Audit Databases on the Database Server; and the Administration and Monitoring Server features on the Administration and Monitoring Server.</span></span>

[<span data-ttu-id="f41b5-116">Configuration Manager と共に MBAM をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="f41b5-116">How to Install MBAM with Configuration Manager</span></span>](how-to-install-mbam-with-configuration-manager.md)

## <span data-ttu-id="f41b5-117">Configuration Manager サーバーで MBAM サーバー機能のインストールを検証する方法</span><span class="sxs-lookup"><span data-stu-id="f41b5-117">How to Validate the MBAM Server Feature Installation on the Configuration Manager Server</span></span>


<span data-ttu-id="f41b5-118">Microsoft BitLocker の管理と監視のインストールが完了したら、インストールによって Configuration Manager サーバーに必要なすべての MBAM 機能が正しく設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f41b5-118">When the Microsoft BitLocker Administration and Monitoring installation is complete, validate that the installation has successfully set up all the necessary MBAM features required for the Configuration Manager Server.</span></span>

[<span data-ttu-id="f41b5-119">Configuration Manager で MBAM のインストールを検証する方法</span><span class="sxs-lookup"><span data-stu-id="f41b5-119">How to Validate the MBAM Installation with Configuration Manager</span></span>](how-to-validate-the-mbam-installation-with-configuration-manager.md)

## <span data-ttu-id="f41b5-120">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f41b5-120">Related topics</span></span>


[<span data-ttu-id="f41b5-121">MBAM と Configuration Manager の使用</span><span class="sxs-lookup"><span data-stu-id="f41b5-121">Using MBAM with Configuration Manager</span></span>](using-mbam-with-configuration-manager.md)

 

 





