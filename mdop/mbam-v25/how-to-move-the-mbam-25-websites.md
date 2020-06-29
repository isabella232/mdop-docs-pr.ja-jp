---
title: MBAM 2.5 Web サイトを移動する方法
description: MBAM 2.5 Web サイトを移動する方法
author: dansimp
ms.assetid: 71af9a54-c27b-408f-9d75-37c0d02e730e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa5bd8156810b3dccc1588b4dfd4cadd96fd22fb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825747"
---
# <span data-ttu-id="47dca-103">MBAM 2.5 Web サイトを移動する方法</span><span class="sxs-lookup"><span data-stu-id="47dca-103">How to Move the MBAM 2.5 Websites</span></span>


<span data-ttu-id="47dca-104">次の手順を使用して、次の MBAM web サイトを1台のコンピューターから別のコンピューターに移動します。つまり、サーバー A からサーバー B に次の機能を移動します。</span><span class="sxs-lookup"><span data-stu-id="47dca-104">Use these procedures to move the following MBAM websites from one computer to another, that is, to move the following features from Server A to Server B:</span></span>

-   <span data-ttu-id="47dca-105">管理と監視の Web サイト</span><span class="sxs-lookup"><span data-stu-id="47dca-105">Administration and Monitoring Website</span></span>

-   <span data-ttu-id="47dca-106">セルフサービスポータル</span><span class="sxs-lookup"><span data-stu-id="47dca-106">Self-Service Portal</span></span>

<span data-ttu-id="47dca-107">**重要** 両方の web サイトの構成中に、現在使用しているものと同じ接続文字列、レポート URL、グループアカウント、および web サービスアプリケーションプールドメインアカウントを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47dca-107">**Important** During the configuration of both websites, you must provide the same connection string, Reports URL, group accounts, and web service application pool domain account as the ones that you are currently using.</span></span> <span data-ttu-id="47dca-108">同じ値を使用しないと、一部のサーバーにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="47dca-108">If you don’t use the same values, you cannot access some of the servers.</span></span> <span data-ttu-id="47dca-109">現在の値を取得する**には、Windows PowerShell**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="47dca-109">To get the current values, use the **Get-MbamWebApplication** Windows PowerShell cmdlet.</span></span>

 

**<span data-ttu-id="47dca-110">管理と監視の Web サイトを別のサーバーに移動するには</span><span class="sxs-lookup"><span data-stu-id="47dca-110">To move the Administration and Monitoring Website to another server</span></span>**

