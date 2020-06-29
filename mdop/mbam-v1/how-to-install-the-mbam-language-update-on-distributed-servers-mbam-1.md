---
title: 分散サーバーに MBAM Language Update をインストールする方法
description: 分散サーバーに MBAM Language Update をインストールする方法
author: dansimp
ms.assetid: 5ddc64c6-0417-4a04-843e-b5e18d9f1a52
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6758463c6fc038c4d6ea86c0d49804f29bb543d3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825697"
---
# <span data-ttu-id="e8db1-103">分散サーバーに MBAM Language Update をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="e8db1-103">How to Install the MBAM Language Update on Distributed Servers</span></span>


<span data-ttu-id="e8db1-104">Microsoft BitLocker の管理と監視 (MBAM) には、1台以上のコンピューターで実行できる4つのサーバーの役割が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e8db1-104">Microsoft BitLocker Administration and Monitoring (MBAM) includes four server roles that can be run on one or more computers.</span></span> <span data-ttu-id="e8db1-105">ただし、mbam 1.0 言語リリースと MBAM ポリシーテンプレートのインストールをサポートする更新プログラムが必要なのは、MBAM Server の2つの機能だけです。</span><span class="sxs-lookup"><span data-stu-id="e8db1-105">However, only two MBAM Server features require the update to support the installation of the MBAM 1.0 language release and the MBAM Policy Template.</span></span> <span data-ttu-id="e8db1-106">MBAM Server 機能が複数のコンピューターにインストールされている構成では、次のサーバー機能のみを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8db1-106">In configurations with the MBAM Server features installed on multiple computers, only the following server features need to be updated:</span></span>

-   <span data-ttu-id="e8db1-107">MBAM コンプライアンスと監査レポート</span><span class="sxs-lookup"><span data-stu-id="e8db1-107">The MBAM Compliance and Audit Reports</span></span>

-   <span data-ttu-id="e8db1-108">MBAM 管理と監視サーバー</span><span class="sxs-lookup"><span data-stu-id="e8db1-108">The MBAM Administration and Monitoring Server</span></span>

<span data-ttu-id="e8db1-109">**重要** MBAM server 機能は、まずコンプライアンスと監査レポートの順序で更新する必要があります。その後、管理と監視のサーバー。</span><span class="sxs-lookup"><span data-stu-id="e8db1-109">**Important** The MBAM server features must be updated in this order: Compliance and Audit Reports first, and then the Administration and Monitoring Server.</span></span> <span data-ttu-id="e8db1-110">MBAM グループポリシーテンプレートは、シーケンスを気にすることなくいつでも更新できます。</span><span class="sxs-lookup"><span data-stu-id="e8db1-110">The MBAM Group Policy templates can be updated at any time without concern for sequence.</span></span>

 

**<span data-ttu-id="e8db1-111">MBAM コンプライアンスおよび監査レポートサーバー機能に MBAM 言語更新プログラムをインストールするには</span><span class="sxs-lookup"><span data-stu-id="e8db1-111">To install the MBAM Language Update on the MBAM Compliance and Audit Report Server feature</span></span>**

1.  <span data-ttu-id="e8db1-112">MBAM コンプライアンスと監査レポート機能を実行しているコンピューターで、MBAM 言語更新セットアップウィザード (MBAMsetup.exe) を見つけて実行します。</span><span class="sxs-lookup"><span data-stu-id="e8db1-112">On the computer running the MBAM Compliance and Audit Report feature, locate and run the MBAM Language Update setup wizard (MBAMsetup.exe).</span></span>

2.  <span data-ttu-id="e8db1-113">コンプライアンスおよび監査レポートのためのウィザードを完了して、ウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e8db1-113">Complete the wizard for the Compliance and Audit Reports and then close the wizard.</span></span>

**<span data-ttu-id="e8db1-114">MBAM 管理および監視サーバー機能に MBAM 言語更新プログラムをインストールするには</span><span class="sxs-lookup"><span data-stu-id="e8db1-114">To install the MBAM Language Update on the MBAM Administration and Monitoring Server feature</span></span>**

