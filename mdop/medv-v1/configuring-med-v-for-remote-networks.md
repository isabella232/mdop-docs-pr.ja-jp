---
title: リモート ネットワークの MED-V の構成
description: リモート ネットワークの MED-V の構成
author: dansimp
ms.assetid: 4d2f0081-622f-4a6f-8d73-f8c2108036e0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 328376046ee5213f3d5bb09be7adf8c81f8508b1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826724"
---
# <span data-ttu-id="ae8ad-103">リモート ネットワークの MED-V の構成</span><span class="sxs-lookup"><span data-stu-id="ae8ad-103">Configuring MED-V for Remote Networks</span></span>


<span data-ttu-id="ae8ad-104">MED-V をネットワーク内部からリモートで、またはネットワーク内部からリモートから、またはその両方で動作するように構成することができます。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-104">You can configure MED-V to work from inside a network, remotely, or both from inside the network and remotely.</span></span>

## <a href="" id="bkmk-howtoconfiguremedvtoworkfrominsideanetworkorremotely"></a>


**<span data-ttu-id="ae8ad-105">ネットワーク内部から動作するように MED-V を構成するには</span><span class="sxs-lookup"><span data-stu-id="ae8ad-105">To configure MED-V to work from inside a network</span></span>**

-   <span data-ttu-id="ae8ad-106">ネットワーク内の MED-V サーバーとイメージの配布を構成します。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-106">Configure a MED-V server and image distribution inside the network.</span></span>

**<span data-ttu-id="ae8ad-107">リモートで動作するように MED-V を構成するには</span><span class="sxs-lookup"><span data-stu-id="ae8ad-107">To configure MED-V to work remotely</span></span>**

1.  <span data-ttu-id="ae8ad-108">インターネットからアクセスできる MED-V サーバーとイメージ配布サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-108">Configure a MED-V server and an image distribution server that are accessible from the Internet.</span></span>

2.  <span data-ttu-id="ae8ad-109">必要に応じて、境界ネットワーク (DMZ とも呼ばれます) のリバースプロキシを構成します。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-109">If needed, configure a perimeter network (also called a DMZ) reverse proxy.</span></span>

3.  <span data-ttu-id="ae8ad-110">*ClientSettings.xml*ファイルで認証方法を設定します。これは、 \**Servers\\Configuration \**フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-110">Set the authentication method, in the *ClientSettings.xml* file, which can be found in the **Servers\\Configuration Server\\** folder.</span></span>

**<span data-ttu-id="ae8ad-111">ネットワーク内部とリモートの両方で動作するように MED-V を構成するには</span><span class="sxs-lookup"><span data-stu-id="ae8ad-111">To configure MED-V to work both from inside a network and remotely</span></span>**

1.  <span data-ttu-id="ae8ad-112">ネットワーク内の MED-V サーバーとイメージ配信サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-112">Configure a MED-V server and image distribution server inside the network.</span></span>

2.  <span data-ttu-id="ae8ad-113">インターネットからサーバーにアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-113">Ensure that the servers are accessible from the Internet.</span></span>

3.  <span data-ttu-id="ae8ad-114">クライアントがサーバーに接続しようとしたときに、クライアントの場所に基づいて適切なサーバー (ネットワーク内またはインターネット経由) に自動的に接続されるように、DNS 解決を構成します。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-114">Configure the DNS resolution so that when the client attempts to connect to a server, it automatically connects to the correct server (within the network or over the Internet) based on the client location.</span></span>

4.  <span data-ttu-id="ae8ad-115">必要に応じて、境界ネットワークのリバースプロキシを構成します。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-115">If needed, configure a perimeter network reverse proxy.</span></span>

5.  <span data-ttu-id="ae8ad-116">*ClientSettings.xml*ファイルで認証方法を設定します。これは、 \**Servers\\Configuration \**フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-116">Set the authentication method, in the *ClientSettings.xml* file, which can be found in the **Servers\\Configuration Server\\** folder.</span></span>

<span data-ttu-id="ae8ad-117">**注** 新しい設定を適用する場合は、サービスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-117">**Note** When applying new settings, the service must be restarted.</span></span>

 

-   <span data-ttu-id="ae8ad-118">IIS 認証スキームは、BASIC、DIGEST、NTLM、または NEGOTIATE のいずれかに変更できます。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-118">You can change the IIS authentication scheme to one of the following: BASIC, DIGEST, NTLM, or NEGOTIATE.</span></span> <span data-ttu-id="ae8ad-119">既定値は NEGOTIATE で、次のエントリを使用します。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-119">The default is NEGOTIATE and uses the following entry:</span></span>

    ```xml
    <ImageDistribution>
    <!-- The authentication used for image download. Basic and digest authentication should be used only under SSL.-->
       <!-- The line below can be one of the following: -->
       <!--BG_AUTH_SCHEME>BG_AUTH_SCHEME_BASIC</BG_AUTH_SCHEME-->
       <!--BG_AUTH_SCHEME>BG_AUTH_SCHEME_DIGEST</BG_AUTH_SCHEME-->
       <!--BG_AUTH_SCHEME>BG_AUTH_SCHEME_NTLM</BG_AUTH_SCHEME-->
       <!--BG_AUTH_SCHEME>BG_AUTH_SCHEME_NEGOTIATE</BG_AUTH_SCHEME-->
       <Authentication type="Kidaro.Foundation.Bits.BG_AUTH_SCHEME">
          <BG_AUTH_SCHEME>BG_AUTH_SCHEME_NEGOTIATE</BG_AUTH_SCHEME>
       </Authentication>
    </ImageDistribution>
    ```

## <span data-ttu-id="ae8ad-120">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ae8ad-120">Related topics</span></span>


[<span data-ttu-id="ae8ad-121">MED-V インフラストラクチャの計画と設計</span><span class="sxs-lookup"><span data-stu-id="ae8ad-121">MED-V Infrastructure Planning and Design</span></span>](med-v-infrastructure-planning-and-design.md)

 

 





