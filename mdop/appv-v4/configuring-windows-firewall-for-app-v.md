---
title: APP-V 用の Windows ファイアウォールの構成
description: APP-V 用の Windows ファイアウォールの構成
author: dansimp
ms.assetid: 6b5e253c-473f-4afc-a48b-631eda11d9ca
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 274f6993b7e3d9dc60778ac5a5521c69e016f060
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821814"
---
# <span data-ttu-id="f12d0-103">APP-V 用の Windows ファイアウォールの構成</span><span class="sxs-lookup"><span data-stu-id="f12d0-103">Configuring Windows Firewall for App-V</span></span>


<span data-ttu-id="f12d0-104">App-v インフラストラクチャ内のコンポーネント間の通信をセキュリティで保護することは、環境のセキュリティ保護における要素の1つにすぎません。</span><span class="sxs-lookup"><span data-stu-id="f12d0-104">Securing the communication between components in an App-V infrastructure is only one element in securing the environment.</span></span> <span data-ttu-id="f12d0-105">サーバーでファイアウォールプログラムを使うと、攻撃対象となる領域を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="f12d0-105">Using a firewall program on the server can help reduce the attack surface area.</span></span> <span data-ttu-id="f12d0-106">このセクションのトピックでは、App-v をサポートする Windows の組み込みファイアウォール機能を構成するための手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="f12d0-106">The topics in this section provide procedures for configuring Windows built-in firewall capabilities that support App-V.</span></span> <span data-ttu-id="f12d0-107">次の手順では、管理サーバーをインストールし、RTSPS 通信用に構成されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="f12d0-107">These procedures assume that you installed a Management Server and that it has been configured for RTSPS communication.</span></span> <span data-ttu-id="f12d0-108">注意事項は、RTSP が通信に使用されているストリーミングサーバーと環境の手順に含まれています。</span><span class="sxs-lookup"><span data-stu-id="f12d0-108">Notes are included in the procedures for Streaming Servers and environments where RTSP is being used for communication.</span></span>

## <span data-ttu-id="f12d0-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f12d0-109">In This Section</span></span>


<a href="" id="how-to-configure-windows-server-2003-firewall-for-app-v"></a>[<span data-ttu-id="f12d0-110">App-V 用に Windows Server 2003 ファイアウォールを構成する方法</span><span class="sxs-lookup"><span data-stu-id="f12d0-110">How to Configure Windows Server 2003 Firewall for App-V</span></span>](how-to-configure-windows-server-2003-firewall-for-app-v.md)  
<span data-ttu-id="f12d0-111">Windows Server 2003 ファイアウォールを App-v 用に構成するために使用できる手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="f12d0-111">Provides a procedure you can use to configure the Windows Server 2003 firewall for App-V.</span></span>

<a href="" id="how-to-configure-windows-server-2008-firewall-for-app-v"></a>[<span data-ttu-id="f12d0-112">App-V 用に Windows Server 2008 ファイアウォールを構成する方法</span><span class="sxs-lookup"><span data-stu-id="f12d0-112">How to Configure Windows Server 2008 Firewall for App-V</span></span>](how-to-configure-windows-server-2008-firewall-for-app-v.md)  
<span data-ttu-id="f12d0-113">Windows Server 2008 ファイアウォールを App-v 用に構成するために使用できる手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="f12d0-113">Provides a procedure you can use to configure the Windows Server 2008 firewall for App-V.</span></span>

 

 





