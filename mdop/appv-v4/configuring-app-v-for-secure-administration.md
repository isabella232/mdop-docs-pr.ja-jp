---
title: セキュリティで保護された管理用の APP-V の構成
description: セキュリティで保護された管理用の APP-V の構成
author: dansimp
ms.assetid: 4543fa81-c8cc-4b10-83b7-060778eb1349
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: de70c1df734bbf1168fd7dacf9410d3451a8a3c2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821904"
---
# <span data-ttu-id="d7ec0-103">セキュリティで保護された管理用の APP-V の構成</span><span class="sxs-lookup"><span data-stu-id="d7ec0-103">Configuring App-V for Secure Administration</span></span>


<span data-ttu-id="d7ec0-104">管理操作がセキュリティで保護されている環境では、app-v では、app-v Web Management サービスと App-v 管理コンソールの間で安全な通信を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d7ec0-104">In an environment where securing administrative operations is important, App-V allows for secure communication between the App-V Web Management Service and the App-V Management Console.</span></span> <span data-ttu-id="d7ec0-105">管理サービスは Web ベースのアプリケーションであるため、管理サービスをホストしている Web サーバー上で App-v Management Server アプリケーションをセキュリティで保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7ec0-105">Because the Management Service is a Web-based application, it requires securing the App-V Management Server application on the Web server that hosts the Management Service.</span></span> <span data-ttu-id="d7ec0-106">次の図に示すように、このプロセスでは、通信に HTTPS を使用し、Windows 統合認証のみを許可するように IIS サーバーを構成しています。</span><span class="sxs-lookup"><span data-stu-id="d7ec0-106">As shown in the following illustration, this process includes using HTTPS for communication and configuring the IIS server to allow only Windows Integrated Authentication.</span></span>

![app-v web service のネットワーク構成](images/appvmgmtwebservice.gif)

<span data-ttu-id="d7ec0-108">App-v Web 管理サービスは、IIS 上の Web ベースのアプリケーションとしてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d7ec0-108">The App-V Web Management Service is installed as a Web-based application on IIS.</span></span> <span data-ttu-id="d7ec0-109">Web 管理サービスで、App-v 管理コンソールと Web 管理サービスの間のセキュリティで保護された (SSL) 接続をサポートするには、Web 管理サービスがインストールされている IIS サーバーを構成し、App-v 管理コンソールを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7ec0-109">For the Web Management Service to support secure (SSL) connections between the App-V Management Console and the Web Management Service, you will need to configure the IIS server where the Web Management Service is installed and configure the App-V Management Console.</span></span>

## <span data-ttu-id="d7ec0-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d7ec0-110">In This Section</span></span>


<a href="" id="configuring-certificates-to-support-the-app-v-web-management-service"></a>[<span data-ttu-id="d7ec0-111">App-V Web Management Service をサポートするための証明書の構成</span><span class="sxs-lookup"><span data-stu-id="d7ec0-111">Configuring Certificates to Support the App-V Web Management Service</span></span>](configuring-certificates-to-support-the-app-v-web-management-service.md)  
<span data-ttu-id="d7ec0-112">SSL ベースの接続をサポートする証明書を構成する方法について説明します。この情報は、App-v Web Management Service の通信をセキュリティで保護するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d7ec0-112">Provides helpful information about configuring certificates to support SSL-based connections, to help secure communication for the App-V Web Management Service.</span></span>

<a href="" id="how-to-install-and-configure-the-app-v-management-console-for-a-more-secure-environment"></a>[<span data-ttu-id="d7ec0-113">より安全な環境のために APP-V Management Console をインストールして構成する方法</span><span class="sxs-lookup"><span data-stu-id="d7ec0-113">How to Install and Configure the App-V Management Console for a More Secure Environment</span></span>](how-to-install-and-configure-the-app-v-management-console-for-a-more-secure-environment.md)  
<span data-ttu-id="d7ec0-114">セキュリティで保護された接続を使用して、App-v Web 管理サービスに接続するための手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="d7ec0-114">Provides a step-by-step procedure for connecting to an App-V Web Management Service by using a secure connection.</span></span>

 

 





