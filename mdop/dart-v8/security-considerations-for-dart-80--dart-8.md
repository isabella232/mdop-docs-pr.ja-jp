---
title: DaRT 8.0 のセキュリティに関する考慮事項
description: DaRT 8.0 のセキュリティに関する考慮事項
author: dansimp
ms.assetid: 45ef8164-fee7-41a1-9a36-de4e3264e7a8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 02d32d926c0def7d33bebd399cd380eed4e8385e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812698"
---
# <span data-ttu-id="fca5f-103">DaRT 8.0 のセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="fca5f-103">Security Considerations for DaRT 8.0</span></span>


<span data-ttu-id="fca5f-104">このトピックでは、Microsoft 診断/回復ツールセット (DaRT) 8.0 に関するアカウントとグループ、ログファイル、およびその他のセキュリティ関連の考慮事項について簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="fca5f-104">This topic contains a brief overview about the accounts and groups, log files, and other security-related considerations for Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0.</span></span> <span data-ttu-id="fca5f-105">詳細については、この記事に記載されているリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fca5f-105">For more information, follow the links within this article.</span></span>

## <span data-ttu-id="fca5f-106">一般的なセキュリティの考慮事項</span><span class="sxs-lookup"><span data-stu-id="fca5f-106">General security considerations</span></span>


<span data-ttu-id="fca5f-107">**セキュリティのリスクについて**説明します。</span><span class="sxs-lookup"><span data-stu-id="fca5f-107">**Understand the security risks**.</span></span> <span data-ttu-id="fca5f-108">DaRT 8.0 には、管理者またはヘルプデスク担当者が DaRT ツールをリモートで実行して、エンドユーザーのコンピューターでの問題を解決できる機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fca5f-108">DaRT 8.0 includes functionality that lets an administrator or a help desk worker run the DaRT tools remotely to resolve problems on an end-user computer.</span></span> <span data-ttu-id="fca5f-109">さらに、国際標準化機構 (ISO) の画像を USB フラッシュドライブに保存することも、ネットワーク上に ISO 画像を配置して、コンピューターのハードディスクに回復用のパーティションとしてコンテンツを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="fca5f-109">In addition, you can save the International Organization for Standardization (ISO) image to a USB flash drive or put the ISO image on a network to include its contents as a recovery partition on a computer’s hard disk.</span></span> <span data-ttu-id="fca5f-110">これらの機能は柔軟性を備えていますが、DaRT を構成するときに考慮する必要がある潜在的なセキュリティリスクも作成します。</span><span class="sxs-lookup"><span data-stu-id="fca5f-110">These capabilities provide flexibility, but also create potential security risks that you should consider when configuring DaRT.</span></span>

<span data-ttu-id="fca5f-111">**コンピューターを物理的に保護**します。</span><span class="sxs-lookup"><span data-stu-id="fca5f-111">**Physically secure your computers**.</span></span> <span data-ttu-id="fca5f-112">管理者およびヘルプデスクの担当者が物理的にコンピューターにいない場合は、コンピューターをロックして、セキュリティで保護されたスクリーンセーバーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fca5f-112">When administrators and help desk workers are not physically at their computers, they should lock their computers and use a secured screen saver.</span></span>

<span data-ttu-id="fca5f-113">**すべてのコンピューターに最新のセキュリティ更新プログラムを適用**します。</span><span class="sxs-lookup"><span data-stu-id="fca5f-113">**Apply the most recent security updates to all computers**.</span></span> <span data-ttu-id="fca5f-114">セキュリティ通知サービス () をサブスクライブすることで、オペレーティングシステムの新しい更新について常に情報を受け取ることが <https://go.microsoft.com/fwlink/?LinkId=28819> できます。</span><span class="sxs-lookup"><span data-stu-id="fca5f-114">Stay informed about new updates for operating systems by subscribing to the Security Notification service (<https://go.microsoft.com/fwlink/?LinkId=28819>).</span></span>

## <span data-ttu-id="fca5f-115">エンドユーザーによる DaRT ツールへのアクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="fca5f-115">Limit end-user access to DaRT tools</span></span>


<span data-ttu-id="fca5f-116">DaRT リカバリ画像を作成する場合、含めるツールを選択できます。</span><span class="sxs-lookup"><span data-stu-id="fca5f-116">When you are creating the DaRT recovery image, you can select the tools that you want to include.</span></span> <span data-ttu-id="fca5f-117">セキュリティ上の理由から、ディスクワイプや Locksmith など、より強力な DaRT ツールへのエンドユーザーのアクセスを制限することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fca5f-117">For security reasons, you might want to restrict end-user access to the more powerful DaRT tools, such as Disk Wipe and Locksmith.</span></span> <span data-ttu-id="fca5f-118">DaRT 8.0 では、構成時に特定のツールを無効にすることができます。また、エンドユーザーがリモート接続機能を開始したときにデスクの担当者に連絡できるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="fca5f-118">In DaRT 8.0, you can disable certain tools during configuration and still make them available to help desk workers when the end user starts the Remote Connection feature.</span></span>

