---
title: App-V サーバー用にファイアウォールを構成する
description: App-V サーバー用にファイアウォールを構成する
author: dansimp
ms.assetid: f779c450-6c6f-46a8-ac66-5e82e0689d55
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 92db727eb060546ab71f2c647f2d89b662be5c64
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821817"
---
# <span data-ttu-id="3f95d-103">App-V サーバー用にファイアウォールを構成する</span><span class="sxs-lookup"><span data-stu-id="3f95d-103">Configuring the Firewall for the App-V Servers</span></span>


<span data-ttu-id="3f95d-104">Microsoft Application Virtualization (App-v) Management サーバーまたはストリーミングサーバーをインストールして、RTSP または RTSPS プロトコルを使用するように構成したら、App-v プログラムのファイアウォール例外を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f95d-104">After you install the Microsoft Application Virtualization (App-V) Management Server or Streaming Server and configure it to use the RTSP or RTSPS protocol, you must create firewall exceptions for the App-V programs.</span></span>

## <span data-ttu-id="3f95d-105">Application Virtualization Management Server のファイアウォール例外の構成</span><span class="sxs-lookup"><span data-stu-id="3f95d-105">Configuring Firewall Exceptions for Application Virtualization Management Server</span></span>


<span data-ttu-id="3f95d-106">**sghwdsptr.exe**と**sghwsvr.exe**のファイアウォール例外を作成します。</span><span class="sxs-lookup"><span data-stu-id="3f95d-106">Create a firewall exception for **sghwdsptr.exe** and **sghwsvr.exe**.</span></span> <span data-ttu-id="3f95d-107">これらのプログラムは、32ビットオペレーティングシステム上のフォルダー Virt ¥¥¥ System Center app Virt Management server¥ files に記載されています。</span><span class="sxs-lookup"><span data-stu-id="3f95d-107">These programs are found in the folder C:\\Program Files\\Microsoft System Center App Virt Management Server\\App Virt Management Server\\bin on a 32-bit operating system.</span></span> <span data-ttu-id="3f95d-108">64ビット版のオペレーティングシステムを使用している場合、このフォルダーは c/c/Virt files (x86) の下にあります。 \\ Microsoft System Center App Virt Management Server\\ app Management Server\\bin.</span><span class="sxs-lookup"><span data-stu-id="3f95d-108">If you are using a 64-bit operating system version, the folder is located under C:\\Program Files (x86)\\Microsoft System Center App Virt Management Server\\App Virt Management Server\\bin.</span></span>

## <span data-ttu-id="3f95d-109">Application Virtualization Streaming Server のファイアウォール例外の構成</span><span class="sxs-lookup"><span data-stu-id="3f95d-109">Configuring Firewall Exceptions for Application Virtualization Streaming Server</span></span>


<span data-ttu-id="3f95d-110">**sglwdsptr.exe**と**sglwsvr.exe**のファイアウォール例外を作成します。</span><span class="sxs-lookup"><span data-stu-id="3f95d-110">Create a firewall exception for **sglwdsptr.exe** and **sglwsvr.exe**.</span></span> <span data-ttu-id="3f95d-111">これらのプログラムは、32ビットオペレーティングシステム上のフォルダー Virt Virt ¥¥ System Center app xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx</span><span class="sxs-lookup"><span data-stu-id="3f95d-111">These programs are found in the folder C:\\Program Files\\Microsoft System Center App Virt Streaming Server\\App Virt Streaming Server\\bin on a 32-bit operating system.</span></span> <span data-ttu-id="3f95d-112">64ビット版のオペレーティングシステムを使用している場合、このフォルダーは c/c/Virt ファイル (x86) の下にあります。 \\ Microsoft System Center App Streaming Server\\ app Virt ストリーミング Server\\bin.</span><span class="sxs-lookup"><span data-stu-id="3f95d-112">If you are using a 64-bit operating system version, the folder is located under C:\\Program Files (x86)\\Microsoft System Center App Virt Streaming Server\\App Virt Streaming Server\\bin.</span></span>

## <span data-ttu-id="3f95d-113">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3f95d-113">Related topics</span></span>


[<span data-ttu-id="3f95d-114">サーバー ベースの展開用にサーバーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="3f95d-114">How to Configure Servers for Server-Based Deployment</span></span>](how-to-configure-servers-for-server-based-deployment.md)

[<span data-ttu-id="3f95d-115">既定のアプリケーションをインストールして構成する方法</span><span class="sxs-lookup"><span data-stu-id="3f95d-115">How to Install and Configure the Default Application</span></span>](how-to-install-and-configure-the-default-application.md)

 

 





