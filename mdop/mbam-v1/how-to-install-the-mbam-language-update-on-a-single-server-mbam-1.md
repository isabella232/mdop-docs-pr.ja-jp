---
title: 単一サーバーに MBAM Language Update をインストールする方法
description: 単一サーバーに MBAM Language Update をインストールする方法
author: dansimp
ms.assetid: e6fe59a3-a3e1-455c-a059-1f23ee083cf6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 94814158335430aba433c180cdba83d0cf15b760
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824754"
---
# <span data-ttu-id="9f47f-103">単一サーバーに MBAM Language Update をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="9f47f-103">How to Install the MBAM Language Update on a Single Server</span></span>


<span data-ttu-id="9f47f-104">Microsoft BitLocker の管理と監視 (MBAM) には、1台以上のコンピューターで実行できる4つのサーバーの役割が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9f47f-104">Microsoft BitLocker Administration and Monitoring (MBAM) includes four server roles that can be run on one or more computers.</span></span> <span data-ttu-id="9f47f-105">ただし、mbam 1.0 言語リリースと MBAM ポリシーテンプレートのインストールをサポートするには、MBAM Server の2つの機能のみを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f47f-105">However, only two MBAM Server features require the update to support installation of the MBAM 1.0 language release and the MBAM Policy Template.</span></span> <span data-ttu-id="9f47f-106">1台のコンピューターにインストールされる必要がある3つのすべての MBAM 機能を更新するには、このトピックで説明する手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9f47f-106">To update all three of the required MBAM features to be installed on one computer, perform the steps described in this topic.</span></span>

**<span data-ttu-id="9f47f-107">1台のサーバーに MBAM 言語更新プログラムをインストールするには</span><span class="sxs-lookup"><span data-stu-id="9f47f-107">To install the MBAM language update on a single server</span></span>**

1.  <span data-ttu-id="9f47f-108">インターネットインフォメーションサービス (IIS) 管理コンソールを開き、[**サイト**] に移動して、Microsoft BitLocker の管理と監視の web サイトを終了します。</span><span class="sxs-lookup"><span data-stu-id="9f47f-108">Open the Internet Information Services (IIS) Management Console, go to **Sites**, and then shut down the Microsoft BitLocker Administration and Monitoring website.</span></span>

2.  <span data-ttu-id="9f47f-109">MBAM web サイトのバインドを編集してから、サイトのバインドを一時的に変更します。</span><span class="sxs-lookup"><span data-stu-id="9f47f-109">Edit the bindings for the MBAM website, and then temporarily modify the bindings of the site.</span></span> <span data-ttu-id="9f47f-110">たとえば、ポートを443から9443に変更します。</span><span class="sxs-lookup"><span data-stu-id="9f47f-110">For example, change the port from 443 to 9443.</span></span>

3.  <span data-ttu-id="9f47f-111">MBAM セットアップウィザード (MBAMsetup.exe) を見つけて実行し、次の3つの機能を選びます。</span><span class="sxs-lookup"><span data-stu-id="9f47f-111">Locate and run the MBAM setup wizard (MBAMsetup.exe) and select the following three features:</span></span>

    1.  <span data-ttu-id="9f47f-112">コンプライアンスと監査レポート</span><span class="sxs-lookup"><span data-stu-id="9f47f-112">Compliance and Audit Reports</span></span>

    2.  <span data-ttu-id="9f47f-113">管理と監視サーバー</span><span class="sxs-lookup"><span data-stu-id="9f47f-113">Administration and Monitoring Server</span></span>

    3.  <span data-ttu-id="9f47f-114">グループポリシーテンプレート</span><span class="sxs-lookup"><span data-stu-id="9f47f-114">Group Policy Templates</span></span>

    <span data-ttu-id="9f47f-115">**重要** MBAM server 機能は、次の順序で更新する必要があります: 最初にコンプライアンスと監査レポート、次に管理と監視サーバー。</span><span class="sxs-lookup"><span data-stu-id="9f47f-115">**Important** The MBAM server features must be updated in the following order: Compliance and Audit Reports first, then Administration and Monitoring Server.</span></span> <span data-ttu-id="9f47f-116">グループポリシーテンプレートは、シーケンスを気にすることなくいつでも更新できます。</span><span class="sxs-lookup"><span data-stu-id="9f47f-116">The Group Policy templates can be updated at any time without concern for sequence.</span></span>

     

4.  <span data-ttu-id="9f47f-117">サーバーデータベースをアップグレードしたら、IIS 管理コンソールを開いて、Microsoft BitLocker の管理と監視の web サイトのバインドを確認します。</span><span class="sxs-lookup"><span data-stu-id="9f47f-117">After you upgrade the server database, open the IIS Management Console and review the bindings of the Microsoft BitLocker Administration and Monitoring website.</span></span>

5.  <span data-ttu-id="9f47f-118">バインドの1つを削除して、残りのバインドに MBAM enterprise 構成の正しいホスト名、証明書、およびポート番号が含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9f47f-118">Delete one of the bindings and ensure that the remaining binding has the correct host name, certificate, and port number for the MBAM enterprise configuration.</span></span>

6.  <span data-ttu-id="9f47f-119">MBAM web サイトを再起動します。</span><span class="sxs-lookup"><span data-stu-id="9f47f-119">Restart the MBAM website.</span></span>

7.  <span data-ttu-id="9f47f-120">MBAM web サイトの機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="9f47f-120">Test the MBAM website functionality:</span></span>

    -   <span data-ttu-id="9f47f-121">MBAM web インターフェイスを開き、クライアントの回復キーを取得できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9f47f-121">Open the MBAM web interface and ensure you can fetch a recovery key for a client.</span></span>

    -   <span data-ttu-id="9f47f-122">新規または手動で解読されたクライアントコンピューターの暗号化を強制します。</span><span class="sxs-lookup"><span data-stu-id="9f47f-122">Enforce encryption of a new or manually decrypted client computer.</span></span>

        <span data-ttu-id="9f47f-123">**注** MBAM クライアントは、回復およびハードウェアデータベースと通信できる場合にのみ開かれます。</span><span class="sxs-lookup"><span data-stu-id="9f47f-123">**Note** The MBAM client opens only if it can communicate with the Recovery and Hardware database.</span></span>

         

## <span data-ttu-id="9f47f-124">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9f47f-124">Related topics</span></span>


[<span data-ttu-id="9f47f-125">MBAM 1.0 Language Release 更新プログラムの展開</span><span class="sxs-lookup"><span data-stu-id="9f47f-125">Deploying the MBAM 1.0 Language Release Update</span></span>](deploying-the-mbam-10-language-release-update.md)

 

 





