---
title: Configuration Manager で MBAM のインストールを検証する方法
description: Configuration Manager で MBAM のインストールを検証する方法
author: dansimp
ms.assetid: 8e268539-91c3-4e8a-baae-faf3605da818
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 500c6f6ee5138b5677bf1fa20e2627a56981df1f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822637"
---
# <span data-ttu-id="2c455-103">Configuration Manager で MBAM のインストールを検証する方法</span><span class="sxs-lookup"><span data-stu-id="2c455-103">How to Validate the MBAM Installation with Configuration Manager</span></span>


<span data-ttu-id="2c455-104">構成マネージャーを使用して Microsoft BitLocker 管理と監視 (MBAM) をインストールした後、次の手順に従って、インストールによって MBAM の必要なすべての機能が正しく設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2c455-104">After installing Microsoft BitLocker Administration and Monitoring (MBAM) with Configuration Manager, validate that the installation has successfully set up all the necessary features for MBAM by completing the following steps.</span></span>

**<span data-ttu-id="2c455-105">Configuration Manager を使用して MBAM サーバー機能のインストールを検証するには</span><span class="sxs-lookup"><span data-stu-id="2c455-105">To validate the MBAM Server feature installation with Configuration Manager</span></span>**

1.  <span data-ttu-id="2c455-106">System Center Configuration Manager が展開されているサーバーで、[**コントロールパネル]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="2c455-106">On the server where System Center Configuration Manager is deployed, open **Control Panel**.</span></span> <span data-ttu-id="2c455-107">プログラムをアンインストールまたは変更するために使用するプログラムを選択します。</span><span class="sxs-lookup"><span data-stu-id="2c455-107">Select the program that is used to uninstall or change a program.</span></span> <span data-ttu-id="2c455-108">**Microsoft BitLocker の管理と監視**が、プログラムと機能の一覧に表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2c455-108">Verify that **Microsoft BitLocker Administration and Monitoring** appears in the list of programs and features.</span></span>

    <span data-ttu-id="2c455-109">**注** インストールを検証するには、各サーバーのローカルコンピューターの管理者資格情報を持つドメインアカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c455-109">**Note** To validate the installation, you must use a domain account that has local computer administrative credentials on each server.</span></span>

     

2.  <span data-ttu-id="2c455-110">Configuration Manager コンソールを使用して、"MBAM サポートされているコンピューター" という新しいコレクションが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2c455-110">Use the Configuration Manager console to confirm that a new collection, called “MBAM Supported Computers,” is displayed.</span></span>

    <span data-ttu-id="2c455-111">Configuration Manager 2007 でコレクションを表示するには、[**サイトデータベース**( &lt; **SiteCode** &gt;  -  &lt; **ServerName** &gt; 、 &lt; **SiteName** &gt; )]、[**コンピューターの管理**] のいずれかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c455-111">To view the collection with Configuration Manager 2007: Click **Site Database** (&lt;**SiteCode**&gt; - &lt;**ServerName**&gt;, &lt;**SiteName**&gt;), **Computer Management**.</span></span>

    <span data-ttu-id="2c455-112">SystemCenter2012 ConfigurationManager でコレクションを表示するには、[**アセット And コンプライアンス**ワークスペース]、[**デバイスコレクション**] のいずれかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c455-112">To view the collection with SystemCenter2012 ConfigurationManager: Click the **Assets and Compliance** workspace, **Device Collections**.</span></span>

