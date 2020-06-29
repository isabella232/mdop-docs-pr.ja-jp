---
title: より安全な環境のために APP-V Management Console をインストールして構成する方法
description: より安全な環境のために APP-V Management Console をインストールして構成する方法
author: dansimp
ms.assetid: 9d89ef09-cdbf-48fc-99da-b24fc987ef8f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9887787d1e203410b5517439d897260305d7526e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817374"
---
# <span data-ttu-id="da9f7-103">より安全な環境のために APP-V Management Console をインストールして構成する方法</span><span class="sxs-lookup"><span data-stu-id="da9f7-103">How to Install and Configure the App-V Management Console for a More Secure Environment</span></span>


<span data-ttu-id="da9f7-104">App-v 管理コンソールの既定のインストールには、セキュリティで保護された通信のサポートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="da9f7-104">The default installation of the App-V Management Console includes support for secure communications.</span></span> <span data-ttu-id="da9f7-105">各管理コンソールは、コンソールが初めて起動されたとき、または追加の App-v Web 管理サービスに接続したときに、接続ごとに構成されます。</span><span class="sxs-lookup"><span data-stu-id="da9f7-105">Each Management Console is configured on a per-connection basis when the console is started for the first time or when connecting to an additional App-V Web Management Service.</span></span> <span data-ttu-id="da9f7-106">既定の構成では、TCP ポート443で SSL を使用しています。</span><span class="sxs-lookup"><span data-stu-id="da9f7-106">The default configuration uses SSL over TCP port 443.</span></span> <span data-ttu-id="da9f7-107">サーバーでポート番号が変更された場合は、ポート番号を変更できます。</span><span class="sxs-lookup"><span data-stu-id="da9f7-107">You can change the port number if the port number was modified on the server.</span></span> <span data-ttu-id="da9f7-108">セキュリティで保護された接続を使用して、次の手順に従って App-v Web 管理サービスに接続することができます。</span><span class="sxs-lookup"><span data-stu-id="da9f7-108">You can use the following procedure to connect to an App-V Web Management Service by using a secure connection.</span></span>

**<span data-ttu-id="da9f7-109">SSL 接続を使用して App-v 管理サービスに接続する方法</span><span class="sxs-lookup"><span data-stu-id="da9f7-109">How to Connect to an App-V Management Service by Using an SSL Connection</span></span>**

1.  <span data-ttu-id="da9f7-110">Application Virtualization 管理コンソールを起動します。</span><span class="sxs-lookup"><span data-stu-id="da9f7-110">Start the Application Virtualization Management Console.</span></span>

2.  <span data-ttu-id="da9f7-111">コンソールの操作ウィンドウで [**接続の構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da9f7-111">Click **Configure Connection** in the actions pane of the console.</span></span>

3.  <span data-ttu-id="da9f7-112">**Web サービスのホスト名**を入力し、[**セキュリティで保護**された接続の使用] が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="da9f7-112">Type the **Web Service Host Name**, and ensure that **Use Secure Connection** is selected.</span></span>

    <span data-ttu-id="da9f7-113">**重要** Web サービスのホスト名で指定された名前は、証明書の一般的な名前と一致する必要があります。接続は失敗します。</span><span class="sxs-lookup"><span data-stu-id="da9f7-113">**Important** The name provided in the Web Service Host Name must match the common name on the certificate, or the connection will fail.</span></span>

     

4.  <span data-ttu-id="da9f7-114">適切なログイン資格情報を選択して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da9f7-114">Select the appropriate login credentials, and click **OK**.</span></span>

## <span data-ttu-id="da9f7-115">関連トピック</span><span class="sxs-lookup"><span data-stu-id="da9f7-115">Related topics</span></span>


[<span data-ttu-id="da9f7-116">App-V Web Management Service をサポートするための証明書の構成</span><span class="sxs-lookup"><span data-stu-id="da9f7-116">Configuring Certificates to Support the App-V Web Management Service</span></span>](configuring-certificates-to-support-the-app-v-web-management-service.md)

 

 





