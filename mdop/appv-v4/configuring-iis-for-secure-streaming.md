---
title: セキュリティで保護されたストリーミング用の IIS の構成
description: セキュリティで保護されたストリーミング用の IIS の構成
author: dansimp
ms.assetid: 9a80a703-4642-4bec-b7af-dc7cb6b76925
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 724fd247d98c265421cea13f4b91c97049a2b4d4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821884"
---
# <span data-ttu-id="93434-103">セキュリティで保護されたストリーミング用の IIS の構成</span><span class="sxs-lookup"><span data-stu-id="93434-103">Configuring IIS for Secure Streaming</span></span>


<span data-ttu-id="93434-104">Microsoft Application Virtualization (App-v) バージョン4.5 のリリースでは、HTTP と HTTPS を、ストリーミングアプリケーションパッケージのプロトコルとして使うことができます。</span><span class="sxs-lookup"><span data-stu-id="93434-104">With the release of Microsoft Application Virtualization (App-V) version 4.5, you can use HTTP and HTTPS as protocols for streaming application packages to the App-V clients.</span></span> <span data-ttu-id="93434-105">このオプションを使用すると、IIS が通常提供する追加のスケーラビリティを組織が活用できます。</span><span class="sxs-lookup"><span data-stu-id="93434-105">This option enables organizations to leverage the additional scalability that IIS typically offers.</span></span> <span data-ttu-id="93434-106">ストリーミングサーバーとして IIS を使う場合は、HTTP の代わりに HTTPS を使用して、クライアントとサーバー間の通信をセキュリティで保護することができます。</span><span class="sxs-lookup"><span data-stu-id="93434-106">When you use IIS as a streaming server, you can help secure the communications between the client and server by using HTTPS instead of HTTP.</span></span>

<span data-ttu-id="93434-107">**注** ファイルサーバーからアプリケーションをストリーミングする場合は、アプリケーションパッケージへの通信のセキュリティを強化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93434-107">**Note** If you want to stream applications from a file server, you should enhance the security of the communications to the application packages.</span></span> <span data-ttu-id="93434-108">これは IPsec を使って実現できます。</span><span class="sxs-lookup"><span data-stu-id="93434-108">This can be achieved using IPsec.</span></span> <span data-ttu-id="93434-109">詳細については、TechNet ライブラリの次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="93434-109">For more information see the following topics in the TechNet Library:</span></span>

-   <span data-ttu-id="93434-110">Windows Server2003 の場合は、</span><span class="sxs-lookup"><span data-stu-id="93434-110">For Windows Server2003,</span></span> <https://go.microsoft.com/fwlink/?LinkId=133226>

-   <span data-ttu-id="93434-111">Windows Server 2008 の場合は、</span><span class="sxs-lookup"><span data-stu-id="93434-111">For Windows Server 2008,</span></span> <https://go.microsoft.com/fwlink/?LinkId=133227>

 

## <span data-ttu-id="93434-112">MIME の種類</span><span class="sxs-lookup"><span data-stu-id="93434-112">MIME Types</span></span>


<span data-ttu-id="93434-113">IIS を使って HTTP または HTTPS で仮想アプリケーションをストリーミングする場合、App-v をサポートするには、次の MIME の種類を IIS サーバーに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93434-113">When you use IIS to stream virtual applications with HTTP or HTTPS, to support App-V, the following MIME types must be added to the IIS server:</span></span>

-   <span data-ttu-id="93434-114">.OSD = TXT</span><span class="sxs-lookup"><span data-stu-id="93434-114">.OSD=TXT</span></span>

-   <span data-ttu-id="93434-115">.SFT = バイナリ</span><span class="sxs-lookup"><span data-stu-id="93434-115">.SFT=Binary</span></span>

<span data-ttu-id="93434-116">MIME の種類を追加するためのガイダンスとして、次のサポート技術情報の記事を使用します。</span><span class="sxs-lookup"><span data-stu-id="93434-116">Use the following KB articles as guidance for adding MIME types:</span></span>

<span data-ttu-id="93434-117">IIS 6.0:</span><span class="sxs-lookup"><span data-stu-id="93434-117">IIS 6.0:</span></span> <https://go.microsoft.com/fwlink/?LinkId=151973>

<span data-ttu-id="93434-118">IIS 7.0:</span><span class="sxs-lookup"><span data-stu-id="93434-118">IIS 7.0:</span></span> <https://go.microsoft.com/fwlink/?LinkId=151977>

## <span data-ttu-id="93434-119">Kerberos 認証</span><span class="sxs-lookup"><span data-stu-id="93434-119">Kerberos Authentication</span></span>


<span data-ttu-id="93434-120">HTTP または HTTPS と Kerberos 認証を使用して、ICO、OSD、または SFT の各ファイルをストリーミングする場合、環境のセキュリティが強化されます。</span><span class="sxs-lookup"><span data-stu-id="93434-120">When you use HTTP or HTTPS and Kerberos authentication to stream ICO, OSD, or SFT files, you are enhancing the security of your environment.</span></span> <span data-ttu-id="93434-121">ただし、IIS で Kerberos 認証をサポートするには、適切なサービスプリンシパル名 (SPN) を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93434-121">However, for IIS to support Kerberos authentication, you must configure a proper Service Principal Name (SPN).</span></span> <span data-ttu-id="93434-122">この `setspn.exe` ツールは、インストール CD のサポートツールから Windows Server2003 で利用でき、Windows Server2008 に組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="93434-122">The `setspn.exe` tool is available for Windows Server2003 from the Support Tools on the installation CD and is built-in to Windows Server2008.</span></span>

<span data-ttu-id="93434-123">SPN を作成するには、 `setspn.exe` ドメイン管理者のメンバーとしてログインしているときに、コマンドプロンプトから実行します (例:) `setspn.exe –A HTTP/FQDN of Server ServerName` 。</span><span class="sxs-lookup"><span data-stu-id="93434-123">To create an SPN, run `setspn.exe` from a command prompt while logged in as a member of Domain Administrators—for example, `setspn.exe –A HTTP/FQDN of Server ServerName`.</span></span>

## <span data-ttu-id="93434-124">関連トピック</span><span class="sxs-lookup"><span data-stu-id="93434-124">Related topics</span></span>


[<span data-ttu-id="93434-125">インストール後の安全な通信のための Management Server または Streaming Server の構成</span><span class="sxs-lookup"><span data-stu-id="93434-125">Configuring Management or Streaming Server for Secure Communications Post-Installation</span></span>](configuring-management-or-streaming-server-for-secure-communications-post-installation.md)

 

 