3.  <span data-ttu-id="2c455-113">Configuration Manager コンソールを使用して、次のレポートが**Mbam**フォルダーに一覧表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2c455-113">Use the Configuration Manager console to verify that the following reports are listed in the **MBAM** folder:</span></span>

    -   <span data-ttu-id="2c455-114">BitLocker コンピューターのコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="2c455-114">BitLocker Computer Compliance</span></span>

    -   <span data-ttu-id="2c455-115">BitLocker エンタープライズコンプライアンスダッシュボード</span><span class="sxs-lookup"><span data-stu-id="2c455-115">BitLocker Enterprise Compliance Dashboard</span></span>

    -   <span data-ttu-id="2c455-116">BitLocker Enterprise コンプライアンスの詳細</span><span class="sxs-lookup"><span data-stu-id="2c455-116">BitLocker Enterprise Compliance Details</span></span>

    -   <span data-ttu-id="2c455-117">BitLocker Enterprise コンプライアンスの概要</span><span class="sxs-lookup"><span data-stu-id="2c455-117">BitLocker Enterprise Compliance Summary</span></span>

    <span data-ttu-id="2c455-118">Configuration Manager 2007 でレポートを表示するには、[**レポート**]、[ **reporting Services**]、[\\ \ \ \ &lt; **ServerName** &gt; ]、[**レポートフォルダー** ] のいずれかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c455-118">To view the reports with Configuration Manager 2007: Click **Reporting**, **Reporting Services**, \\\\&lt;**ServerName**&gt;, **Report Folders**</span></span>

    <span data-ttu-id="2c455-119">SystemCenter2012 ConfigurationManager のレポートを表示するには、[**監視**ワークスペース]、[**レポート**]、[**レポート**] のいずれかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c455-119">To view the reports with SystemCenter2012 ConfigurationManager: Click the **Monitoring** workspace, **Reporting**, **Reports**.</span></span>

4.  <span data-ttu-id="2c455-120">Configuration Manager コンソールを使用して、構成基準 "BitLocker Protection" が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2c455-120">Use the Configuration Manager console to confirm that the configuration baseline “BitLocker Protection” is listed.</span></span>

    <span data-ttu-id="2c455-121">Configuration Manager 2007 で構成基準を表示するには、[**必要な構成管理**]、[**構成基準**] のいずれかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c455-121">To view the configuration baselines with Configuration Manager 2007: Click **Desired Configuration Management**, **Configuration Baselines**.</span></span>

    <span data-ttu-id="2c455-122">SystemCenter2012 ConfigurationManager で構成基準を表示するには、[**資産とコンプライアンス**のワークスペース]、[**コンプライアンスの設定**]、[**構成基準**] のいずれかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c455-122">To view the configuration baselines with SystemCenter2012 ConfigurationManager: Click the **Assets and Compliance** workspace, **Compliance Settings**, **Configuration Baselines**.</span></span>

5.  <span data-ttu-id="2c455-123">Configuration Manager コンソールを使用して、次の新しい構成項目が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2c455-123">Use the Configuration Manager console to confirm that the following new configuration items are displayed:</span></span>

    -   <span data-ttu-id="2c455-124">BitLocker 固定データドライブの保護</span><span class="sxs-lookup"><span data-stu-id="2c455-124">BitLocker Fixed Data Drives Protection</span></span>

    -   <span data-ttu-id="2c455-125">BitLocker オペレーティングシステムドライブの保護</span><span class="sxs-lookup"><span data-stu-id="2c455-125">BitLocker Operating System Drive Protection</span></span>

    <span data-ttu-id="2c455-126">Configuration Manager 2007 で構成項目を表示するには、[**必要な構成管理**]、[**構成項目**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c455-126">To view the configuration items with Configuration Manager 2007: Click **Desired Configuration Management**, **Configuration Items**.</span></span>

    <span data-ttu-id="2c455-127">SystemCenter2012 ConfigurationManager で構成項目を表示するには、[**資産とコンプライアンス**のワークスペース]、[**コンプライアンス設定**]、[**構成項目**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c455-127">To view the configuration items with SystemCenter2012 ConfigurationManager: Click the **Assets and Compliance** workspace, **Compliance Settings**, **Configuration Items**.</span></span>

## <span data-ttu-id="2c455-128">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2c455-128">Related topics</span></span>


[<span data-ttu-id="2c455-129">Configuration Manager による MBAM の展開</span><span class="sxs-lookup"><span data-stu-id="2c455-129">Deploying MBAM with Configuration Manager</span></span>](deploying-mbam-with-configuration-manager-mbam2.md)

 

 





