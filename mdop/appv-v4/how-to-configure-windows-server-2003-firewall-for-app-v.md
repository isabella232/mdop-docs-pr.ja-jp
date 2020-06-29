---
title: App-V 用に Windows Server 2003 ファイアウォールを構成する方法
description: App-V 用に Windows Server 2003 ファイアウォールを構成する方法
author: dansimp
ms.assetid: 2c0e80f8-41e9-4164-ac83-b23b132b489a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: af75479504b454851ee2efc7ca2638d2daf45053
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817727"
---
# <span data-ttu-id="e83e5-103">App-V 用に Windows Server 2003 ファイアウォールを構成する方法</span><span class="sxs-lookup"><span data-stu-id="e83e5-103">How to Configure Windows Server 2003 Firewall for App-V</span></span>


<span data-ttu-id="e83e5-104">次の手順を使用して、WindowsServer 2003 ファイアウォールを App-v 用に構成します。</span><span class="sxs-lookup"><span data-stu-id="e83e5-104">Use the following procedure to configure the WindowsServer 2003 firewall for App-V.</span></span>

**<span data-ttu-id="e83e5-105">WindowsServer 2003 ファイアウォールを App-v 用に構成するには</span><span class="sxs-lookup"><span data-stu-id="e83e5-105">To configure WindowsServer 2003 firewall for App-V</span></span>**

1.  <span data-ttu-id="e83e5-106">**コントロールパネル**で、 **Windows ファイアウォール**を開きます。</span><span class="sxs-lookup"><span data-stu-id="e83e5-106">In **Control Panel**, open the **Windows Firewall**.</span></span>

    <span data-ttu-id="e83e5-107">**注** この手順を実行する前にサーバーがファイアウォールサービスを実行するように構成されていない場合は、ファイアウォールサービスを開始するように求められます。</span><span class="sxs-lookup"><span data-stu-id="e83e5-107">**Note** If the server has not been configured to run the firewall service before this step, you will be prompted to start the firewall service.</span></span>

     

2.  <span data-ttu-id="e83e5-108">ICO ファイルと OSD ファイルが SMB 経由で公開されている場合は、[**例外**] タブで [**ファイルとプリンターの共有**] が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e83e5-108">If ICO and OSD files are published through SMB, ensure that **File and Printer Sharing** is enabled on the **Exceptions** tab.</span></span>

    <span data-ttu-id="e83e5-109">**注** 管理サーバー上の HTTP/HTTPS を使用して、ICO ファイルと OSD ファイルが公開されている場合、HTTP または HTTPS の例外を追加する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="e83e5-109">**Note** If ICO and OSD files are published through HTTP/HTTPS on the Management Server, you might need to add an exception for HTTP or HTTPS.</span></span> <span data-ttu-id="e83e5-110">ICO ファイルと OSD ファイルをホストしている IIS サーバーが管理サーバーとは別のコンピューターでホストされている場合は、そのコンピューターに例外を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e83e5-110">If the IIS server hosting the ICO and OSD files is hosted on a computer separate from the Management Server, you need to add the exception to that computer.</span></span> <span data-ttu-id="e83e5-111">パフォーマンスを最大にするには、管理サーバーとは別のサーバー上で ICO ファイルと OSD ファイルをホストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e83e5-111">To maximize performance, it is recommended that you host the ICO and OSD files on a separate server from the Management Server.</span></span>

     

3.  <span data-ttu-id="e83e5-112">管理サーバーサービスの実行可能ファイルのプログラム例外を追加し `sghwdsptr.exe` ます。</span><span class="sxs-lookup"><span data-stu-id="e83e5-112">Add a program exception for `sghwdsptr.exe`, which is the Management Server service executable.</span></span> <span data-ttu-id="e83e5-113">この実行可能ファイルの既定のパスは `%ProgramFiles%\Microsoft System Center App Virt Management Server\App Virt Management Server\bin` です。</span><span class="sxs-lookup"><span data-stu-id="e83e5-113">The default path to this executable is `%ProgramFiles%\Microsoft System Center App Virt Management Server\App Virt Management Server\bin`.</span></span>

    <span data-ttu-id="e83e5-114">**注** 管理サーバーで、通信に RTSP を使用している場合は、のプログラム例外も追加する必要があり `sghwsvr.exe` ます。</span><span class="sxs-lookup"><span data-stu-id="e83e5-114">**Note** If the Management Server uses RTSP for communication, you must also add a program exception for `sghwsvr.exe`.</span></span>

    <span data-ttu-id="e83e5-115">App-v ストリーミングサーバーには、RTSPS 通信のプログラム例外が必要です `sglwdsptr.exe` 。</span><span class="sxs-lookup"><span data-stu-id="e83e5-115">The App-V Streaming Server requires a program exception `sglwdsptr.exe` for RTSPS communication.</span></span> <span data-ttu-id="e83e5-116">接続用に RTSP を使う App-v Streaming Server では、のプログラム例外も必要です `sglwsvr.exe` 。</span><span class="sxs-lookup"><span data-stu-id="e83e5-116">The App-V Streaming Server that uses RTSP for communication also requires a program exception for `sglwsvr.exe`.</span></span>

     

4.  <span data-ttu-id="e83e5-117">各例外に対して適切なスコープが構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e83e5-117">Ensure that the proper scope is configured for each exception.</span></span> <span data-ttu-id="e83e5-118">リスクを軽減するには、コンピューターを削除し、サーバーが応答する IP アドレスを厳密に制限します。</span><span class="sxs-lookup"><span data-stu-id="e83e5-118">To reduce risk, remove any computer and strictly limit the IP addresses to which the server will respond.</span></span>

## <span data-ttu-id="e83e5-119">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e83e5-119">Related topics</span></span>


[<span data-ttu-id="e83e5-120">App-V 用に Windows Server 2008 ファイアウォールを構成する方法</span><span class="sxs-lookup"><span data-stu-id="e83e5-120">How to Configure Windows Server 2008 Firewall for App-V</span></span>](how-to-configure-windows-server-2008-firewall-for-app-v.md)

 

 





