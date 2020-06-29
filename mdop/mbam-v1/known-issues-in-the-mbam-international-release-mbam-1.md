---
title: MBAM International Release の既知の問題
description: MBAM International Release の既知の問題
author: dansimp
ms.assetid: bbf888dc-93c1-4323-b43c-0ded098e9b93
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: af32551135ff297d25930f94b40bf04c0fcaaafe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825787"
---
# <span data-ttu-id="13fbb-103">MBAM International Release の既知の問題</span><span class="sxs-lookup"><span data-stu-id="13fbb-103">Known Issues in the MBAM International Release</span></span>

<span data-ttu-id="13fbb-104">このセクションでは、Microsoft BitLocker の管理と監視 (MBAM) 国際リリースに関する既知の問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="13fbb-104">This section contains known issues for Microsoft BitLocker Administration and Monitoring (MBAM) International Release.</span></span>

## <span data-ttu-id="13fbb-105">MBAM International Release の既知の問題</span><span class="sxs-lookup"><span data-stu-id="13fbb-105">Known Issues in the MBAM International Release</span></span>

### <span data-ttu-id="13fbb-106">インストールプロセスで更新プログラムが指定されていない</span><span class="sxs-lookup"><span data-stu-id="13fbb-106">The Installation Process Does Not Specify Update</span></span>

<span data-ttu-id="13fbb-107">Microsoft BitLocker の管理と監視のサーバーまたはサーバーを更新したときに、セットアッププログラムは更新プログラムがインストールされていることを示しません。</span><span class="sxs-lookup"><span data-stu-id="13fbb-107">Upon updating the Microsoft BitLocker Administration and Monitoring server or servers, the Setup program does not state that an update is being installed.</span></span>

<span data-ttu-id="13fbb-108">**回避策**: なし。</span><span class="sxs-lookup"><span data-stu-id="13fbb-108">**Workaround**: None.</span></span>

### <span data-ttu-id="13fbb-109">管理/監視サーバーの役割に使用される証明書</span><span class="sxs-lookup"><span data-stu-id="13fbb-109">Certificates Used for the Administration and Monitoring Server Role</span></span>

<span data-ttu-id="13fbb-110">MBAM サーバー間の認証に証明書を使用している場合は、MBAM 管理と監視サーバーを更新した後、証明書が有効であり、失効していないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13fbb-110">If you are using a certificate for authentication between MBAM servers, after updating the MBAM Administration and Monitoring server you must ensure that the certificate is valid and not revoked or expired.</span></span>

<span data-ttu-id="13fbb-111">**回避策**: なし。</span><span class="sxs-lookup"><span data-stu-id="13fbb-111">**Workaround**: None.</span></span>

### <span data-ttu-id="13fbb-112">MBAM Svclog ファイルディスクスペース</span><span class="sxs-lookup"><span data-stu-id="13fbb-112">MBAM Svclog File Filling Disk Space</span></span>

<span data-ttu-id="13fbb-113">[サポート技術情報の記事 2668170](https://go.microsoft.com/fwlink/?LinkID=247277)をフォローしている場合は、この更新プログラムをインストールした後で KB 手順を繰り返す必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="13fbb-113">If you have followed [Knowledge Base article 2668170](https://go.microsoft.com/fwlink/?LinkID=247277), you might have to repeat the KB steps after you install this update.</span></span>

<span data-ttu-id="13fbb-114">**回避策**: なし。</span><span class="sxs-lookup"><span data-stu-id="13fbb-114">**Workaround**: None.</span></span>

## <span data-ttu-id="13fbb-115">関連トピック</span><span class="sxs-lookup"><span data-stu-id="13fbb-115">Related topics</span></span>

[<span data-ttu-id="13fbb-116">MBAM 1.0 Language Release 更新プログラムの展開</span><span class="sxs-lookup"><span data-stu-id="13fbb-116">Deploying the MBAM 1.0 Language Release Update</span></span>](deploying-the-mbam-10-language-release-update.md)

 

 