<span data-ttu-id="fca5f-119">また、リモート接続セッションを開始するオプションがエンドユーザーが利用できる唯一のツールとなるように、DaRT イメージを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="fca5f-119">You can even configure the DaRT image so that the option to start a remote connection session is the only tool available to an end user.</span></span>

<span data-ttu-id="fca5f-120">**重要** リモート接続が確立されると、その回復イメージに含まれているすべてのツール (エンドユーザーが利用できないものも含む) は、エンドユーザーのコンピューターを操作しているすべてのヘルプデスクワーカーに対して利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="fca5f-120">**Important** After the remote connection is established, all the tools that you included in the recovery image, including those unavailable to the end user, will become available to any help desk worker who is working on the end–user computer.</span></span>

 

<span data-ttu-id="fca5f-121">DaRT リカバリ画像にツールを含める方法について詳しくは、「 [dart 8.0 でのツールの概要](overview-of-the-tools-in-dart-80-dart-8.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fca5f-121">For more information about including tools in the DaRT recovery image, see [Overview of the Tools in DaRT 8.0](overview-of-the-tools-in-dart-80-dart-8.md).</span></span>

## <span data-ttu-id="fca5f-122">DaRT リカバリイメージをセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="fca5f-122">Secure the DaRT recovery image</span></span>


<span data-ttu-id="fca5f-123">DaRT リカバリ・イメージを USB フラッシュドライブに保存するか、リモートパーティションまたは回復パーティションを作成して展開する場合は、会社の推奨されるドライブ暗号化方法を ISO に含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fca5f-123">If you deploy the DaRT recovery image by saving it to a USB flash drive or by creating a remote partition or a recovery partition, you might want to include your company’s preferred method of drive encryption on the ISO.</span></span> <span data-ttu-id="fca5f-124">ISO を暗号化することにより、エンドユーザーは、回復イメージにアクセスする必要がある場合に DaRT 機能を使用できなくなり、他のユーザーに属しているコンピューターでは、不正ユーザーが DaRT を起動することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="fca5f-124">Encrypting the ISO helps to ensure that end users cannot use DaRT functionality if they were to gain access to the recovery image, and it ensures that unauthorized users cannot boot into DaRT on computers that belong to someone else.</span></span> <span data-ttu-id="fca5f-125">暗号化の方法を使用する場合は、必ずすべてのコンピューターに展開して有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="fca5f-125">If you use an encryption method, be sure to deploy and enable it in all computers.</span></span>

<span data-ttu-id="fca5f-126">**注** DaRT 8.0 は、BitLocker をネイティブでサポートしています。</span><span class="sxs-lookup"><span data-stu-id="fca5f-126">**Note** DaRT 8.0 supports BitLocker natively.</span></span>

 

<span data-ttu-id="fca5f-127">ドライブの暗号化を含めるには、回復イメージを作成するときに暗号化ソリューションファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="fca5f-127">To include drive encryption, add the encryption solution files when you create the recovery image.</span></span> <span data-ttu-id="fca5f-128">暗号化ソリューションは、WinPE で実行できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="fca5f-128">Your encryption solution must be able to run on WinPE.</span></span> <span data-ttu-id="fca5f-129">ISO から起動したエンドユーザーはその暗号化ソリューションにアクセスして、ドライブのブロックを解除することができます。</span><span class="sxs-lookup"><span data-stu-id="fca5f-129">End users who boot from the ISO are then able to access that encryption solution and unblock the drive.</span></span>

## <span data-ttu-id="fca5f-130">リモート接続を使用するときに2台のコンピューター間のセキュリティを維持する</span><span class="sxs-lookup"><span data-stu-id="fca5f-130">Maintain security between two computers when you use Remote Connection</span></span>


<span data-ttu-id="fca5f-131">既定では、**リモート接続**セッションを確立した2台のコンピューター間の通信は暗号化されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="fca5f-131">By default, the communication between two computers that have established a **Remote Connection** session may not be encrypted.</span></span> <span data-ttu-id="fca5f-132">そのため、2台のコンピューター間のセキュリティを維持するために、両方のコンピューターが同じネットワークの一部であることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fca5f-132">Therefore, to help maintain security between the two computers, we recommend that both computers are a part of the same network.</span></span>

## <span data-ttu-id="fca5f-133">関連トピック</span><span class="sxs-lookup"><span data-stu-id="fca5f-133">Related topics</span></span>


[<span data-ttu-id="fca5f-134">DaRT 8.0 のセキュリティとプライバシー</span><span class="sxs-lookup"><span data-stu-id="fca5f-134">Security and Privacy for DaRT 8.0</span></span>](security-and-privacy-for-dart-80-dart-8.md)

 

 





