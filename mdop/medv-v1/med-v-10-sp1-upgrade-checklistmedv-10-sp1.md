---
title: MED-V 1.0 SP1 アップグレードのチェックリスト
description: MED-V 1.0 SP1 アップグレードのチェックリスト
author: dansimp
ms.assetid: 1a462b37-8c7a-4826-9175-0b1b701d345b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9c418eff8dfb6146204d7d9212d42e49db000fb1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827267"
---
# <span data-ttu-id="c6c80-103">MED-V 1.0 SP1 アップグレードのチェックリスト</span><span class="sxs-lookup"><span data-stu-id="c6c80-103">MED-V 1.0 SP1 Upgrade Checklist</span></span>


<span data-ttu-id="c6c80-104">Microsoft Enterprise デスクトップ仮想化 (MED-V) 1.0 から MED-V 1.0 Service Pack1 (SP1) にアップグレードするには、クライアントをアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6c80-104">To upgrade Microsoft Enterprise Desktop Virtualization (MED-V)1.0 to MED-V1.0 Service Pack1 (SP1), the client must be upgraded.</span></span> <span data-ttu-id="c6c80-105">サーバーは、必要に応じてアップグレードすることができます。</span><span class="sxs-lookup"><span data-stu-id="c6c80-105">The server can optionally be upgraded.</span></span>

## <span data-ttu-id="c6c80-106">サーバーのアップグレード</span><span class="sxs-lookup"><span data-stu-id="c6c80-106">Server Upgrade</span></span>


**<span data-ttu-id="c6c80-107">MED-V 1.0 サーバーを MED-V 1.0 SP1 にアップグレードするには</span><span class="sxs-lookup"><span data-stu-id="c6c80-107">To upgrade the MED-V1.0 server to MED-V1.0 SP1</span></span>**

1.  <span data-ttu-id="c6c80-108">\* &lt; InstallDir &gt; /Servers/configurationserver\*ディレクトリにある次のファイルをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="c6c80-108">Back up the following files that are located in the *&lt;InstallDir&gt; / Servers / ConfigurationServer* directory:</span></span>

    -   <span data-ttu-id="c6c80-109">OrganizationalPolicy.XML</span><span class="sxs-lookup"><span data-stu-id="c6c80-109">OrganizationalPolicy.XML</span></span>

    -   <span data-ttu-id="c6c80-110">ClientPolicy.XML</span><span class="sxs-lookup"><span data-stu-id="c6c80-110">ClientPolicy.XML</span></span>

    -   <span data-ttu-id="c6c80-111">WorkspaceKeys.XML</span><span class="sxs-lookup"><span data-stu-id="c6c80-111">WorkspaceKeys.XML</span></span>

2.  <span data-ttu-id="c6c80-112">\* &lt; InstallDir &gt; /Servers/ServerSettings.xml\*ファイルをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="c6c80-112">Back up the *&lt;InstallDir&gt; / Servers / ServerSettings.xml* file.</span></span>

3.  <span data-ttu-id="c6c80-113">MED-V 1.0 サーバーをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="c6c80-113">Uninstall the MED-V1.0 server.</span></span>

4.  <span data-ttu-id="c6c80-114">MED-V 1.0 SP1 サーバーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c6c80-114">Install the MED-V1.0 SP1 server.</span></span>

5.  <span data-ttu-id="c6c80-115">バックアップファイルを適切なディレクトリに復元します。</span><span class="sxs-lookup"><span data-stu-id="c6c80-115">Restore the backup files to the appropriate directories.</span></span>

6.  <span data-ttu-id="c6c80-116">MED-V server サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="c6c80-116">Restart the MED-V server service.</span></span>

<span data-ttu-id="c6c80-117">**注** サーバーの構成が既定から変更されている場合は、ファイルが別の場所に保存されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c6c80-117">**Note** If the server configuration has been changed from the default, the files might be stored in a different location.</span></span>

 

## <span data-ttu-id="c6c80-118">クライアントアップグレード</span><span class="sxs-lookup"><span data-stu-id="c6c80-118">Client Upgrade</span></span>


<span data-ttu-id="c6c80-119">Med-v 1.0 クライアントを MED-V 1.0 SP1 にアップグレードするには、med-v ファイルを med-v 1.0 クライアントにインストールします。</span><span class="sxs-lookup"><span data-stu-id="c6c80-119">To upgrade the MED-V1.0 client to MED-V1.0 SP1, install the .msp file on a MED-V1.0 client.</span></span> <span data-ttu-id="c6c80-120">クライアントと MED-V は自動的にアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="c6c80-120">The client and MED-V are automatically upgraded.</span></span>

 

 