1.  <span data-ttu-id="47dca-111">サーバー B で、MBAM 2.5 サーバーソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="47dca-111">On Server B, install the MBAM 2.5 Server software.</span></span> <span data-ttu-id="47dca-112">手順については、「 [MBAM 2.5 サーバーソフトウェアをインストールする](installing-the-mbam-25-server-software.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47dca-112">For instructions, see [Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md).</span></span>

2.  <span data-ttu-id="47dca-113">サーバー B で、MBAM サーバー構成ウィザードを起動し、[**新しい機能の追加**] をクリックして、[**管理と監視の web サイト**] 機能のみを選択します。</span><span class="sxs-lookup"><span data-stu-id="47dca-113">On Server B, start the MBAM Server Configuration wizard, click **Add New Features**, and then select only the **Administration and Monitoring Website** feature.</span></span>

    <span data-ttu-id="47dca-114">または、 **MbamWebApplication** Windows PowerShell コマンドレットを使用して、管理と監視の web サイトを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="47dca-114">Alternatively, you can use the **Enable-MbamWebApplication** Windows PowerShell cmdlet to configure the Administration and Monitoring Website.</span></span>

    <span data-ttu-id="47dca-115">管理と監視の web サイトを構成する方法については、「 [MBAM 2.5 Web アプリケーションを構成する方法](how-to-configure-the-mbam-25-web-applications.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47dca-115">For instructions on how to configure the Administration and Monitoring Website, see [How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md).</span></span>

**<span data-ttu-id="47dca-116">セルフサービスポータルを別のサーバーに移動するには</span><span class="sxs-lookup"><span data-stu-id="47dca-116">To move the Self-Service Portal to another server</span></span>**

1.  <span data-ttu-id="47dca-117">サーバー B で、MBAM 2.5 サーバーソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="47dca-117">On Server B, install the MBAM 2.5 Server software.</span></span> <span data-ttu-id="47dca-118">手順については、「 [MBAM 2.5 サーバーソフトウェアをインストールする](installing-the-mbam-25-server-software.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47dca-118">For instructions, see [Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md).</span></span>

2.  <span data-ttu-id="47dca-119">サーバー B で、MBAM サーバー構成ウィザードを起動し、[**新しい機能の追加**] をクリックして、[**セルフサービスポータル**機能のみ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="47dca-119">On Server B, start the MBAM Server Configuration wizard, click **Add New Features**, and then select only the **Self-Service Portal** feature.</span></span>

    <span data-ttu-id="47dca-120">または、 **MbamWebApplication** Windows PowerShell コマンドレットを使用して、セルフサービスポータルを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="47dca-120">Alternatively, you can use the **Enable-MbamWebApplication** Windows PowerShell cmdlet to configure the Self-Service Portal.</span></span>

    <span data-ttu-id="47dca-121">管理と監視の web サイトを構成する方法については、「 [MBAM 2.5 Web アプリケーションを構成する方法](how-to-configure-the-mbam-25-web-applications.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47dca-121">For instructions on how to configure the Administration and Monitoring Website, see [How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md).</span></span>

3.  <span data-ttu-id="47dca-122">組織内のクライアントコンピューターが Microsoft コンテンツ配信ネットワークにアクセスできない場合は、JavaScript ファイルも移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47dca-122">If the client computers in your organization do not have access to the Microsoft Content Delivery Network, you also have to move the JavaScript files.</span></span> <span data-ttu-id="47dca-123">[クライアントコンピューターが Microsoft コンテンツ配信ネットワークにアクセスできない場合に、セルフサービスポータルを構成する方法](how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network.md)について説明します。詳細については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="47dca-123">See [How to Configure the Self-Service Portal When Client Computers Cannot Access the Microsoft Content Delivery Network](how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network.md) for more information.</span></span>

4.  <span data-ttu-id="47dca-124">組織のセルフサービスポータルをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="47dca-124">Customize the Self-Service Portal for your organization.</span></span> <span data-ttu-id="47dca-125">「[組織のためにセルフサービスポータルをカスタマイズ](customizing-the-self-service-portal-for-your-organization.md)する」の手順に従って、現在のカスタマイズ内容を確認し、サーバー B のセルフサーバーポータルでカスタム設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="47dca-125">Use the instructions in [Customizing the Self-Service Portal for Your Organization](customizing-the-self-service-portal-for-your-organization.md) to review your current customizations and to configure custom settings on the Self-Server Portal on Server B.</span></span>



## <span data-ttu-id="47dca-126">関連トピック</span><span class="sxs-lookup"><span data-stu-id="47dca-126">Related topics</span></span>


[<span data-ttu-id="47dca-127">MBAM 2.5 Web アプリケーションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="47dca-127">How to Configure the MBAM 2.5 Web Applications</span></span>](how-to-configure-the-mbam-25-web-applications.md)

[<span data-ttu-id="47dca-128">Windows PowerShell を使用した MBAM 2.5 サーバー機能の構成</span><span class="sxs-lookup"><span data-stu-id="47dca-128">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span>](configuring-mbam-25-server-features-by-using-windows-powershell.md)

[<span data-ttu-id="47dca-129">他のサーバーへの MBAM 2.5 機能の移行</span><span class="sxs-lookup"><span data-stu-id="47dca-129">Moving MBAM 2.5 Features to Another Server</span></span>](moving-mbam-25-features-to-another-server.md)

 

## <span data-ttu-id="47dca-130">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="47dca-130">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="47dca-131">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="47dca-131">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="47dca-132">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="47dca-132">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





