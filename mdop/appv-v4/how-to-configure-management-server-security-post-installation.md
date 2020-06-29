---
title: Management Server のインストール後のセキュリティを構成する方法
description: Management Server のインストール後のセキュリティを構成する方法
author: dansimp
ms.assetid: 71979fa6-3d0b-4a8b-994e-cb728d013090
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 521e72ead78055a7d3261664ccb75d454c22e622
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817937"
---
# <span data-ttu-id="63db4-103">Management Server のインストール後のセキュリティを構成する方法</span><span class="sxs-lookup"><span data-stu-id="63db4-103">How to Configure Management Server Security Post-Installation</span></span>


<span data-ttu-id="63db4-104">App-v 管理コンソールを使用して証明書を追加し、セキュリティを強化するために App-v Management Server を構成します。</span><span class="sxs-lookup"><span data-stu-id="63db4-104">Use the App-V Management Console to add the certificate and configure the App-V Management Server for enhanced security.</span></span> <span data-ttu-id="63db4-105">次の手順を使用して、セキュリティのインストール後の構成を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="63db4-105">You can use the following procedure to configure security post-installation.</span></span>

**<span data-ttu-id="63db4-106">管理サーバーのセキュリティのインストール後に構成するには</span><span class="sxs-lookup"><span data-stu-id="63db4-106">To configure Management Server security post-installation</span></span>**

1.  <span data-ttu-id="63db4-107">App-v 管理コンソールを開き、App-v 管理者の権限を持つ**管理サービス**に接続します。</span><span class="sxs-lookup"><span data-stu-id="63db4-107">Open the App-V Management Console, and connect to the **Management Service** with App-V administrator privileges.</span></span>

2.  <span data-ttu-id="63db4-108">サーバーを展開し、[**サーバーグループ**] を展開して、管理サーバーが登録されている適切なサーバーグループを選びます。</span><span class="sxs-lookup"><span data-stu-id="63db4-108">Expand the server, expand **Server Groups**, and then select the appropriate server group with which the Management Server was registered.</span></span>

3.  <span data-ttu-id="63db4-109">管理サーバーオブジェクトを右クリックし、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="63db4-109">Right-click the Management Server object, and select **Properties**.</span></span>

4.  <span data-ttu-id="63db4-110">[**ポート**] タブで、[**サーバー証明書**] をクリックし、ウィザードを完了して適切にプロビジョニングされた証明書を選びます。</span><span class="sxs-lookup"><span data-stu-id="63db4-110">On the **Ports** tab, click **Server Certificate** and complete the wizard to select the properly provisioned certificate.</span></span>

    <span data-ttu-id="63db4-111">**注** ウィザードに証明書が表示されない場合は、証明書がプロビジョニングされていないか、証明書が App-v の要件を満たしていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="63db4-111">**Note** If no certificates are displayed in the wizard, a certificate has not been provisioned or the certificate does meet the requirements of App-V.</span></span>

     

5.  <span data-ttu-id="63db4-112">[**次へ**] をクリックして、[**証明書へようこそ] ウィザード**のページに進みます。</span><span class="sxs-lookup"><span data-stu-id="63db4-112">Click **Next** to continue on to the **Welcome To Certificate Wizard** page.</span></span>

6.  <span data-ttu-id="63db4-113">[**利用可能な証明書**] 画面で適切な証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="63db4-113">Select the correct certificate in the **Available Certificates** screen.</span></span>

7.  <span data-ttu-id="63db4-114">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63db4-114">Click **Finish**.</span></span>

8.  <span data-ttu-id="63db4-115">ウィザードが完了したら、利用可能なリッスンポートとして**RTSP**をクリアします。</span><span class="sxs-lookup"><span data-stu-id="63db4-115">After completing the wizard, clear **RTSP** as an available listening port.</span></span> <span data-ttu-id="63db4-116">これにより、セキュリティで保護されていない通信チャネルを介して接続が行われるのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="63db4-116">This prevents connections from being made over a non-secure communication channel.</span></span>

9.  <span data-ttu-id="63db4-117">[**適用**] をクリックして、 **Microsoft 仮想アプリケーションサーバー**サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="63db4-117">Click **Apply**, and restart the **Microsoft Virtual Application Server** service.</span></span> <span data-ttu-id="63db4-118">このタスクを実行するには、サービスの MMC スナップインを使用します。</span><span class="sxs-lookup"><span data-stu-id="63db4-118">Use the service’s MMC snap-in to accomplish this task.</span></span>

## <span data-ttu-id="63db4-119">関連トピック</span><span class="sxs-lookup"><span data-stu-id="63db4-119">Related topics</span></span>


[<span data-ttu-id="63db4-120">Streaming Server のインストール後のセキュリティを構成する方法</span><span class="sxs-lookup"><span data-stu-id="63db4-120">How to Configure Streaming Server Security Post-Installation</span></span>](how-to-configure-streaming-server-security-post-installation.md)

[<span data-ttu-id="63db4-121">証明書のアクセス許可の問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="63db4-121">Troubleshooting Certificate Permission Issues</span></span>](troubleshooting-certificate-permission-issues.md)

 

 