1.  <span data-ttu-id="e8db1-115">MBAM 管理と監視機能を実行しているコンピューターで、インターネットインフォメーションサービス (IIS) 管理コンソールを開き、[**サイト**] に移動して、Microsoft BitLocker の管理と監視の web サイトを終了します。</span><span class="sxs-lookup"><span data-stu-id="e8db1-115">On the computer that is running the MBAM Administration and Monitoring feature, open the Internet Information Services (IIS) management console, go to **Sites**, and then shut down the Microsoft BitLocker Administration and Monitoring website.</span></span>

2.  <span data-ttu-id="e8db1-116">MBAM web サイトのバインドを編集して、サイトのバインドを変更します。</span><span class="sxs-lookup"><span data-stu-id="e8db1-116">Choose to edit the bindings for the MBAM website, and then modify the bindings of the site.</span></span> <span data-ttu-id="e8db1-117">たとえば、ポートを443から9443に変更します。</span><span class="sxs-lookup"><span data-stu-id="e8db1-117">For example, change the port from 443 to 9443.</span></span>

3.  <span data-ttu-id="e8db1-118">MBAM 言語更新セットアップウィザード (MBAMsetup.exe) を見つけて実行します。</span><span class="sxs-lookup"><span data-stu-id="e8db1-118">Locate and run the MBAM Language Update setup wizard (MBAMsetup.exe).</span></span> <span data-ttu-id="e8db1-119">[管理と監視] サーバー機能のウィザードを完了して、ウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e8db1-119">Complete the wizard for the Administration and Monitoring Server feature and then close the wizard.</span></span>

4.  <span data-ttu-id="e8db1-120">サーバーデータベースをアップグレードしたら、IIS 管理コンソールを開き、Microsoft BitLocker の管理と監視の web サイトのバインドを確認します。</span><span class="sxs-lookup"><span data-stu-id="e8db1-120">After you upgrade the server database, open IIS Management Console and review the bindings of the Microsoft BitLocker Administration and Monitoring website.</span></span>

5.  <span data-ttu-id="e8db1-121">古いバインドを削除して、残りのバインドに、MBAM enterprise 構成の正しいホスト名、証明書、およびポート番号が含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e8db1-121">Delete the old binding and ensure that the remaining binding has the correct host name, certificate, and port number for the MBAM enterprise configuration.</span></span>

6.  <span data-ttu-id="e8db1-122">MBAM web サイトを再起動します。</span><span class="sxs-lookup"><span data-stu-id="e8db1-122">Restart the MBAM web site.</span></span>

7.  <span data-ttu-id="e8db1-123">MBAM web サイトの機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="e8db1-123">Test the MBAM web site functionality:</span></span>

    -   <span data-ttu-id="e8db1-124">MBAM web インターフェイスを開き、クライアントの回復キーを取得できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e8db1-124">Open the MBAM web interface and ensure that you can obtain a recovery key for a client.</span></span>

    -   <span data-ttu-id="e8db1-125">新規または手動で解読されたクライアントコンピューターの暗号化を強制します。</span><span class="sxs-lookup"><span data-stu-id="e8db1-125">Enforce encryption of a new or manually decrypted client computer.</span></span>

        <span data-ttu-id="e8db1-126">**注** MBAM クライアントは、回復およびハードウェアデータベースと通信できる場合にのみ開かれます。</span><span class="sxs-lookup"><span data-stu-id="e8db1-126">**Note** The MBAM client opens only if it can communicate with the Recovery and Hardware database.</span></span>

         

## <span data-ttu-id="e8db1-127">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e8db1-127">Related topics</span></span>


[<span data-ttu-id="e8db1-128">MBAM 1.0 Language Release 更新プログラムの展開</span><span class="sxs-lookup"><span data-stu-id="e8db1-128">Deploying the MBAM 1.0 Language Release Update</span></span>](deploying-the-mbam-10-language-release-update.md)

 

 





