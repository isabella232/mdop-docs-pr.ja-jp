---
title: クラスター モードの MED-V サーバーの構成
description: クラスター モードの MED-V サーバーの構成
author: dansimp
ms.assetid: 41f0b2a3-4ce9-48e1-a6fb-4c13c4228515
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ddb7dd5af65d8a465c5c1884bb27a3027621bac1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826717"
---
# <span data-ttu-id="ca05e-103">クラスター モードの MED-V サーバーの構成</span><span class="sxs-lookup"><span data-stu-id="ca05e-103">Configuring MED-V Server for Cluster Mode</span></span>


<span data-ttu-id="ca05e-104">クラスターモードでは、MED-V サーバーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="ca05e-104">You can configure the MED-V server in cluster mode.</span></span> <span data-ttu-id="ca05e-105">クラスターモードでは、2つのサーバーが使われ、両方のサーバーに対して同一のファイルがすべてファイルシステムに配置されます。</span><span class="sxs-lookup"><span data-stu-id="ca05e-105">In cluster mode, two servers are used and all files identified as mutual to both servers are placed on a file system.</span></span> <span data-ttu-id="ca05e-106">サーバーは、ファイルをローカルに保存するのではなく、ファイルシステムからファイルにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ca05e-106">The server accesses the files from the file system rather than storing the files locally.</span></span>

## <a href="" id="bkmk-howtoconfigurethemedvserverinclustermode"></a>


**<span data-ttu-id="ca05e-107">クラスターモードで MED-V サーバーを構成するには</span><span class="sxs-lookup"><span data-stu-id="ca05e-107">To configure the MED-V server in cluster mode</span></span>**

1.  <span data-ttu-id="ca05e-108">いずれかのサーバーに MED-V をインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="ca05e-108">Install and configure MED-V on one of the servers.</span></span>

2.  <span data-ttu-id="ca05e-109">すべてのサーバーがアクセスできる中央の場所で共有ネットワークを作成します。</span><span class="sxs-lookup"><span data-stu-id="ca05e-109">Create a shared network in a central location where all of the servers can access it.</span></span>

3.  <span data-ttu-id="ca05e-110">\* &lt; InstallDir &gt; //Dns/configurationserver\*フォルダーの内容を共有ネットワークにコピーします。</span><span class="sxs-lookup"><span data-stu-id="ca05e-110">Copy the contents of the *&lt;InstallDir&gt;/Servers/ConfigurationServer* folder to the shared network.</span></span>

4.  <span data-ttu-id="ca05e-111">指定したすべてのサーバーに MED-V サーバーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ca05e-111">Install MED-V server on all designated servers.</span></span>

5.  <span data-ttu-id="ca05e-112">共有ネットワークで、すべての MED-V サーバーシステムアカウントへのフルアクセスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ca05e-112">On the shared network, assign full access to all MED-V server system accounts.</span></span>

6.  <span data-ttu-id="ca05e-113">各サーバーで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ca05e-113">On each server, do the following:</span></span>

    1.  <span data-ttu-id="ca05e-114">\* &lt; InstallDir &gt; //dns/ServerConfiguration.xml\*ファイルで、 \* &lt; storepath &gt; \*の値を共有ネットワークパスに設定します。</span><span class="sxs-lookup"><span data-stu-id="ca05e-114">In the *&lt;InstallDir&gt;/Servers/ServerConfiguration.xml* file, set the value of *&lt;StorePath&gt;* to the shared network path.</span></span>

    2.  <span data-ttu-id="ca05e-115">使用しているサーバーから\* &lt; instsalldir &gt; /servers/KeyPair.xml\*ファイルをすべての med-v サーバーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="ca05e-115">Copy the *&lt;InstsallDir&gt;/Servers/KeyPair.xml* file from the original server to all MED-V servers.</span></span>

    3.  <span data-ttu-id="ca05e-116">MED-V サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="ca05e-116">Restart the MED-V service.</span></span>

<span data-ttu-id="ca05e-117">**注** すべてのサーバーのローカル設定が同じ (リッスンポート、IIS サーバー、管理アクセス許可、レポートデータベースなど) の場合は、 \* &lt; InstallDir/servers &gt; /ServerSettings.xml\*をすべてのサーバーで共有することもできます。</span><span class="sxs-lookup"><span data-stu-id="ca05e-117">**Note** If all servers have the same local settings (such as listening ports, IIS server, management permissions, report database, and so on), the *&lt;InstallDir&gt;/Servers/ServerSettings.xml* can be shared by all servers as well.</span></span>

 

## <span data-ttu-id="ca05e-118">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ca05e-118">Related topics</span></span>


[<span data-ttu-id="ca05e-119">MED-V インフラストラクチャの計画と設計</span><span class="sxs-lookup"><span data-stu-id="ca05e-119">MED-V Infrastructure Planning and Design</span></span>](med-v-infrastructure-planning-and-design.md)

 

 





